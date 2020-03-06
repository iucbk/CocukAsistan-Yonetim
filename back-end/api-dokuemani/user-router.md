# 👤 User Router

## 🔗 URL

```text
https://cocukasistan.azurewebsites.net
```

## 🚪 Login

{% api-method method="post" host="URL" path="/user/login" %}
{% api-method-summary %}
Login Method
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
{% endapi-method-response-example-description %}

```javascript
{
  "code": 500,
  "message": "An error occured while creating token"
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

