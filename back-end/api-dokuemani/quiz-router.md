# 📃 Quiz Router

## 🔗 URL

```text
https://cocukasistan.herokuapp.com/
```

{% api-method method="get" host="URL" path="/quiz/getCategories" %}
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
            "name": "Hayvanlar",
            "isAllSolved": 1
        },
        {
            "id": 2,
            "name": "Meyveler",
            "isAllSolved": 0
        },
        {
            "id": 3,
            "name": "Sebzeler",
            "isAllSolved": 0
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

{% api-method method="get" host="URL" path="/quiz/getById?quiz\_id=<quiz\_id>" %}
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
// URL/quiz/getById?quiz_id=1
{
    "code": 200,
    "message": "Quiz fetched successfully",
    "data": {
        "quiz_id": 1,
        "quiz_title": "İlk Quiz",
        "questions": [
            {
                "question_content": "Soru",
                "true_option": 1,
                "options": [
                    "Seçenek1",
                    "Seçenek2",
                    "Seçenek3"
                ]
            },
            {
                "question_content": "Başka Soru",
                "true_option": 3,
                "options": [
                    "Seçenek1",
                    "Seçenek2",
                    "Seçenek3"
                ]
            },
            {
                "question_content": "Bir soru",
                "true_option": 1,
                "options": [
                    "Seçenek1",
                    "Seçenek2",
                    "Seçenek3"
                ]
            }
        ]
    }
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=404 %}
{% api-method-response-example-description %}
🔸 Quiz bulunamadı hatası
{% endapi-method-response-example-description %}

```javascript
{
    "code": 404,
    "message": "Quiz not found"
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=503 %}
{% api-method-response-example-description %}
🗃️ Veri tabanı hatası
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

{% api-method method="get" host="URL/" path="getByCategory?category\_id=<category\_id>" %}
{% api-method-summary %}
🧮 GetByCategory
{% endapi-method-summary %}

{% api-method-description %}
🗃️ Gönderilen `category_id` parametresine göre ilgili quizleri çekme metodu  
👩‍🚀 isSolved alanı ile kullanıcının çözüp çözmediği belirtilir  
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}
🔏 Login token'ı
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-query-parameters %}
{% api-method-parameter name="caetgory\_id" type="integer" required=true %}
🆔 İstenen kategorinin ID'si
{% endapi-method-parameter %}
{% endapi-method-query-parameters %}
{% endapi-method-request %}

{% api-method-response %}
{% api-method-response-example httpCode=200 %}
{% api-method-response-example-description %}
✔️ Başarı durumu
{% endapi-method-response-example-description %}

```javascript
{
  "code": 200,
  "message": "Quizes fetched successfully",
  "data": [
    {
      "quiz_id": 1,
      "quiz_title": "İlk Quiz",
      "isSolved": 0
    },
    {
      "quiz_id": 3,
      "quiz_title": "Üçüncü Quiz",
      "isSolved": 0
    }
  ]
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=503 %}
{% api-method-response-example-description %}
✖️ Veri tabanı hatası oluşma durumu
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

{% api-method method="post" host="URL" path="/quiz/solvedQuiz" %}
{% api-method-summary %}
✔️ SolvedQuiz
{% endapi-method-summary %}

{% api-method-description %}
- 🗃️ Bir quiz çözüldükten sonra veritabanında kayda alma metodu  
- 🚀 Bu metod, yeni kayıt eklemek ve önceden eklenen kaydın skorunu güncellemek için kullanılmakta 
{% endapi-method-description %}

{% api-method-spec %}
{% api-method-request %}
{% api-method-headers %}
{% api-method-parameter name="token" type="string" required=true %}
🔏 Login token'ı
{% endapi-method-parameter %}
{% endapi-method-headers %}

{% api-method-body-parameters %}
{% api-method-parameter name="quiz\_score" type="integer" required=true %}
🔢 Quizin skoru
{% endapi-method-parameter %}

{% api-method-parameter name="quiz\_id" type="integer" required=true %}
🆔 Çözülmüş quizin ID'si
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
    "message": "Quiz sent successfully",
    "data": null
}
```
{% endapi-method-response-example %}

{% api-method-response-example httpCode=503 %}
{% api-method-response-example-description %}
✖️ Veri tabanı hatası oluşma durumu
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

