## 풀이

우선 index.html 소스를 확인해보자.

```html
<!doctype html>
<html>
<head>
  <meta charset="utf-8">
  <title>Welcome</title>
</head>

<body>
  <h1>Welcome! 👋</h1>
  <form method="POST">
    <input type="hidden" name="64se64_encoding" value="IyEvdXNyL2Jpbi9lbnYgcHl0aG9uMwphc2M9WzY4LCA3MiwgMTIzLCA5OCwgMTAxLCA0OCwgNTIsIDU0LCA5OCwgNTUsIDUzLCA1MCwgNTAsIDk3LCA5NywgNTAsIDEwMSwgNTAsIDU2LCAxMDIsIDUwLCA1NSwgNTQsIDEwMSwgNDgsIDk5LCA1NywgNDksIDQ4LCA1MywgNTAsIDQ5LCAxMDIsIDUwLCA1MSwgOTcsIDQ4LCA1MywgNTYsIDU1LCA0OCwgNDgsIDUzLCA5NywgNTYsIDUxLCA1NSwgNTUsIDUxLCA1NSwgNDgsIDk3LCA0OSwgNDksIDEwMSwgNTMsIDEwMSwgNTIsIDEwMCwgOTksIDQ5LCA1MywgMTAyLCA5OCwgNTAsIDk3LCA5OCwgMTI1XQphcnI9WzAgZm9yIGkgaW4gcmFuZ2UoNjgpXQpmb3IgaSBpbiByYW5nZSgwLDY4KToKICAgIGFycltpXT1jaHIoYXNjW2ldKQpmbGFnPScnLmpvaW4oYXJyKQpwcmludChmbGFnKQ==">
  </form>
</body>
</html>
```

value가 힌트인 것 같으니 Base64 디코딩을 진행해보자.
결과는 다음과 같다.

```python
#!/usr/bin/env python3
asc=[68, 72, 123, 98, 101, 48, 52, 54, 98, 55, 53, 50, 50, 97, 97, 50, 101, 50, 56, 102, 50, 55, 54, 101, 48, 99, 57, 49, 48, 53, 50, 49, 102, 50, 51, 97, 48, 53, 56, 55, 48, 48, 53, 97, 56, 51, 55, 55, 51, 55, 48, 97, 49, 49, 101, 53, 101, 52, 100, 99, 49, 53, 102, 98, 50, 97, 98, 125]
arr=[0 for i in range(68)]
for i in range(0,68):
    arr[i]=chr(asc[i])
flag=''.join(arr)
print(flag)
```

이를 파이썬 ide에 실행시켜보면 flag 값을 출력한다.

> DH{be046b7522aa2e28f276e0c910521f23a0587005a8377370a11e5e4dc15fb2ab}