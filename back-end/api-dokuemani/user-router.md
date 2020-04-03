# 👤 User Router

## 🔗 URL

```text
https://cocukasistan.herokuapp.com/
```

{% api-method method="post" host="URL" path="/user/login" %}
{% api-method-summary %}
🚪 Login Metodu
{% endapi-method-summary %}

{% api-method-description %}
Giriş yapma metodu
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="email" type="string" required=true %}
📧 Kullanıcının maili
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
🔏 Kullanıcının şifresi
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
✔️ Başarı giriş yapma durumu
{% endapi-method-response-example-description %}

```javascript
{
  "code": 200,
  "message": "Logged in successfully",
  "data": {
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MTIsImlhdCI6MTU4MzQwNTEyNn0.0HwBhXl6utA5tAD4ryu9Mj1lHuW-PgcmyYJOvERPwkA"
  }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=422 %}
{% api-method-response-example-description %}
✖️ Hatalı mail veya şifre durumu
{% endapi-method-response-example-description %}

```javascript
{
  "code": 422,
  "message": "Incorrect email or password"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
✖️ Token oluşturma hatası  
✖️ Deşifreleme hatası  
- 👮‍♂️ İki durumda da server hatası olduğu için aynı kod kullanılmıştır
{% endapi-method-response-example-description %}

```javascript
{
  "code": 500,
  "message": "An error occured while creating token"
}

{
    "code": 500,
    "message": "An error occured while comparing password"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=503 %}
{% api-method-response-example-description %}
🗃️ Veritabnı hatası
{% endapi-method-response-example-description %}

```javascript
{
    "code": 503,
    "message": "Database error"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="URL" path="/user/signup" %}
{% api-method-summary %}
👤 Signup Metodu
{% endapi-method-summary %}

{% api-method-description %}
Yeni kullanıcı ekleme metodu
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="email" type="string" required=true %}
📧 Kullanıcı maili
{% endapi-method-parameter %}

{% api-method-parameter name="full\_name" type="string" required=true %}
🆎 Kullanıcının full ismi
{% endapi-method-parameter %}

{% api-method-parameter name="password" type="string" required=true %}
🔏 Kullanıcı şifresi
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
✔️ Başarı durumu
{% endapi-method-response-example-description %}

```javascript
// URL/user/signup
{
"code": 200,
"message": "The mail was sent in successfully",
"data": null
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
✖️ Kullanıcı veritabanında mevcut hatası  
✖️ Token oluşturma hatası  
✖️ Mail gönderme hatası
{% endapi-method-response-example-description %}

```javascript
{
"code": 500,
"message": "User is exist"
}
-------------------------
{
"code": 500,
"message": "An error occured while creating token"
}
-------------------------
{
"code": 500,
"message": "An error occured while sending mail"
}

```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=503 %}
{% api-method-response-example-description %}
✖️Veri eklenirken hata oluşma durumu
{% endapi-method-response-example-description %}

```javascript
// URL/user/signup
{
"code": 503,
"message": "Database error"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="post" host="URL" path="/user/updatePassword" %}
{% api-method-summary %}
🔒 Şifre Güncelleme Metodu
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}
🔒 Login token'ı
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="new\_password " type="string" required=true %}
🔏 Yeni şifre
{% endapi-method-parameter %}
{% endapi-method-body-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
✔️ Başarı durumu
{% endapi-method-response-example-description %}

```javascript
{
    "code": 200,
    "message": "Updated password in successfully",
    "data": null
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=500 %}
{% api-method-response-example-description %}
✖️ Hash hatası
{% endapi-method-response-example-description %}

```javascript
{
    "code": 500,
    "message": "An error occured while hashing password"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=503 %}
{% api-method-response-example-description %}
✖️ Veritabanı hatası
{% endapi-method-response-example-description %}

```javascript
{
    "code": 503,
    "message": "Database error"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

{% api-method method="get" host="URL" path="/user/getInfo" %}
{% api-method-summary %}
🔸 getInfo Metodu
{% endapi-method-summary %}

{% api-method-description %}
Gelen token ile kullanıcı mailini ve ismini çekme metodu
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}
🔒 signup linkindeki token
{% endapi-method-parameter %}
{% endapi-method-headers %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
✔️ Başarı durumu
{% endapi-method-response-example-description %}

```javascript
{
    "code": 200,
    "message": "Success",
    "data": {
        "full_name": "Umut Bulak",
        "email": "umut_aslan95@hotmail.com"
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=422 %}
{% api-method-response-example-description %}
✖️ Geçersiz token durumu
{% endapi-method-response-example-description %}

```
{
    "code": 422,
    "message": "Invalid token"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

