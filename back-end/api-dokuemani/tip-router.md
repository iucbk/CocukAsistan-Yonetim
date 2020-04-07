# 🔔 Tip Router

## 🔗 URL

```text
https://cocukasistan.herokuapp.com/
```

{% api-method method="post" host="URL" path="/notification/getTip" %}
{% api-method-summary %}
🎈 getTip
{% endapi-method-summary %}

{% api-method-description %}
Yeni tip çekme metodu
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-path-parameters %}
{% api-method-parameter name="token" type="string" required=true %}
🔒 Login token'ı
{% endapi-method-parameter %}
{% endapi-method-path-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
✔️ Başarı durumu
{% endapi-method-response-example-description %}

```javascript
{
    "code": 200,
    "message": "Tip fetch in successfully",
    "data": "Tip2"
}
-----------------------------------------------
{
    "code": 200,
    "message": "All tips are seen",
    "data": null
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=503 %}
{% api-method-response-example-description %}
✖️ Veri tabanı haatsı durumu 
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



