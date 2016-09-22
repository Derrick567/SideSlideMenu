### 1.自定屬性

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
  
