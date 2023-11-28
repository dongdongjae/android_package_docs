## UserValidate

### isPossibleSignin()
사용자로부터 입력받은 로그인 정보(email, password)를 서버에 전송하기 전에 호출하여 Form validate 하는 메서드입니다. 
```kotlin
import com.example.userlibrary.UserValidate

val validateResult = 
    UserValidate.isPossibleSignin(email, password)
```

<br />
**isPossibleSignin 파라미터** 
<br />

---


<P><span style="font-weight:bold">email</span> <span style="color:red">필수</span> · <span style="color:green">string</span></p>
사용자의 이메일입니다.  

---

<P><span style="font-weight:bold">passwordOne</span> <span style="color:red">필수</span> · <span style="color:green">string</span></p>
사용자의 비밀번호입니다. 반드시 6글자 이상의 문자열이어야 합니다.

---

</br>
빈 문자열이 있는지 또는 이메일이 정규식(@, . 포함)에 맞게 작성되었는지, 비밀번호가 6글자 이상인지에 대해 검사를 실시합니다. 검사에 실패하는 경우 False와 실패 메시지를 반환하고, 반대로 성공하는 경우  True와 성공 메시지를 반환합니다.

<span style="color:red">Fail</span>

```kotlin
// 빈 문자열이 있는 경우
{
    "result": false,
    "message": "이메일 또는 비밀번호를 다시 확인해주세요.",
}

// 이메일을 정확하게 입력하지 않은 경우
{
    "result": false,
    "message": "이메일을 다시 확인해주세요.",
}

// 비밀번호가 6글자 이상이 아닌 경우
{
    "result": false,
    "message": "비밀번호는 6글자 이상 작성해야합니다.",
}
```

<span style="color:blue">Success</span>

```kotlin
{
    "result": true,
    "message": "로그인",
}
```

</br> 

### isPossibleSignup() 
사용자로부터 입력받은 회원가입 정보(email, passwordOne, passwordTwo, username)를 서버에 전송하기 전에 호출하여 Form validate 하는 메서드입니다. 
```kotlin
import com.example.userlibrary.UserValidate

val validateResult = 
    UserValidate.isPossibleSignup(email, passwordOne, passwordTwo, username)
```
<br />
**isPossibleSignup 파라미터** 
<br />

---


<P><span style="font-weight:bold">email</span> <span style="color:red">필수</span> · <span style="color:green">string</span></p>
사용자의 이메일입니다.  

---

<P><span style="font-weight:bold">passwordOne</span> <span style="color:red">필수</span> · <span style="color:green">string</span></p>
사용자의 비밀번호입니다. 반드시 6글자 이상의 문자열이어야 합니다.

---

<P><span style="font-weight:bold">passwordTwo</span> <span style="color:red">필수</span> · <span style="color:green">string</span></p>
사용자가 재입력한 비밀번호입니다. 반드시 6글자 이상의 문자열이어야 합니다.

---

<P><span style="font-weight:bold">username</span> <span style="color:red">필수</span> · <span style="color:green">string</span></p>
사용자의 이름(닉네임)입니다.  

---

<br />
빈 문자열이 있는 경우 또는 이메일이 제대로 작성되어있는지, 비밀번호가 6글자 이상인지, 두 번 작성된 비밀번호가 서로 일치한지에 대해 검사를 실시합니다. 검사에 실패하는 경우 False와 실패 메시지를 반환하고, 반대로 성공하는 경우  True와 성공 메시지를 반환합니다.

<br />
<span style="color:red">Fail</span>

```kotlin
// 빈 문자열이 있는 경우
{
    "result": false,
    "message": "빈 항목이 없는지 확인해주세요.",
}

// 이메일을 정확하게 입력하지 않은 경우
{
    "result": false,
    "message": "이메일을 다시 확인해주세요.",
}

// 비밀번호가 6글자 이상이 아닌 경우
{
    "result": false,
    "message": "비밀번호는 6글자 이상 작성해야합니다.",
}

// 입력된 두 비밀번호가 서로 다른 경우
{
    "result": false,
    "message": "비밀번호가 서로 다릅니다.",
}
```

<br />
<span style="color:blue">Success</span>
```kotlin
{
    "result": true,
    "message": "회원가입",
}
```

<br/ >
<br/ >
<br/ >
