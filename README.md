# 杂记
## View的相关回调函数
* 绘制相关<br>
    onMeasure,onLayout, onDraw, onSizeChanged<br>
  * onMeasure * 2(自己) -> onSizeChanged -> onLayout(自己) -> onMeasure(父) * 2 -> onLayout(父) -> visible ? onDraw : pass
* 生命周期相关<br>
    construct, onFinishInflate, onVisibilityChanged, onRtlPropertiesChanged, ,onAttachedToWindow, onWindowVisibilityChanged, onWindowFocusChanged, onDetachedFromWindow<br>
  * onVisibilityChanged -> construct -> onFinishInflate  -> onVisibilityChanged * 2 -> onRtlPropertiesChanged * 2 -> onAttachedToWindow   -> onWindowVisibilityChanged -> gone ? pass : 绘制相关 -> onWindowFocusChanged -> 用户可见,可交互 -> onWindowFocusChanged -> onWindowVisibilityChanged -> onDetachedFromWindow
* 点击事件相关<br>
    dispatchTouchEvent, onInterceptTouchEvent, onTouchEvent<br>
  * Activity.dispatchTouchEvent -> ViewGroup.dispatchTouchEvent -> ViewGroup.onInterceptTouchEvent -> View.dispatchTouchEvent -> View.onInterceptTouchEvent -> View.onTouchEvent -> ViewGroup.onTouchEvent -> Activity.onTouchEvent
