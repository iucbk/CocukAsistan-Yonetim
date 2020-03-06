# 📃 Quiz Router

## 🔗 URL

```text
https://cocukasistan.azurewebsites.net
```

## 🎨 Quiz Kategorilerini Çekme

{% api-method method="get" host="" path="URL/quiz/getCategories" %}
{% api-method-summary %}
Get Categories Method
{% endapi-method-summary %}

{% api-method-description %}
Quizlerin kategorilerini çekme metodu
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}
🔏 Login token'ı
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
  "message": "Categories fetched successfully",
  "data": [
    {
      "id": 1,
      "name": "Hayvanlar"
    },
    {
      "id": 2,
      "name": "Meyveler"
    },
    {
      "id": 3,
      "name": "Sebzeler"
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

