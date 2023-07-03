# APIDoc

PATH:https://XXX

## 用户

### 注册

POST PATH/v1/users/register
**request**

```json
{
    username: string,
    password: string,
}
```

**response**
邮箱验证

### 登录

GET PATH/v1/users/login
**request**

```json
{
    username: string,
    password: string,
}
```

**response**

```json
{
    profile: {
        //存储用户个人信息
        username:
    },
    work:{
        //存储用户之前的作品信息
    }，
    subscription{
        //存储用户订阅情况
    }
}
```

### 忘记密码

GET PATH/v1/users/reset
**request**

```json
{
    username: string,
}
```

**response**
发个重设密码邮件

### 重设密码

PUT PATH/v1/users/register
**request**

```json
{
    username: string,
    password: string,
}
```

**response**
和 login 的一样

## 作品

### 转换

POST PATH/v1/works/generate
**request**

```json
{
    generateImageUri: string,
    prompt: string,
    negativePrompt: string,
    Module: string (?number?),
    weight: number,
}
```

**response**

```json
{
    convertedImageUris: Array<string>,
}
```

### 印章

POST PATH/v1/works/seal
**request**

```json
{
    sealImageUri: string,
    sealType: string (?number?),
    postion:{
        //长方形的四个点
        x1:number,
        x2:number,
        y1:number,
        y2:number,
    }
}
```

**response**

```json
{
    processedImageUri: string,
}
```
