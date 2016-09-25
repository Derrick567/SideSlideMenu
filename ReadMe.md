### 一.自定屬性  
  rightPadding :值越大 menu寬度越小  
#### 1.使用時
layout需先加上這行
>xmlns:mytools1="http://schemas.android.com/apk/res-auto"
  (*mytools1為自定名稱)
  
#### 2.當使用自定屬性, 會call 3個參數的constructor  
  
      public MyHorizontalScrollView(Context context, AttributeSet attrs, int defStyleAttr) {
       ...
       }
#### 2.獲取自訂屬性
     TypedArray a = context.getTheme().obtainStyledAttributes(attrs, R.styleable.MyHorizontalScrollView, defStyleAttr, 0);
      int n = a.getIndexCount();
        for (int i = 0; i < n; i++) {
            int attr = a.getIndex(i);
            switch (attr) {
                case R.styleable.MyHorizontalScrollView_rightPadding:
                mMenuRightPadding = a.getDimensionPixelSize(attr,
                (int) TypedValue.applyDimension
                      (TypedValue.COMPLEX_UNIT_DIP, 50, context.getResources().getDisplayMetrics()));
            }
        }
        //使用完需要回收
        a.recycle();

### 二.動畫效果
   scale = 1.0~0.0
#### 1. 內容區域 
   縮放: 1.0~0.7
   0.7+0.3*scale
#### 2. Menu 
   縮放: 0.7~1.0 
   1.0-0.3*scale
   透明度:0.6~1.0
   0.6+0.4*(1-scale)
