# 📦 Object Router

## 🔗 URL

```text
https://cocukasistan.herokuapp.com/
```

{% api-method method="get" host="URL" path="/object/getById" %}
{% api-method-summary %}
🆔 Objeyi ID ile çekme metodu 
{% endapi-method-summary %}

{% api-method-description %}

{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-body-parameters %}
{% api-method-parameter name="object\_id" type="string" required=true %}
İstenen objenin ID'si
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
  "message": "Object fetched successfully",
  "data": [
    {
      "object_id": 4,
      "name": "Bacak Sayısı",
      "value": "4 bacak"
    },
    {
      "object_id": 4,
      "name": "Tür",
      "value": "Memeliler"
    }
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=503 %}
{% api-method-response-example-description %}
🗃️ Veritabanı hatası
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

