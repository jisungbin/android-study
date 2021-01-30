# android-study
android 공부할거야!

> [ios 공부할거야!](https://github.com/sungbin5304/ios-study)

-----

1. 인터페이스
2. 구현체
3. MutableList
4. getSystemService context
5. di scope 범위 (activity, context)
6. rx 구독 생명주기 관리
7. 패키지 구분은 비슷한 클래스끼리로 묶기
8. 엑티비티에서도 databinding 활용하기
9. Parcelize
10. **[밑에 코드](https://github.com/fornewid/android-animation-11p-more/blob/end/sample/src/main/java/soup/animation/sample/SplashActivity.kt#L17) 이해하기**
```kotlin
private val binding by viewBindings(SplashActivityBinding::inflate)

inline fun <reified VB : ViewBinding> Activity.viewBindings(
    crossinline inflater: (LayoutInflater) -> VB
): Lazy<VB> {
    return lazy(LazyThreadSafetyMode.NONE) {
        inflater.invoke(layoutInflater)
    }
}
```
