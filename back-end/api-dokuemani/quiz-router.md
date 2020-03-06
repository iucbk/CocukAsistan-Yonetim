# 📃 Quiz Router

## 🔗 URL

```text
https://cocukasistan.azurewebsites.net
```

{% api-method method="get" host="" path="URL/quiz/getCategories" %}
{% api-method-summary %}
🎨 GetCategories
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
// URL/quiz/getCategories
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

{% api-method method="get" host="URL/quiz/" path="getById?quiz\_id=<quiz\_id>" %}
{% api-method-summary %}
🆔 GetQuizById
{% endapi-method-summary %}

{% api-method-description %}
Gönderilen `quiz_id` parametresine göre quiz çekme metodu
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}
🔏 Login token'ı
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="quiz\_id" type="integer" required=true %}
🆔 İstenen quizin ID'si
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
✔️ Başarı durumu
{% endapi-method-response-example-description %}

```javascript
// URL/quiz/getById?quiz_id=2
{
  "code": 200,
  "message": "Quiz fetched successfully",
  "data": [
    {
      "quiz_id": 2,
      "quiz_title": "İkinci Quiz",
      "question_content": "Soru metni",
      "options": "Seçenek1\\nSeçenek2\\nSeçenek3",
      "true_option": 1
    },
    {
      "quiz_id": 2,
      "quiz_title": "İkinci Quiz",
      "question_content": "Soru içeriği",
      "options": "Seçenek1\\nSeçenek2\\nSeçenek3",
      "true_option": 2
    }
  ]
}
```
{% endapi-method-response-example %}
{% endapi-method-response %}
{% endapi-method-spec %}
{% endapi-method %}

