# DispatchQueue.main.asyncAfter

특정 코드를 일정한 시간 뒤에 실행시키고자 할 때
DispatchQueue.main.asyncAfter 를 사용한다.

```Swift
DispatchQueue.main.asyncAfter(deadline: .now() + 5.0) {
  print("Not found")
}
```

[Apple Documents][apple]

[apple]: https://developer.apple.com/documentation/dispatch/dispatchqueue/2300020-asyncafter
