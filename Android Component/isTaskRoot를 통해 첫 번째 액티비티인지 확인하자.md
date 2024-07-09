## `isTaskRoot`를 통해 첫 번째 액티비티인지 확인하자
- Activity[.isTaskRoot](https://developer.android.com/reference/android/app/Activity#isTaskRoot())는 액티비티가 태스크 중 첫 번째 액티비티인지 반환
### 사용 예시
```
if (isTaskRoot) {
    startActivity(Intent(this, MainActivity::class.java))
    finish()
}
```
