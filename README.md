# khamini
- Swagger : [docs](https://abdelrhman-arfat.github.io/Kahmini-docs/)

Base URLs:

# Authentication

- HTTP Authentication, scheme: bearer

# Auth

## POST Login By Phone

POST /auth/login

> Body Parameters

```yaml
login_type: otp
phone: "50000000"
otp: "000000"
```

### Params

| Name         | Location | Type   | Required | Description |
| ------------ | -------- | ------ | -------- | ----------- |
| body         | body     | object | no       | none        |
| » login_type | body     | string | no       | none        |
| » phone      | body     | string | no       | none        |
| » otp        | body     | string | no       | none        |

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "تم تسجيل الدخول بنجاح",
    "code": 200,
    "data": {
        "user": {
            "id": 1175,
            "name": "Abdo",
            "phone": "50000000",
            "phone_verified_at": null,
            "email": "abdo@gmail.com",
            "email_verified_at": null,
            "image": null,
            "address": null,
            "last_login_at": "2025-12-16T09:57:07.000000Z",
            "status": "active",
            "deleted_at": null,
            "created_at": "2025-12-16T09:18:54.000000Z",
            "updated_at": "2025-12-16T09:57:07.000000Z",
            "auth_otp": {
                "id": 5,
                "user_id": 1175,
                "otp": "000000",
                "expires_at": "2025-12-16T09:59:40.000000Z",
                "created_at": "2025-12-16T09:56:40.000000Z",
                "updated_at": "2025-12-16T09:56:40.000000Z"
            }
        },
        "token": "6|knXHmrYGKPzOAwopCE14cjRHBotjW6hLuzJHLov492d1dea7"
    },
    "meta_data": []
}
```

### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none        | Inline      |

### Responses Data Schema

HTTP Status Code **200**

| Name                  | Type     | Required | Restrictions | Title | description |
| --------------------- | -------- | -------- | ------------ | ----- | ----------- |
| » success             | boolean  | true     | none         |       | none        |
| » message             | string   | true     | none         |       | none        |
| » code                | integer  | true     | none         |       | none        |
| » data                | object   | true     | none         |       | none        |
| »» user               | object   | true     | none         |       | none        |
| »»» id                | integer  | true     | none         |       | none        |
| »»» name              | string   | true     | none         |       | none        |
| »»» phone             | string   | true     | none         |       | none        |
| »»» phone_verified_at | null     | true     | none         |       | none        |
| »»» email             | string   | true     | none         |       | none        |
| »»» email_verified_at | null     | true     | none         |       | none        |
| »»» image             | null     | true     | none         |       | none        |
| »»» address           | null     | true     | none         |       | none        |
| »»» last_login_at     | string   | true     | none         |       | none        |
| »»» status            | string   | true     | none         |       | none        |
| »»» deleted_at        | null     | true     | none         |       | none        |
| »»» created_at        | string   | true     | none         |       | none        |
| »»» updated_at        | string   | true     | none         |       | none        |
| »»» auth_otp          | object   | true     | none         |       | none        |
| »»»» id               | integer  | true     | none         |       | none        |
| »»»» user_id          | integer  | true     | none         |       | none        |
| »»»» otp              | string   | true     | none         |       | none        |
| »»»» expires_at       | string   | true     | none         |       | none        |
| »»»» created_at       | string   | true     | none         |       | none        |
| »»»» updated_at       | string   | true     | none         |       | none        |
| »» token              | string   | true     | none         |       | none        |
| » meta_data           | [string] | true     | none         |       | none        |

## POST Create new account

POST /auth/register

> Body Parameters

```yaml
name: Abdo
email: abdo@khamini.com
password: password
password_confirmation: password
phone: "50000001"
```

### Params

| Name                    | Location | Type   | Required | Description |
| ----------------------- | -------- | ------ | -------- | ----------- |
| Accept-Language         | header   | string | no       | none        |
| body                    | body     | object | no       | none        |
| » name                  | body     | string | no       | none        |
| » email                 | body     | string | no       | none        |
| » password              | body     | string | no       | none        |
| » password_confirmation | body     | string | no       | none        |
| » phone                 | body     | string | no       | none        |

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "تم إنشاء المستخدم بنجاح",
    "code": 201,
    "data": {
        "name": "Abdo",
        "email": "abdo@gmail.com",
        "phone": "50000000",
        "updated_at": "2025-12-16T09:18:54.000000Z",
        "created_at": "2025-12-16T09:18:54.000000Z",
        "id": 1175
    },
    "meta_data": []
}
```

> 422 Response

```json
{
    "success": false,
    "message": "البريد الإلكتروني مستخدم بالفعل",
    "code": 422,
    "data": null,
    "meta_data": []
}
```

### Responses

| HTTP Status Code | Meaning                                                                  | Description | Data schema |
| ---------------- | ------------------------------------------------------------------------ | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1)                  | none        | Inline      |
| 422              | [Unprocessable Entity](https://tools.ietf.org/html/rfc2518#section-10.3) | none        | Inline      |

### Responses Data Schema

HTTP Status Code **200**

| Name          | Type     | Required | Restrictions | Title | description |
| ------------- | -------- | -------- | ------------ | ----- | ----------- |
| » success     | boolean  | true     | none         |       | none        |
| » message     | string   | true     | none         |       | none        |
| » code        | integer  | true     | none         |       | none        |
| » data        | object   | true     | none         |       | none        |
| »» name       | string   | true     | none         |       | none        |
| »» email      | string   | true     | none         |       | none        |
| »» phone      | string   | true     | none         |       | none        |
| »» updated_at | string   | true     | none         |       | none        |
| »» created_at | string   | true     | none         |       | none        |
| »» id         | integer  | true     | none         |       | none        |
| » meta_data   | [string] | true     | none         |       | none        |

HTTP Status Code **422**

| Name        | Type     | Required | Restrictions | Title | description |
| ----------- | -------- | -------- | ------------ | ----- | ----------- |
| » success   | boolean  | true     | none         |       | none        |
| » message   | string   | true     | none         |       | none        |
| » code      | integer  | true     | none         |       | none        |
| » data      | null     | true     | none         |       | none        |
| » meta_data | [string] | true     | none         |       | none        |

## POST Generate Login OTP

POST /auth/otp/generate

> Body Parameters

```yaml
phone: "50000000"
```

### Params

| Name    | Location | Type   | Required | Description |
| ------- | -------- | ------ | -------- | ----------- |
| body    | body     | object | no       | none        |
| » phone | body     | string | no       | none        |

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "تم انشاء رمز التحقق ينجاح",
    "code": 200,
    "data": {
        "expires_at": "2025-12-16T09:45:47.000000Z"
    },
    "meta_data": []
}
```

### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none        | Inline      |

### Responses Data Schema

HTTP Status Code **200**

| Name          | Type     | Required | Restrictions | Title | description |
| ------------- | -------- | -------- | ------------ | ----- | ----------- |
| » success     | boolean  | true     | none         |       | none        |
| » message     | string   | true     | none         |       | none        |
| » code        | integer  | true     | none         |       | none        |
| » data        | object   | true     | none         |       | none        |
| »» expires_at | string   | true     | none         |       | none        |
| » meta_data   | [string] | true     | none         |       | none        |

## POST Verifiy OPT

POST /auth/otp/verify

> Body Parameters

```yaml
phone: "50000000"
otp: "000000"
```

### Params

| Name    | Location | Type   | Required | Description |
| ------- | -------- | ------ | -------- | ----------- |
| body    | body     | object | no       | none        |
| » phone | body     | string | no       | none        |
| » otp   | body     | string | no       | none        |

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "تم التحقق من رمز التحقق بنجاح",
    "code": 200,
    "data": null,
    "meta_data": []
}
```

### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none        | Inline      |

### Responses Data Schema

HTTP Status Code **200**

| Name        | Type     | Required | Restrictions | Title | description |
| ----------- | -------- | -------- | ------------ | ----- | ----------- |
| » success   | boolean  | true     | none         |       | none        |
| » message   | string   | true     | none         |       | none        |
| » code      | integer  | true     | none         |       | none        |
| » data      | null     | true     | none         |       | none        |
| » meta_data | [string] | true     | none         |       | none        |

## GET GET User Profile Data

GET /auth/profile

> Response Examples

> 200 Response

```json
{}
```

### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none        | Inline      |

### Responses Data Schema

# Games

## PUT Assign Winner For the round

PUT /games/round/assign-winner

> Body Parameters

```json
"{\r\n    \"game_id\":,\r\n    \"round_id\":,\r\n    \"team_id\":,\r\n}"
```

### Params

| Name | Location | Type   | Required | Description |
| ---- | -------- | ------ | -------- | ----------- |
| body | body     | object | no       | none        |

> Response Examples

> 200 Response

```json
{}
```

### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none        | Inline      |

### Responses Data Schema

## POST Start new Game

POST /games/start

> Body Parameters

```json
{
    "teams": [
        {
            "team_number": 1,
            "name": "Team One",
            "point_plan": 400
        },
        {
            "team_number": 2,
            "name": "Team Two",
            "point_plan": 200
        }
    ],
    "categories_ids": [1, 2]
}
```

### Params

| Name | Location | Type   | Required | Description |
| ---- | -------- | ------ | -------- | ----------- |
| body | body     | object | no       | none        |

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "success",
    "code": 200,
    "data": {
        "name": "Team One VS Team Two",
        "status": "in_progress",
        "user_id": 1791,
        "updated_at": "2025-12-16T17:50:12.000000Z",
        "created_at": "2025-12-16T17:50:12.000000Z",
        "id": 2554,
        "teams": [
            {
                "id": 5107,
                "game_id": 2554,
                "team_number": 1,
                "name": "Team One",
                "image": null,
                "is_winner": false,
                "created_at": "2025-12-16T17:50:12.000000Z",
                "updated_at": "2025-12-16T17:50:12.000000Z"
            },
            {
                "id": 5108,
                "game_id": 2554,
                "team_number": 2,
                "name": "Team Two",
                "image": null,
                "is_winner": false,
                "created_at": "2025-12-16T17:50:12.000000Z",
                "updated_at": "2025-12-16T17:50:12.000000Z"
            }
        ],
        "rounds": [
            {
                "id": 13977,
                "game_id": 2554,
                "category_id": 1,
                "subscription_id": 24812,
                "round_number": 1,
                "created_at": "2025-12-16T17:50:12.000000Z",
                "updated_at": "2025-12-16T17:50:12.000000Z",
                "round_data": [
                    {
                        "id": 27953,
                        "round_id": 13977,
                        "team_id": 5107,
                        "point_plan": 400,
                        "status": "draw",
                        "point_earned": 0,
                        "qr_code": "https://willcreatelater/1",
                        "question_number": 0,
                        "answer_number": 0,
                        "created_at": "2025-12-16T17:50:12.000000Z",
                        "updated_at": "2025-12-16T17:50:12.000000Z"
                    },
                    {
                        "id": 27954,
                        "round_id": 13977,
                        "team_id": 5108,
                        "point_plan": 200,
                        "status": "draw",
                        "point_earned": 0,
                        "qr_code": "https://willcreatelater/2",
                        "question_number": 0,
                        "answer_number": 0,
                        "created_at": "2025-12-16T17:50:12.000000Z",
                        "updated_at": "2025-12-16T17:50:12.000000Z"
                    }
                ]
            },
            {
                "id": 13978,
                "game_id": 2554,
                "category_id": 2,
                "subscription_id": 24812,
                "round_number": 2,
                "created_at": "2025-12-16T17:50:12.000000Z",
                "updated_at": "2025-12-16T17:50:12.000000Z",
                "round_data": [
                    {
                        "id": 27955,
                        "round_id": 13978,
                        "team_id": 5107,
                        "point_plan": 400,
                        "status": "draw",
                        "point_earned": 0,
                        "qr_code": "https://willcreatelater/6",
                        "question_number": 0,
                        "answer_number": 0,
                        "created_at": "2025-12-16T17:50:12.000000Z",
                        "updated_at": "2025-12-16T17:50:12.000000Z"
                    },
                    {
                        "id": 27956,
                        "round_id": 13978,
                        "team_id": 5108,
                        "point_plan": 200,
                        "status": "draw",
                        "point_earned": 0,
                        "qr_code": "https://willcreatelater/3",
                        "question_number": 0,
                        "answer_number": 0,
                        "created_at": "2025-12-16T17:50:12.000000Z",
                        "updated_at": "2025-12-16T17:50:12.000000Z"
                    }
                ]
            }
        ]
    },
    "meta_data": []
}
```

### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none        | Inline      |

### Responses Data Schema

HTTP Status Code **200**

| Name                 | Type     | Required | Restrictions | Title | description |
| -------------------- | -------- | -------- | ------------ | ----- | ----------- |
| » success            | boolean  | true     | none         |       | none        |
| » message            | string   | true     | none         |       | none        |
| » code               | integer  | true     | none         |       | none        |
| » data               | object   | true     | none         |       | none        |
| »» name              | string   | true     | none         |       | none        |
| »» status            | string   | true     | none         |       | none        |
| »» user_id           | integer  | true     | none         |       | none        |
| »» updated_at        | string   | true     | none         |       | none        |
| »» created_at        | string   | true     | none         |       | none        |
| »» id                | integer  | true     | none         |       | none        |
| »» teams             | [object] | true     | none         |       | none        |
| »»» id               | integer  | true     | none         |       | none        |
| »»» game_id          | integer  | true     | none         |       | none        |
| »»» team_number      | integer  | true     | none         |       | none        |
| »»» name             | string   | true     | none         |       | none        |
| »»» image            | null     | true     | none         |       | none        |
| »»» is_winner        | boolean  | true     | none         |       | none        |
| »»» created_at       | string   | true     | none         |       | none        |
| »»» updated_at       | string   | true     | none         |       | none        |
| »» rounds            | [object] | true     | none         |       | none        |
| »»» id               | integer  | false    | none         |       | none        |
| »»» game_id          | integer  | false    | none         |       | none        |
| »»» category_id      | integer  | false    | none         |       | none        |
| »»» subscription_id  | integer  | false    | none         |       | none        |
| »»» round_number     | integer  | false    | none         |       | none        |
| »»» created_at       | string   | false    | none         |       | none        |
| »»» updated_at       | string   | false    | none         |       | none        |
| »»» round_data       | [object] | false    | none         |       | none        |
| »»»» id              | integer  | true     | none         |       | none        |
| »»»» round_id        | integer  | true     | none         |       | none        |
| »»»» team_id         | integer  | true     | none         |       | none        |
| »»»» point_plan      | integer  | true     | none         |       | none        |
| »»»» status          | string   | true     | none         |       | none        |
| »»»» point_earned    | integer  | true     | none         |       | none        |
| »»»» qr_code         | string   | true     | none         |       | none        |
| »»»» question_number | integer  | true     | none         |       | none        |
| »»»» answer_number   | integer  | true     | none         |       | none        |
| »»»» created_at      | string   | true     | none         |       | none        |
| »»»» updated_at      | string   | true     | none         |       | none        |
| » meta_data          | [string] | true     | none         |       | none        |

## GET GET Game Statics

GET /games/2554/statistics

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "تم جلب إحصائيات اللعبة بنجاح",
    "code": 200,
    "data": {
        "game": {
            "id": 2554,
            "name": "Team One VS Team Two",
            "status": "in_progress",
            "created_at": "2025-12-16T17:50:12.000000Z",
            "updated_at": "2025-12-16T17:50:12.000000Z"
        },
        "statistics": {
            "total_rounds": 2,
            "total_points": 300,
            "wins": 1,
            "losses": 1,
            "draws": 2
        },
        "teams": [
            {
                "team_id": 5107,
                "team_number": 1,
                "name": "Team One",
                "image": null,
                "is_winner": true,
                "total_points": 400,
                "wins": 1,
                "losses": 0,
                "draws": 1
            },
            {
                "team_id": 5108,
                "team_number": 2,
                "name": "Team Two",
                "image": null,
                "is_winner": false,
                "total_points": -100,
                "wins": 0,
                "losses": 1,
                "draws": 1
            }
        ],
        "rounds": [
            {
                "round_id": 13977,
                "round_number": 1,
                "category": {
                    "id": 1,
                    "name": "رياضة"
                },
                "teams_data": [
                    {
                        "round_data_id": 27953,
                        "team_id": 5107,
                        "team_name": "Team One",
                        "team_number": 1,
                        "point_plan": 400,
                        "point_earned": 400,
                        "status": "winner",
                        "question_number": 20,
                        "answer_number": 2,
                        "max_questions": 20,
                        "max_answers": 2
                    },
                    {
                        "round_data_id": 27954,
                        "team_id": 5108,
                        "team_name": "Team Two",
                        "team_number": 2,
                        "point_plan": 200,
                        "point_earned": -100,
                        "status": "loser",
                        "question_number": 1,
                        "answer_number": 0,
                        "max_questions": 20,
                        "max_answers": 2
                    }
                ]
            },
            {
                "round_id": 13978,
                "round_number": 2,
                "category": {
                    "id": 2,
                    "name": "ثقافة"
                },
                "teams_data": [
                    {
                        "round_data_id": 27955,
                        "team_id": 5107,
                        "team_name": "Team One",
                        "team_number": 1,
                        "point_plan": 400,
                        "point_earned": 0,
                        "status": "draw",
                        "question_number": 0,
                        "answer_number": 0,
                        "max_questions": 20,
                        "max_answers": 2
                    },
                    {
                        "round_data_id": 27956,
                        "team_id": 5108,
                        "team_name": "Team Two",
                        "team_number": 2,
                        "point_plan": 200,
                        "point_earned": 0,
                        "status": "draw",
                        "question_number": 0,
                        "answer_number": 0,
                        "max_questions": 20,
                        "max_answers": 2
                    }
                ]
            }
        ]
    },
    "meta_data": []
}
```

### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none        | Inline      |

### Responses Data Schema

HTTP Status Code **200**

| Name                 | Type     | Required | Restrictions | Title | description |
| -------------------- | -------- | -------- | ------------ | ----- | ----------- |
| » success            | boolean  | true     | none         |       | none        |
| » message            | string   | true     | none         |       | none        |
| » code               | integer  | true     | none         |       | none        |
| » data               | object   | true     | none         |       | none        |
| »» game              | object   | true     | none         |       | none        |
| »»» id               | integer  | true     | none         |       | none        |
| »»» name             | string   | true     | none         |       | none        |
| »»» status           | string   | true     | none         |       | none        |
| »»» created_at       | string   | true     | none         |       | none        |
| »»» updated_at       | string   | true     | none         |       | none        |
| »» statistics        | object   | true     | none         |       | none        |
| »»» total_rounds     | integer  | true     | none         |       | none        |
| »»» total_points     | integer  | true     | none         |       | none        |
| »»» wins             | integer  | true     | none         |       | none        |
| »»» losses           | integer  | true     | none         |       | none        |
| »»» draws            | integer  | true     | none         |       | none        |
| »» teams             | [object] | true     | none         |       | none        |
| »»» team_id          | integer  | true     | none         |       | none        |
| »»» team_number      | integer  | true     | none         |       | none        |
| »»» name             | string   | true     | none         |       | none        |
| »»» image            | null     | true     | none         |       | none        |
| »»» is_winner        | boolean  | true     | none         |       | none        |
| »»» total_points     | integer  | true     | none         |       | none        |
| »»» wins             | integer  | true     | none         |       | none        |
| »»» losses           | integer  | true     | none         |       | none        |
| »»» draws            | integer  | true     | none         |       | none        |
| »» rounds            | [object] | true     | none         |       | none        |
| »»» round_id         | integer  | true     | none         |       | none        |
| »»» round_number     | integer  | true     | none         |       | none        |
| »»» category         | object   | true     | none         |       | none        |
| »»»» id              | integer  | true     | none         |       | none        |
| »»»» name            | string   | true     | none         |       | none        |
| »»» teams_data       | [object] | true     | none         |       | none        |
| »»»» round_data_id   | integer  | true     | none         |       | none        |
| »»»» team_id         | integer  | true     | none         |       | none        |
| »»»» team_name       | string   | true     | none         |       | none        |
| »»»» team_number     | integer  | true     | none         |       | none        |
| »»»» point_plan      | integer  | true     | none         |       | none        |
| »»»» point_earned    | integer  | true     | none         |       | none        |
| »»»» status          | string   | true     | none         |       | none        |
| »»»» question_number | integer  | true     | none         |       | none        |
| »»»» answer_number   | integer  | true     | none         |       | none        |
| »»»» max_questions   | integer  | true     | none         |       | none        |
| »»»» max_answers     | integer  | true     | none         |       | none        |
| » meta_data          | [string] | true     | none         |       | none        |

# Games/round

## GET GET Round Data

GET /games/rounds/2554/13977

> Response Examples

> 200 Response

```json
{}
```

### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none        | Inline      |

### Responses Data Schema

# Games/round/round-data

## PATCH Update Round Data Score

PATCH /games/round/data/update-score

> Body Parameters

```json
{
    "game_id": 2554,
    "round_data_id": 27954,
    "action": "questions",
    "action_keys": "questions for increase question_number, answers for .... answer_number"
}
```

### Params

| Name | Location | Type   | Required | Description |
| ---- | -------- | ------ | -------- | ----------- |
| body | body     | object | no       | none        |

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "تم بنجاح",
    "code": 200,
    "data": {
        "id": 27954,
        "round_id": 13977,
        "team_id": 5108,
        "question_number": 1,
        "answer_number": 0,
        "point_earned": 0,
        "point_plan": 200,
        "ar_code": "https://willcreatelater/2",
        "can_update_questions": true,
        "can_update_answers": true
    },
    "meta_data": []
}
```

### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none        | Inline      |

### Responses Data Schema

HTTP Status Code **200**

| Name                    | Type     | Required | Restrictions | Title | description |
| ----------------------- | -------- | -------- | ------------ | ----- | ----------- |
| » success               | boolean  | true     | none         |       | none        |
| » message               | string   | true     | none         |       | none        |
| » code                  | integer  | true     | none         |       | none        |
| » data                  | object   | true     | none         |       | none        |
| »» id                   | integer  | true     | none         |       | none        |
| »» round_id             | integer  | true     | none         |       | none        |
| »» team_id              | integer  | true     | none         |       | none        |
| »» question_number      | integer  | true     | none         |       | none        |
| »» answer_number        | integer  | true     | none         |       | none        |
| »» point_earned         | integer  | true     | none         |       | none        |
| »» point_plan           | integer  | true     | none         |       | none        |
| »» ar_code              | string   | true     | none         |       | none        |
| »» can_update_questions | boolean  | true     | none         |       | none        |
| »» can_update_answers   | boolean  | true     | none         |       | none        |
| » meta_data             | [string] | true     | none         |       | none        |

## GET GET round data data

GET /round/data/game_id/round_data_id

> Response Examples

> 200 Response

```json
{}
```

### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none        | Inline      |

### Responses Data Schema

# Category

## GET Get All Categories

GET /categories

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "success",
    "code": 200,
    "data": [
        {
            "id": 1,
            "name": "رياضة",
            "description": "فئة خاصة بالرياضة والألعاب الرياضية",
            "image": null,
            "status": true,
            "created_at": "2025-12-11T13:10:51.000000Z",
            "updated_at": "2025-12-11T13:10:51.000000Z"
        },
        {
            "id": 2,
            "name": "ثقافة",
            "description": "فئة خاصة بالثقافة والمعرفة",
            "image": null,
            "status": true,
            "created_at": "2025-12-11T13:10:51.000000Z",
            "updated_at": "2025-12-11T13:10:51.000000Z"
        },
        {
            "id": 3,
            "name": "ترفيه",
            "description": "فئة خاصة بالترفيه والألعاب",
            "image": null,
            "status": true,
            "created_at": "2025-12-11T13:10:51.000000Z",
            "updated_at": "2025-12-11T13:10:51.000000Z"
        },
        {
            "id": 4,
            "name": "تعليم",
            "description": "فئة خاصة بالتعليم والدراسة",
            "image": null,
            "status": true,
            "created_at": "2025-12-11T13:10:51.000000Z",
            "updated_at": "2025-12-11T13:10:51.000000Z"
        }
    ],
    "meta_data": []
}
```

### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none        | Inline      |

### Responses Data Schema

HTTP Status Code **200**

| Name           | Type     | Required | Restrictions | Title | description |
| -------------- | -------- | -------- | ------------ | ----- | ----------- |
| » success      | boolean  | true     | none         |       | none        |
| » message      | string   | true     | none         |       | none        |
| » code         | integer  | true     | none         |       | none        |
| » data         | [object] | true     | none         |       | none        |
| »» id          | integer  | true     | none         |       | none        |
| »» name        | string   | true     | none         |       | none        |
| »» description | string   | true     | none         |       | none        |
| »» image       | null     | true     | none         |       | none        |
| »» status      | boolean  | true     | none         |       | none        |
| »» created_at  | string   | true     | none         |       | none        |
| »» updated_at  | string   | true     | none         |       | none        |
| » meta_data    | [string] | true     | none         |       | none        |

# Packages

## GET GET all packages

GET /packages

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "success",
    "code": 200,
    "data": [
        {
            "id": 1,
            "name": "الباقة الأساسية",
            "description": "باقة مناسبة للمبتدئين مع نقاط ومزايا أساسية",
            "image": null,
            "button_text": "اشترك الآن",
            "price": "99.99",
            "points": 500,
            "limit": 5,
            "money_png_count": 5,
            "status": true,
            "deleted_at": null,
            "created_at": "2025-12-16T17:32:44.000000Z",
            "updated_at": "2025-12-16T17:32:44.000000Z"
        },
        {
            "id": 2,
            "name": "الباقة المتوسطة",
            "description": "باقة متوسطة مع نقاط ومزايا أكثر",
            "image": null,
            "button_text": "احصل عليها",
            "price": "199.99",
            "points": 1500,
            "limit": 15,
            "money_png_count": 1,
            "status": true,
            "deleted_at": null,
            "created_at": "2025-12-16T17:32:44.000000Z",
            "updated_at": "2025-12-16T17:32:44.000000Z"
        },
        {
            "id": 3,
            "name": "الباقة المميزة",
            "description": "باقة مميزة مع نقاط ومزايا كثيرة",
            "image": null,
            "button_text": "اشترك الآن",
            "price": "299.99",
            "points": 1000,
            "limit": 10,
            "money_png_count": 20,
            "status": true,
            "deleted_at": null,
            "created_at": "2025-12-16T17:32:44.000000Z",
            "updated_at": "2025-12-16T17:32:44.000000Z"
        },
        {
            "id": 4,
            "name": "الباقة الذهبية",
            "description": "باقة ذهبية مع نقاط ومزايا غير محدودة",
            "image": null,
            "button_text": "احصل على الذهبية",
            "price": "499.99",
            "points": 800,
            "limit": 8,
            "money_png_count": 2,
            "status": true,
            "deleted_at": null,
            "created_at": "2025-12-16T17:32:44.000000Z",
            "updated_at": "2025-12-16T17:32:44.000000Z"
        }
    ],
    "meta_data": []
}
```

### Responses

| HTTP Status Code | Meaning                                                 | Description | Data schema |
| ---------------- | ------------------------------------------------------- | ----------- | ----------- |
| 200              | [OK](https://tools.ietf.org/html/rfc7231#section-6.3.1) | none        | Inline      |

### Responses Data Schema

HTTP Status Code **200**

| Name               | Type     | Required | Restrictions | Title | description |
| ------------------ | -------- | -------- | ------------ | ----- | ----------- |
| » success          | boolean  | true     | none         |       | none        |
| » message          | string   | true     | none         |       | none        |
| » code             | integer  | true     | none         |       | none        |
| » data             | [object] | true     | none         |       | none        |
| »» id              | integer  | true     | none         |       | none        |
| »» name            | string   | true     | none         |       | none        |
| »» description     | string   | true     | none         |       | none        |
| »» image           | null     | true     | none         |       | none        |
| »» button_text     | string   | true     | none         |       | none        |
| »» price           | string   | true     | none         |       | none        |
| »» points          | integer  | true     | none         |       | none        |
| »» limit           | integer  | true     | none         |       | none        |
| »» money_png_count | integer  | true     | none         |       | none        |
| »» status          | boolean  | true     | none         |       | none        |
| »» deleted_at      | null     | true     | none         |       | none        |
| »» created_at      | string   | true     | none         |       | none        |
| »» updated_at      | string   | true     | none         |       | none        |
| » meta_data        | [string] | true     | none         |       | none        |

# Data Schema
