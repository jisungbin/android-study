# android-study
android 공부할거야!

> [ios 공부할거야!](https://github.com/sungbin5304/ios-study)

-----

1. - [x] interface
2. - [x] ~~구현체~~
3. - [x] MutableList
4. - [ ] getSystemService context scope (use application or activity)
5. - [ ] di scope 범위 (activity, context)
6. - [ ] rx 구독 생명주기 관리
7. - [x] 패키지 구분은 비슷한 클래스끼리로 묶기
8. - [x] 엑티비티에서도 databinding 활용하기
9. - [ ] Parcelize / Serializable
10. - [ ] 밑에 코드 이해하기 [[원본코드]](https://github.com/fornewid/android-animation-11p-more/blob/end/sample/src/main/java/soup/animation/sample/SplashActivity.kt#L17)
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
11. - [ ] android:configChanges 속성
12. - [ ] 인텐드애서 newTask 관련 -> task 관련
13. - [ ] [Clean Architecture](https://codechacha.com/ko/android-clean-architecture/)
14. - [ ] Kotlin open vs abstract
15. - [x] repository 폴더는 무슨 역할을 담는 폴더 일까? -> 대충 이해 완료
16. - [x] \~\~Impl 클래스는 무슨 역할을 하는 클래스 일까?
17. - [ ] di(dagger2, hilt) 심화 학습
18. - [ ] windowSoftInputMode 관련 정보
19. - [ ] @Binds가 뭘 까? in Dagger2
20. - [ ] what is Observable in DataBidning
21. - [ ] ConstraintLayout 자세한 정보
22. - [ ] Flow 관련
23. - [ ] StateFlow / SharedFlow
24. - [ ] Why use .invoke ?
25. - [x] 밑에 코드 이해하기 [(callbackFlow)](https://medium.com/harrythegreat/kotlin-%EC%BD%94%EB%A3%A8%ED%8B%B4%EC%9D%98-callbackflow%EC%99%80-channelflow-f4e66c9fa116)
```kotlin
@ExperimentalCoroutinesApi 
fun testFirestoreSnapshotObserve() = callbackFlow {
    val databaseReference = FirebaseFirestore.getInstance().collection("test").document("user")
    val eventListener = databaseReference.addSnapshotListener { value, _ ->
        val userData = value?.toObject(UserDTO::class.java)
        this@callbackFlow.sendBlocking(userData!!)
    }
    awaitClose {
        eventListener.remove()
    }
}
```
26. - [ ] ~~ReKotlin~~
27. - [x] ScopedStorage
28. - [x] [suspend](https://stackoverflow.com/a/52925057)
29. - [ ] [Delegates](https://medium.com/hongbeomi-dev/%EB%B2%88%EC%97%AD-%EB%82%B4%EC%9E%A5%EB%90%9C-delegates-2%ED%8E%B8-bc4a23cb6f10)
30. - [x] [레포지토리 패턴](https://devvkkid.tistory.com/196)
