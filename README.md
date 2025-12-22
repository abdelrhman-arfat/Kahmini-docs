# Read Docs:

- Swagger Link: (DOCS)[https://abdelrhman-arfat.github.io/Kahmini-docs/]

# khamini

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
email: abdo@khamine.com
password: password
password_confirmation: password
phone: "50000002"
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
take_type: login
```

### Params

| Name        | Location | Type   | Required | Description |
| ----------- | -------- | ------ | -------- | ----------- |
| body        | body     | object | no       | none        |
| » phone     | body     | string | no       | none        |
| » take_type | body     | string | no       | none        |

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
take_type: reset_password
```

### Params

| Name        | Location | Type   | Required | Description           |
| ----------- | -------- | ------ | -------- | --------------------- |
| body        | body     | object | no       | none                  |
| » phone     | body     | string | no       | none                  |
| » otp       | body     | string | no       | none                  |
| » take_type | body     | string | no       | login - rest_password |

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

## POST Rest password by otp

POST /auth/reset-password

> Body Parameters

```json
{
    "phone": "50000000",
    "password": "new-password",
    "password_confirmation": "new-password",
    "otp": "000000"
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
    "message": "تم إعادة تعيين كلمة المرور بنجاح",
    "code": 200,
    "data": {
        "id": 1290,
        "name": "Abdo",
        "phone": "50000000",
        "phone_verified_at": null,
        "email": "abdo@gmail.com",
        "email_verified_at": null,
        "image": null,
        "address": null,
        "last_login_at": "2025-12-16T17:38:51.000000Z",
        "status": "active",
        "deleted_at": null,
        "created_at": "2025-12-16T17:34:42.000000Z",
        "updated_at": "2025-12-18T09:38:11.000000Z",
        "subscription": null
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
| »» id                | integer  | true     | none         |       | none        |
| »» name              | string   | true     | none         |       | none        |
| »» phone             | string   | true     | none         |       | none        |
| »» phone_verified_at | null     | true     | none         |       | none        |
| »» email             | string   | true     | none         |       | none        |
| »» email_verified_at | null     | true     | none         |       | none        |
| »» image             | null     | true     | none         |       | none        |
| »» address           | null     | true     | none         |       | none        |
| »» last_login_at     | string   | true     | none         |       | none        |
| »» status            | string   | true     | none         |       | none        |
| »» deleted_at        | null     | true     | none         |       | none        |
| »» created_at        | string   | true     | none         |       | none        |
| »» updated_at        | string   | true     | none         |       | none        |
| »» subscription      | null     | true     | none         |       | none        |
| » meta_data          | [string] | true     | none         |       | none        |

## POST Rest password by old password (only for request has tokens

POST /auth/reset-password-by-password

> Body Parameters

```json
{
    "password": "password",
    "password_confirmation": "password",
    "old_password": "password"
}
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

# Games

## PUT Assign Winner For the round

PUT /games/round/assign-winner

> Body Parameters

```json
{
    "game_id": 2564,
    "round_id": 13993,
    "team_id": 5125
}
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
            "categories_ids": [1]
        },
        {
            "team_number": 2,
            "name": "Team Two",
            "categories_ids": [1]
        }
    ]
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
        "updated_at": "2025-12-18T11:49:06.000000Z",
        "created_at": "2025-12-18T11:49:06.000000Z",
        "id": 2565,
        "teams": [
            {
                "id": 5127,
                "game_id": 2565,
                "team_number": 1,
                "name": "Team One",
                "image": null,
                "is_winner": false,
                "created_at": "2025-12-18T11:49:06.000000Z",
                "updated_at": "2025-12-18T11:49:06.000000Z",
                "total_points": 0,
                "round_data": [
                    {
                        "id": 27989,
                        "round_id": 13995,
                        "team_id": 5127,
                        "point_plan": null,
                        "status": "draw",
                        "point_earned": 0,
                        "qr_code": null,
                        "question_number": 0,
                        "answer_number": 0,
                        "created_at": "2025-12-18T11:49:06.000000Z",
                        "updated_at": "2025-12-18T11:49:06.000000Z",
                        "max_answers": 2,
                        "max_questions": 20
                    },
                    {
                        "id": 27991,
                        "round_id": 13996,
                        "team_id": 5127,
                        "point_plan": null,
                        "status": "draw",
                        "point_earned": 0,
                        "qr_code": null,
                        "question_number": 0,
                        "answer_number": 0,
                        "created_at": "2025-12-18T11:49:06.000000Z",
                        "updated_at": "2025-12-18T11:49:06.000000Z",
                        "max_answers": 2,
                        "max_questions": 20
                    }
                ]
            },
            {
                "id": 5128,
                "game_id": 2565,
                "team_number": 2,
                "name": "Team Two",
                "image": null,
                "is_winner": false,
                "created_at": "2025-12-18T11:49:06.000000Z",
                "updated_at": "2025-12-18T11:49:06.000000Z",
                "total_points": 0,
                "round_data": [
                    {
                        "id": 27990,
                        "round_id": 13995,
                        "team_id": 5128,
                        "point_plan": null,
                        "status": "draw",
                        "point_earned": 0,
                        "qr_code": null,
                        "question_number": 0,
                        "answer_number": 0,
                        "created_at": "2025-12-18T11:49:06.000000Z",
                        "updated_at": "2025-12-18T11:49:06.000000Z",
                        "max_answers": 2,
                        "max_questions": 20
                    },
                    {
                        "id": 27992,
                        "round_id": 13996,
                        "team_id": 5128,
                        "point_plan": null,
                        "status": "draw",
                        "point_earned": 0,
                        "qr_code": null,
                        "question_number": 0,
                        "answer_number": 0,
                        "created_at": "2025-12-18T11:49:06.000000Z",
                        "updated_at": "2025-12-18T11:49:06.000000Z",
                        "max_answers": 2,
                        "max_questions": 20
                    }
                ]
            }
        ],
        "rounds": [
            {
                "id": 13995,
                "game_id": 2565,
                "category_id": 1,
                "subscription_id": 24814,
                "round_number": 1,
                "created_at": "2025-12-18T11:49:06.000000Z",
                "updated_at": "2025-12-18T11:49:06.000000Z",
                "round_data": [
                    {
                        "id": 27989,
                        "round_id": 13995,
                        "team_id": 5127,
                        "point_plan": null,
                        "status": "draw",
                        "point_earned": 0,
                        "qr_code": null,
                        "question_number": 0,
                        "answer_number": 0,
                        "created_at": "2025-12-18T11:49:06.000000Z",
                        "updated_at": "2025-12-18T11:49:06.000000Z",
                        "max_answers": 2,
                        "max_questions": 20
                    },
                    {
                        "id": 27990,
                        "round_id": 13995,
                        "team_id": 5128,
                        "point_plan": null,
                        "status": "draw",
                        "point_earned": 0,
                        "qr_code": null,
                        "question_number": 0,
                        "answer_number": 0,
                        "created_at": "2025-12-18T11:49:06.000000Z",
                        "updated_at": "2025-12-18T11:49:06.000000Z",
                        "max_answers": 2,
                        "max_questions": 20
                    }
                ]
            },
            {
                "id": 13996,
                "game_id": 2565,
                "category_id": 2,
                "subscription_id": 24814,
                "round_number": 2,
                "created_at": "2025-12-18T11:49:06.000000Z",
                "updated_at": "2025-12-18T11:49:06.000000Z",
                "round_data": [
                    {
                        "id": 27991,
                        "round_id": 13996,
                        "team_id": 5127,
                        "point_plan": null,
                        "status": "draw",
                        "point_earned": 0,
                        "qr_code": null,
                        "question_number": 0,
                        "answer_number": 0,
                        "created_at": "2025-12-18T11:49:06.000000Z",
                        "updated_at": "2025-12-18T11:49:06.000000Z",
                        "max_answers": 2,
                        "max_questions": 20
                    },
                    {
                        "id": 27992,
                        "round_id": 13996,
                        "team_id": 5128,
                        "point_plan": null,
                        "status": "draw",
                        "point_earned": 0,
                        "qr_code": null,
                        "question_number": 0,
                        "answer_number": 0,
                        "created_at": "2025-12-18T11:49:06.000000Z",
                        "updated_at": "2025-12-18T11:49:06.000000Z",
                        "max_answers": 2,
                        "max_questions": 20
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
| »»» total_points     | integer  | true     | none         |       | none        |
| »»» round_data       | [object] | true     | none         |       | none        |
| »»»» id              | integer  | true     | none         |       | none        |
| »»»» round_id        | integer  | true     | none         |       | none        |
| »»»» team_id         | integer  | true     | none         |       | none        |
| »»»» point_plan      | null     | true     | none         |       | none        |
| »»»» status          | string   | true     | none         |       | none        |
| »»»» point_earned    | integer  | true     | none         |       | none        |
| »»»» qr_code         | null     | true     | none         |       | none        |
| »»»» question_number | integer  | true     | none         |       | none        |
| »»»» answer_number   | integer  | true     | none         |       | none        |
| »»»» created_at      | string   | true     | none         |       | none        |
| »»»» updated_at      | string   | true     | none         |       | none        |
| »»»» max_answers     | integer  | true     | none         |       | none        |
| »»»» max_questions   | integer  | true     | none         |       | none        |
| »» rounds            | [object] | true     | none         |       | none        |
| »»» id               | integer  | true     | none         |       | none        |
| »»» game_id          | integer  | true     | none         |       | none        |
| »»» category_id      | integer  | true     | none         |       | none        |
| »»» subscription_id  | integer  | true     | none         |       | none        |
| »»» round_number     | integer  | true     | none         |       | none        |
| »»» created_at       | string   | true     | none         |       | none        |
| »»» updated_at       | string   | true     | none         |       | none        |
| »»» round_data       | [object] | true     | none         |       | none        |
| »»»» id              | integer  | true     | none         |       | none        |
| »»»» round_id        | integer  | true     | none         |       | none        |
| »»»» team_id         | integer  | true     | none         |       | none        |
| »»»» point_plan      | null     | true     | none         |       | none        |
| »»»» status          | string   | true     | none         |       | none        |
| »»»» point_earned    | integer  | true     | none         |       | none        |
| »»»» qr_code         | null     | true     | none         |       | none        |
| »»»» question_number | integer  | true     | none         |       | none        |
| »»»» answer_number   | integer  | true     | none         |       | none        |
| »»»» created_at      | string   | true     | none         |       | none        |
| »»»» updated_at      | string   | true     | none         |       | none        |
| »»»» max_answers     | integer  | true     | none         |       | none        |
| »»»» max_questions   | integer  | true     | none         |       | none        |
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

## PATCH End Game

PATCH /games/end/2554

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

## GET GET all games

GET /games

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "success",
    "code": 200,
    "data": [
        {
            "id": 2564,
            "name": "Team One VS Team Two",
            "user_id": 1791,
            "status": "in_progress",
            "created_at": "2025-12-17T10:02:54.000000Z",
            "updated_at": "2025-12-17T10:02:54.000000Z",
            "rounds": [
                {
                    "id": 13993,
                    "game_id": 2564,
                    "category_id": 1,
                    "subscription_id": 24813,
                    "round_number": 1,
                    "created_at": "2025-12-17T10:02:54.000000Z",
                    "updated_at": "2025-12-17T10:02:54.000000Z",
                    "round_data": [
                        {
                            "id": 27985,
                            "round_id": 13993,
                            "team_id": 5125,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/2",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T10:02:54.000000Z",
                            "updated_at": "2025-12-17T10:02:54.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27986,
                            "round_id": 13993,
                            "team_id": 5126,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/1",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T10:02:54.000000Z",
                            "updated_at": "2025-12-17T10:02:54.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                },
                {
                    "id": 13994,
                    "game_id": 2564,
                    "category_id": 2,
                    "subscription_id": 24813,
                    "round_number": 2,
                    "created_at": "2025-12-17T10:02:54.000000Z",
                    "updated_at": "2025-12-17T10:02:54.000000Z",
                    "round_data": [
                        {
                            "id": 27987,
                            "round_id": 13994,
                            "team_id": 5125,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/3",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T10:02:54.000000Z",
                            "updated_at": "2025-12-17T10:02:54.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27988,
                            "round_id": 13994,
                            "team_id": 5126,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/6",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T10:02:54.000000Z",
                            "updated_at": "2025-12-17T10:02:54.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                }
            ]
        },
        {
            "id": 2561,
            "name": "Team One VS Team Two",
            "user_id": 1791,
            "status": "in_progress",
            "created_at": "2025-12-17T09:48:12.000000Z",
            "updated_at": "2025-12-17T09:48:12.000000Z",
            "rounds": [
                {
                    "id": 13991,
                    "game_id": 2561,
                    "category_id": 1,
                    "subscription_id": 24813,
                    "round_number": 1,
                    "created_at": "2025-12-17T09:48:12.000000Z",
                    "updated_at": "2025-12-17T09:48:12.000000Z",
                    "round_data": [
                        {
                            "id": 27981,
                            "round_id": 13991,
                            "team_id": 5121,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/1",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:12.000000Z",
                            "updated_at": "2025-12-17T09:48:12.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27982,
                            "round_id": 13991,
                            "team_id": 5122,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/2",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:12.000000Z",
                            "updated_at": "2025-12-17T09:48:12.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                },
                {
                    "id": 13992,
                    "game_id": 2561,
                    "category_id": 2,
                    "subscription_id": 24813,
                    "round_number": 2,
                    "created_at": "2025-12-17T09:48:12.000000Z",
                    "updated_at": "2025-12-17T09:48:12.000000Z",
                    "round_data": [
                        {
                            "id": 27983,
                            "round_id": 13992,
                            "team_id": 5121,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/6",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:12.000000Z",
                            "updated_at": "2025-12-17T09:48:12.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27984,
                            "round_id": 13992,
                            "team_id": 5122,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/5",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:12.000000Z",
                            "updated_at": "2025-12-17T09:48:12.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                }
            ]
        },
        {
            "id": 2560,
            "name": "Team One VS Team Two",
            "user_id": 1791,
            "status": "in_progress",
            "created_at": "2025-12-17T09:48:10.000000Z",
            "updated_at": "2025-12-17T09:48:10.000000Z",
            "rounds": [
                {
                    "id": 13989,
                    "game_id": 2560,
                    "category_id": 1,
                    "subscription_id": 24813,
                    "round_number": 1,
                    "created_at": "2025-12-17T09:48:10.000000Z",
                    "updated_at": "2025-12-17T09:48:10.000000Z",
                    "round_data": [
                        {
                            "id": 27977,
                            "round_id": 13989,
                            "team_id": 5119,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/2",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:10.000000Z",
                            "updated_at": "2025-12-17T09:48:10.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27978,
                            "round_id": 13989,
                            "team_id": 5120,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/1",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:10.000000Z",
                            "updated_at": "2025-12-17T09:48:10.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                },
                {
                    "id": 13990,
                    "game_id": 2560,
                    "category_id": 2,
                    "subscription_id": 24813,
                    "round_number": 2,
                    "created_at": "2025-12-17T09:48:10.000000Z",
                    "updated_at": "2025-12-17T09:48:10.000000Z",
                    "round_data": [
                        {
                            "id": 27979,
                            "round_id": 13990,
                            "team_id": 5119,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/5",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:10.000000Z",
                            "updated_at": "2025-12-17T09:48:10.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27980,
                            "round_id": 13990,
                            "team_id": 5120,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/4",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:10.000000Z",
                            "updated_at": "2025-12-17T09:48:10.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                }
            ]
        },
        {
            "id": 2559,
            "name": "Team One VS Team Two",
            "user_id": 1791,
            "status": "in_progress",
            "created_at": "2025-12-17T09:48:07.000000Z",
            "updated_at": "2025-12-17T09:48:07.000000Z",
            "rounds": [
                {
                    "id": 13987,
                    "game_id": 2559,
                    "category_id": 1,
                    "subscription_id": 24813,
                    "round_number": 1,
                    "created_at": "2025-12-17T09:48:07.000000Z",
                    "updated_at": "2025-12-17T09:48:07.000000Z",
                    "round_data": [
                        {
                            "id": 27973,
                            "round_id": 13987,
                            "team_id": 5117,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/2",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:07.000000Z",
                            "updated_at": "2025-12-17T09:48:07.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27974,
                            "round_id": 13987,
                            "team_id": 5118,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/1",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:07.000000Z",
                            "updated_at": "2025-12-17T09:48:07.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                },
                {
                    "id": 13988,
                    "game_id": 2559,
                    "category_id": 2,
                    "subscription_id": 24813,
                    "round_number": 2,
                    "created_at": "2025-12-17T09:48:07.000000Z",
                    "updated_at": "2025-12-17T09:48:07.000000Z",
                    "round_data": [
                        {
                            "id": 27975,
                            "round_id": 13988,
                            "team_id": 5117,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/3",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:07.000000Z",
                            "updated_at": "2025-12-17T09:48:07.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27976,
                            "round_id": 13988,
                            "team_id": 5118,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/4",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:07.000000Z",
                            "updated_at": "2025-12-17T09:48:07.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                }
            ]
        },
        {
            "id": 2558,
            "name": "Team One VS Team Two",
            "user_id": 1791,
            "status": "in_progress",
            "created_at": "2025-12-17T09:48:04.000000Z",
            "updated_at": "2025-12-17T09:48:04.000000Z",
            "rounds": [
                {
                    "id": 13985,
                    "game_id": 2558,
                    "category_id": 1,
                    "subscription_id": 24813,
                    "round_number": 1,
                    "created_at": "2025-12-17T09:48:04.000000Z",
                    "updated_at": "2025-12-17T09:48:04.000000Z",
                    "round_data": [
                        {
                            "id": 27969,
                            "round_id": 13985,
                            "team_id": 5115,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/1",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:04.000000Z",
                            "updated_at": "2025-12-17T09:48:04.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27970,
                            "round_id": 13985,
                            "team_id": 5116,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/2",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:04.000000Z",
                            "updated_at": "2025-12-17T09:48:04.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                },
                {
                    "id": 13986,
                    "game_id": 2558,
                    "category_id": 2,
                    "subscription_id": 24813,
                    "round_number": 2,
                    "created_at": "2025-12-17T09:48:04.000000Z",
                    "updated_at": "2025-12-17T09:48:04.000000Z",
                    "round_data": [
                        {
                            "id": 27971,
                            "round_id": 13986,
                            "team_id": 5115,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/5",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:04.000000Z",
                            "updated_at": "2025-12-17T09:48:04.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27972,
                            "round_id": 13986,
                            "team_id": 5116,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/6",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:04.000000Z",
                            "updated_at": "2025-12-17T09:48:04.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                }
            ]
        },
        {
            "id": 2557,
            "name": "Team One VS Team Two",
            "user_id": 1791,
            "status": "in_progress",
            "created_at": "2025-12-17T09:48:02.000000Z",
            "updated_at": "2025-12-17T09:48:02.000000Z",
            "rounds": [
                {
                    "id": 13983,
                    "game_id": 2557,
                    "category_id": 1,
                    "subscription_id": 24813,
                    "round_number": 1,
                    "created_at": "2025-12-17T09:48:02.000000Z",
                    "updated_at": "2025-12-17T09:48:02.000000Z",
                    "round_data": [
                        {
                            "id": 27965,
                            "round_id": 13983,
                            "team_id": 5113,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/1",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:02.000000Z",
                            "updated_at": "2025-12-17T09:48:02.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27966,
                            "round_id": 13983,
                            "team_id": 5114,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/2",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:02.000000Z",
                            "updated_at": "2025-12-17T09:48:02.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                },
                {
                    "id": 13984,
                    "game_id": 2557,
                    "category_id": 2,
                    "subscription_id": 24813,
                    "round_number": 2,
                    "created_at": "2025-12-17T09:48:02.000000Z",
                    "updated_at": "2025-12-17T09:48:02.000000Z",
                    "round_data": [
                        {
                            "id": 27967,
                            "round_id": 13984,
                            "team_id": 5113,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/5",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:02.000000Z",
                            "updated_at": "2025-12-17T09:48:02.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27968,
                            "round_id": 13984,
                            "team_id": 5114,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/6",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:48:02.000000Z",
                            "updated_at": "2025-12-17T09:48:02.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                }
            ]
        },
        {
            "id": 2556,
            "name": "Team One VS Team Two",
            "user_id": 1791,
            "status": "in_progress",
            "created_at": "2025-12-17T09:47:59.000000Z",
            "updated_at": "2025-12-17T09:47:59.000000Z",
            "rounds": [
                {
                    "id": 13981,
                    "game_id": 2556,
                    "category_id": 1,
                    "subscription_id": 24813,
                    "round_number": 1,
                    "created_at": "2025-12-17T09:47:59.000000Z",
                    "updated_at": "2025-12-17T09:47:59.000000Z",
                    "round_data": [
                        {
                            "id": 27961,
                            "round_id": 13981,
                            "team_id": 5111,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/2",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:47:59.000000Z",
                            "updated_at": "2025-12-17T09:47:59.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27962,
                            "round_id": 13981,
                            "team_id": 5112,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/1",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:47:59.000000Z",
                            "updated_at": "2025-12-17T09:47:59.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                },
                {
                    "id": 13982,
                    "game_id": 2556,
                    "category_id": 2,
                    "subscription_id": 24813,
                    "round_number": 2,
                    "created_at": "2025-12-17T09:47:59.000000Z",
                    "updated_at": "2025-12-17T09:47:59.000000Z",
                    "round_data": [
                        {
                            "id": 27963,
                            "round_id": 13982,
                            "team_id": 5111,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/4",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:47:59.000000Z",
                            "updated_at": "2025-12-17T09:47:59.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27964,
                            "round_id": 13982,
                            "team_id": 5112,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/5",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:47:59.000000Z",
                            "updated_at": "2025-12-17T09:47:59.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                }
            ]
        },
        {
            "id": 2555,
            "name": "Team One VS Team Two",
            "user_id": 1791,
            "status": "in_progress",
            "created_at": "2025-12-17T09:47:30.000000Z",
            "updated_at": "2025-12-17T09:47:30.000000Z",
            "rounds": [
                {
                    "id": 13979,
                    "game_id": 2555,
                    "category_id": 1,
                    "subscription_id": 24813,
                    "round_number": 1,
                    "created_at": "2025-12-17T09:47:30.000000Z",
                    "updated_at": "2025-12-17T09:47:30.000000Z",
                    "round_data": [
                        {
                            "id": 27957,
                            "round_id": 13979,
                            "team_id": 5109,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/1",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:47:30.000000Z",
                            "updated_at": "2025-12-17T09:47:30.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27958,
                            "round_id": 13979,
                            "team_id": 5110,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/2",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:47:30.000000Z",
                            "updated_at": "2025-12-17T09:47:30.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                },
                {
                    "id": 13980,
                    "game_id": 2555,
                    "category_id": 2,
                    "subscription_id": 24813,
                    "round_number": 2,
                    "created_at": "2025-12-17T09:47:31.000000Z",
                    "updated_at": "2025-12-17T09:47:31.000000Z",
                    "round_data": [
                        {
                            "id": 27959,
                            "round_id": 13980,
                            "team_id": 5109,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/5",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:47:31.000000Z",
                            "updated_at": "2025-12-17T09:47:31.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27960,
                            "round_id": 13980,
                            "team_id": 5110,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/4",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-17T09:47:31.000000Z",
                            "updated_at": "2025-12-17T09:47:31.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                }
            ]
        },
        {
            "id": 2554,
            "name": "Team One VS Team Two",
            "user_id": 1791,
            "status": "completed",
            "created_at": "2025-12-16T17:50:12.000000Z",
            "updated_at": "2025-12-18T08:05:27.000000Z",
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
                            "status": "winner",
                            "point_earned": 400,
                            "qr_code": "https://willcreatelater/1",
                            "question_number": 20,
                            "answer_number": 2,
                            "created_at": "2025-12-16T17:50:12.000000Z",
                            "updated_at": "2025-12-17T09:22:08.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27954,
                            "round_id": 13977,
                            "team_id": 5108,
                            "point_plan": 200,
                            "status": "loser",
                            "point_earned": -100,
                            "qr_code": "https://willcreatelater/2",
                            "question_number": 1,
                            "answer_number": 0,
                            "created_at": "2025-12-16T17:50:12.000000Z",
                            "updated_at": "2025-12-17T09:22:08.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
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
                            "updated_at": "2025-12-16T17:50:12.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
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
                            "updated_at": "2025-12-16T17:50:12.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                }
            ]
        },
        {
            "id": 2553,
            "name": "Team One VS Team Two",
            "user_id": 1791,
            "status": "in_progress",
            "created_at": "2025-12-16T17:49:09.000000Z",
            "updated_at": "2025-12-16T17:49:09.000000Z",
            "rounds": [
                {
                    "id": 13975,
                    "game_id": 2553,
                    "category_id": 1,
                    "subscription_id": 24812,
                    "round_number": 1,
                    "created_at": "2025-12-16T17:49:09.000000Z",
                    "updated_at": "2025-12-16T17:49:09.000000Z",
                    "round_data": [
                        {
                            "id": 27949,
                            "round_id": 13975,
                            "team_id": 5105,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/1",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-16T17:49:09.000000Z",
                            "updated_at": "2025-12-16T17:49:09.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27950,
                            "round_id": 13975,
                            "team_id": 5106,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/2",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-16T17:49:09.000000Z",
                            "updated_at": "2025-12-16T17:49:09.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                },
                {
                    "id": 13976,
                    "game_id": 2553,
                    "category_id": 2,
                    "subscription_id": 24812,
                    "round_number": 2,
                    "created_at": "2025-12-16T17:49:09.000000Z",
                    "updated_at": "2025-12-16T17:49:09.000000Z",
                    "round_data": [
                        {
                            "id": 27951,
                            "round_id": 13976,
                            "team_id": 5105,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/3",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-16T17:49:09.000000Z",
                            "updated_at": "2025-12-16T17:49:09.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27952,
                            "round_id": 13976,
                            "team_id": 5106,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/4",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-16T17:49:09.000000Z",
                            "updated_at": "2025-12-16T17:49:09.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                }
            ]
        },
        {
            "id": 2552,
            "name": "Team One VS Team Two",
            "user_id": 1791,
            "status": "in_progress",
            "created_at": "2025-12-16T17:47:51.000000Z",
            "updated_at": "2025-12-16T17:47:51.000000Z",
            "rounds": [
                {
                    "id": 13973,
                    "game_id": 2552,
                    "category_id": 1,
                    "subscription_id": 24812,
                    "round_number": 1,
                    "created_at": "2025-12-16T17:47:51.000000Z",
                    "updated_at": "2025-12-16T17:47:51.000000Z",
                    "round_data": [
                        {
                            "id": 27945,
                            "round_id": 13973,
                            "team_id": 5103,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/2",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-16T17:47:51.000000Z",
                            "updated_at": "2025-12-16T17:47:51.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27946,
                            "round_id": 13973,
                            "team_id": 5104,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/2",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-16T17:47:51.000000Z",
                            "updated_at": "2025-12-16T17:47:51.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                },
                {
                    "id": 13974,
                    "game_id": 2552,
                    "category_id": 2,
                    "subscription_id": 24812,
                    "round_number": 2,
                    "created_at": "2025-12-16T17:47:51.000000Z",
                    "updated_at": "2025-12-16T17:47:51.000000Z",
                    "round_data": [
                        {
                            "id": 27947,
                            "round_id": 13974,
                            "team_id": 5103,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/3",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-16T17:47:51.000000Z",
                            "updated_at": "2025-12-16T17:47:51.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27948,
                            "round_id": 13974,
                            "team_id": 5104,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/3",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-16T17:47:51.000000Z",
                            "updated_at": "2025-12-16T17:47:51.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                }
            ]
        },
        {
            "id": 2551,
            "name": "Team One VS Team Two",
            "user_id": 1791,
            "status": "in_progress",
            "created_at": "2025-12-16T17:46:04.000000Z",
            "updated_at": "2025-12-16T17:46:04.000000Z",
            "rounds": [
                {
                    "id": 13972,
                    "game_id": 2551,
                    "category_id": 1,
                    "subscription_id": 24812,
                    "round_number": 1,
                    "created_at": "2025-12-16T17:46:04.000000Z",
                    "updated_at": "2025-12-16T17:46:04.000000Z",
                    "round_data": [
                        {
                            "id": 27943,
                            "round_id": 13972,
                            "team_id": 5101,
                            "point_plan": 400,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/1",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-16T17:46:04.000000Z",
                            "updated_at": "2025-12-16T17:46:04.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        },
                        {
                            "id": 27944,
                            "round_id": 13972,
                            "team_id": 5102,
                            "point_plan": 200,
                            "status": "draw",
                            "point_earned": 0,
                            "qr_code": "https://willcreatelater/1",
                            "question_number": 0,
                            "answer_number": 0,
                            "created_at": "2025-12-16T17:46:04.000000Z",
                            "updated_at": "2025-12-16T17:46:04.000000Z",
                            "max_answers": 2,
                            "max_questions": 20
                        }
                    ]
                }
            ]
        }
    ],
    "meta_data": {
        "total": 12,
        "last_page": 1,
        "current_page": 1,
        "per_page": 20,
        "links": {}
    }
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
| » data               | [object] | true     | none         |       | none        |
| »» id                | integer  | true     | none         |       | none        |
| »» name              | string   | true     | none         |       | none        |
| »» user_id           | integer  | true     | none         |       | none        |
| »» status            | string   | true     | none         |       | none        |
| »» created_at        | string   | true     | none         |       | none        |
| »» updated_at        | string   | true     | none         |       | none        |
| »» rounds            | [object] | true     | none         |       | none        |
| »»» id               | integer  | true     | none         |       | none        |
| »»» game_id          | integer  | true     | none         |       | none        |
| »»» category_id      | integer  | true     | none         |       | none        |
| »»» subscription_id  | integer  | true     | none         |       | none        |
| »»» round_number     | integer  | true     | none         |       | none        |
| »»» created_at       | string   | true     | none         |       | none        |
| »»» updated_at       | string   | true     | none         |       | none        |
| »»» round_data       | [object] | true     | none         |       | none        |
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
| »»»» max_answers     | integer  | true     | none         |       | none        |
| »»»» max_questions   | integer  | true     | none         |       | none        |
| » meta_data          | object   | true     | none         |       | none        |
| »» total             | integer  | true     | none         |       | none        |
| »» last_page         | integer  | true     | none         |       | none        |
| »» current_page      | integer  | true     | none         |       | none        |
| »» per_page          | integer  | true     | none         |       | none        |
| »» links             | object   | true     | none         |       | none        |

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

GET /round/data/game_id/27993

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

## PATCH Update Point Plan

PATCH /games/round/data/update-point-plan

> Body Parameters

```json
{
    "game_id": 2567,
    "rounds_data": [
        {
            "round_data_id": 27995,
            "point_plan": 200
        },
        {
            "round_data_id": 27996,
            "point_plan": 200
        }
    ]
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
    "message": "تم تحديث point_plan بنجاح",
    "code": 200,
    "data": {
        "id": 13994,
        "game_id": 2564,
        "round_id": null,
        "round_data": [
            {
                "id": 27987,
                "round_id": 13994,
                "team_id": 5125,
                "question_number": 0,
                "answer_number": 0,
                "point_earned": 0,
                "point_plan": 400,
                "ar_code": "https://willcreatelater/3",
                "can_update_questions": true,
                "can_update_answers": true
            },
            {
                "id": 27988,
                "round_id": 13994,
                "team_id": 5126,
                "question_number": 0,
                "answer_number": 0,
                "point_earned": 0,
                "point_plan": 200,
                "ar_code": "https://willcreatelater/6",
                "can_update_questions": true,
                "can_update_answers": true
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

| Name                     | Type     | Required | Restrictions | Title | description |
| ------------------------ | -------- | -------- | ------------ | ----- | ----------- |
| » success                | boolean  | true     | none         |       | none        |
| » message                | string   | true     | none         |       | none        |
| » code                   | integer  | true     | none         |       | none        |
| » data                   | object   | true     | none         |       | none        |
| »» id                    | integer  | true     | none         |       | none        |
| »» game_id               | integer  | true     | none         |       | none        |
| »» round_id              | null     | true     | none         |       | none        |
| »» round_data            | [object] | true     | none         |       | none        |
| »»» id                   | integer  | true     | none         |       | none        |
| »»» round_id             | integer  | true     | none         |       | none        |
| »»» team_id              | integer  | true     | none         |       | none        |
| »»» question_number      | integer  | true     | none         |       | none        |
| »»» answer_number        | integer  | true     | none         |       | none        |
| »»» point_earned         | integer  | true     | none         |       | none        |
| »»» point_plan           | integer  | true     | none         |       | none        |
| »»» ar_code              | string   | true     | none         |       | none        |
| »»» can_update_questions | boolean  | true     | none         |       | none        |
| »»» can_update_answers   | boolean  | true     | none         |       | none        |
| » meta_data              | [string] | true     | none         |       | none        |

# Games/Teams

## GET GET Team by id

GET /games/teams/5107

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "success",
    "code": 200,
    "data": {
        "id": 5107,
        "game_id": 2554,
        "team_number": 1,
        "name": "Team One",
        "image": null,
        "is_winner": true,
        "created_at": "2025-12-16T17:50:12.000000Z",
        "updated_at": "2025-12-17T09:22:08.000000Z",
        "total_points": 400,
        "round_data": [
            {
                "id": 27953,
                "round_id": 13977,
                "team_id": 5107,
                "point_plan": 400,
                "status": "winner",
                "point_earned": 400,
                "qr_code": "https://willcreatelater/1",
                "question_number": 20,
                "answer_number": 2,
                "created_at": "2025-12-16T17:50:12.000000Z",
                "updated_at": "2025-12-17T09:22:08.000000Z",
                "max_answers": 2,
                "max_questions": 20
            },
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
                "updated_at": "2025-12-16T17:50:12.000000Z",
                "max_answers": 2,
                "max_questions": 20
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

| Name                | Type     | Required | Restrictions | Title | description |
| ------------------- | -------- | -------- | ------------ | ----- | ----------- |
| » success           | boolean  | true     | none         |       | none        |
| » message           | string   | true     | none         |       | none        |
| » code              | integer  | true     | none         |       | none        |
| » data              | object   | true     | none         |       | none        |
| »» id               | integer  | true     | none         |       | none        |
| »» game_id          | integer  | true     | none         |       | none        |
| »» team_number      | integer  | true     | none         |       | none        |
| »» name             | string   | true     | none         |       | none        |
| »» image            | null     | true     | none         |       | none        |
| »» is_winner        | boolean  | true     | none         |       | none        |
| »» created_at       | string   | true     | none         |       | none        |
| »» updated_at       | string   | true     | none         |       | none        |
| »» total_points     | integer  | true     | none         |       | none        |
| »» round_data       | [object] | true     | none         |       | none        |
| »»» id              | integer  | true     | none         |       | none        |
| »»» round_id        | integer  | true     | none         |       | none        |
| »»» team_id         | integer  | true     | none         |       | none        |
| »»» point_plan      | integer  | true     | none         |       | none        |
| »»» status          | string   | true     | none         |       | none        |
| »»» point_earned    | integer  | true     | none         |       | none        |
| »»» qr_code         | string   | true     | none         |       | none        |
| »»» question_number | integer  | true     | none         |       | none        |
| »»» answer_number   | integer  | true     | none         |       | none        |
| »»» created_at      | string   | true     | none         |       | none        |
| »»» updated_at      | string   | true     | none         |       | none        |
| »»» max_answers     | integer  | true     | none         |       | none        |
| »»» max_questions   | integer  | true     | none         |       | none        |
| » meta_data         | [string] | true     | none         |       | none        |

## GET GET Game Teams Data

GET /games/teams/game/2554

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "success",
    "code": 200,
    "data": [
        {
            "id": 5107,
            "game_id": 2554,
            "team_number": 1,
            "name": "Team One",
            "image": null,
            "is_winner": true,
            "created_at": "2025-12-16T17:50:12.000000Z",
            "updated_at": "2025-12-17T09:22:08.000000Z",
            "total_points": 400,
            "round_data": [
                {
                    "id": 27953,
                    "round_id": 13977,
                    "team_id": 5107,
                    "point_plan": 400,
                    "status": "winner",
                    "point_earned": 400,
                    "qr_code": "https://willcreatelater/1",
                    "question_number": 20,
                    "answer_number": 2,
                    "created_at": "2025-12-16T17:50:12.000000Z",
                    "updated_at": "2025-12-17T09:22:08.000000Z",
                    "max_answers": 2,
                    "max_questions": 20
                },
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
                    "updated_at": "2025-12-16T17:50:12.000000Z",
                    "max_answers": 2,
                    "max_questions": 20
                }
            ]
        },
        {
            "id": 5108,
            "game_id": 2554,
            "team_number": 2,
            "name": "Team Two",
            "image": null,
            "is_winner": false,
            "created_at": "2025-12-16T17:50:12.000000Z",
            "updated_at": "2025-12-16T17:50:12.000000Z",
            "total_points": -100,
            "round_data": [
                {
                    "id": 27954,
                    "round_id": 13977,
                    "team_id": 5108,
                    "point_plan": 200,
                    "status": "loser",
                    "point_earned": -100,
                    "qr_code": "https://willcreatelater/2",
                    "question_number": 1,
                    "answer_number": 0,
                    "created_at": "2025-12-16T17:50:12.000000Z",
                    "updated_at": "2025-12-17T09:22:08.000000Z",
                    "max_answers": 2,
                    "max_questions": 20
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
                    "updated_at": "2025-12-16T17:50:12.000000Z",
                    "max_answers": 2,
                    "max_questions": 20
                }
            ]
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

| Name                | Type     | Required | Restrictions | Title | description |
| ------------------- | -------- | -------- | ------------ | ----- | ----------- |
| » success           | boolean  | true     | none         |       | none        |
| » message           | string   | true     | none         |       | none        |
| » code              | integer  | true     | none         |       | none        |
| » data              | [object] | true     | none         |       | none        |
| »» id               | integer  | true     | none         |       | none        |
| »» game_id          | integer  | true     | none         |       | none        |
| »» team_number      | integer  | true     | none         |       | none        |
| »» name             | string   | true     | none         |       | none        |
| »» image            | null     | true     | none         |       | none        |
| »» is_winner        | boolean  | true     | none         |       | none        |
| »» created_at       | string   | true     | none         |       | none        |
| »» updated_at       | string   | true     | none         |       | none        |
| »» total_points     | integer  | true     | none         |       | none        |
| »» round_data       | [object] | true     | none         |       | none        |
| »»» id              | integer  | true     | none         |       | none        |
| »»» round_id        | integer  | true     | none         |       | none        |
| »»» team_id         | integer  | true     | none         |       | none        |
| »»» point_plan      | integer  | true     | none         |       | none        |
| »»» status          | string   | true     | none         |       | none        |
| »»» point_earned    | integer  | true     | none         |       | none        |
| »»» qr_code         | string   | true     | none         |       | none        |
| »»» question_number | integer  | true     | none         |       | none        |
| »»» answer_number   | integer  | true     | none         |       | none        |
| »»» created_at      | string   | true     | none         |       | none        |
| »»» updated_at      | string   | true     | none         |       | none        |
| »»» max_answers     | integer  | true     | none         |       | none        |
| »»» max_questions   | integer  | true     | none         |       | none        |
| » meta_data         | [string] | true     | none         |       | none        |

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

# Settings

## GET GET app settings

GET /settings/application-settings

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "success",
    "code": 200,
    "data": {
        "app_name": "akadf",
        "app_description": "adf;jasdfkjasdf",
        "app_logo": "http://localhost:8000/storage/settings/694938bbe13ad.jpg"
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

| Name               | Type     | Required | Restrictions | Title | description |
| ------------------ | -------- | -------- | ------------ | ----- | ----------- |
| » success          | boolean  | true     | none         |       | none        |
| » message          | string   | true     | none         |       | none        |
| » code             | integer  | true     | none         |       | none        |
| » data             | object   | true     | none         |       | none        |
| »» app_name        | string   | true     | none         |       | none        |
| »» app_description | string   | true     | none         |       | none        |
| »» app_logo        | string   | true     | none         |       | none        |
| » meta_data        | [string] | true     | none         |       | none        |

## GET GET privcy and policy settings

GET /settings/privacy-policy

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "string",
    "code": 0,
    "data": {
        "privacy_policy": [
            {
                "title": "string",
                "content": "string"
            }
        ],
        "terms_and_conditions": [
            {
                "title": "string",
                "content": "string"
            }
        ],
        "about_us": [
            {
                "title": "string",
                "content": "string"
            }
        ]
    },
    "meta_data": [null]
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
| »» privacy_policy       | [object] | true     | none         |       | none        |
| »»» title               | string   | true     | none         |       | none        |
| »»» content             | string   | true     | none         |       | none        |
| »» terms_and_conditions | [object] | true     | none         |       | none        |
| »»» title               | string   | true     | none         |       | none        |
| »»» content             | string   | true     | none         |       | none        |
| »» about_us             | [object] | true     | none         |       | none        |
| »»» title               | string   | false    | none         |       | none        |
| »»» content             | string   | false    | none         |       | none        |
| » meta_data             | [any]    | true     | none         |       | none        |

## GET GET game terms settings

GET /settings/game-terms

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "success",
    "code": 200,
    "data": {
        "game_terms": ["dad"]
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
| »» game_terms | [string] | true     | none         |       | none        |
| » meta_data   | [string] | true     | none         |       | none        |

## GET GET Notfication settings

GET /settings/notification-messages

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "success",
    "code": 200,
    "data": {
        "not_subscribed_message": "لا يمكنك اشتراك هنا",
        "game_terms": ["dad"]
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

| Name                      | Type     | Required | Restrictions | Title | description |
| ------------------------- | -------- | -------- | ------------ | ----- | ----------- |
| » success                 | boolean  | true     | none         |       | none        |
| » message                 | string   | true     | none         |       | none        |
| » code                    | integer  | true     | none         |       | none        |
| » data                    | object   | true     | none         |       | none        |
| »» not_subscribed_message | string   | true     | none         |       | none        |
| »» game_terms             | [string] | true     | none         |       | none        |
| » meta_data               | [string] | true     | none         |       | none        |

## GET GET Social media data

GET /settings/social-settings

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "success",
    "code": 200,
    "data": {
        "facebook": "https://facebook.com",
        "snapchat": "https://facebook.com",
        "twitter": "https://facebook.com",
        "instagram": "https://facebook.com",
        "linkedin": "https://facebook.com",
        "youtube": "https://facebook.com"
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

| Name         | Type     | Required | Restrictions | Title | description |
| ------------ | -------- | -------- | ------------ | ----- | ----------- |
| » success    | boolean  | true     | none         |       | none        |
| » message    | string   | true     | none         |       | none        |
| » code       | integer  | true     | none         |       | none        |
| » data       | object   | true     | none         |       | none        |
| »» facebook  | string   | true     | none         |       | none        |
| »» snapchat  | string   | true     | none         |       | none        |
| »» twitter   | string   | true     | none         |       | none        |
| »» instagram | string   | true     | none         |       | none        |
| »» linkedin  | string   | true     | none         |       | none        |
| »» youtube   | string   | true     | none         |       | none        |
| » meta_data  | [string] | true     | none         |       | none        |

## GET GET Support settings

GET /settings/support-settings

> Response Examples

> 200 Response

```json
{
    "success": true,
    "message": "success",
    "code": 200,
    "data": {
        "support_email": "abdo@gmail.com",
        "support_phone": "01202510",
        "support_address": "Kwait"
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

| Name               | Type     | Required | Restrictions | Title | description |
| ------------------ | -------- | -------- | ------------ | ----- | ----------- |
| » success          | boolean  | true     | none         |       | none        |
| » message          | string   | true     | none         |       | none        |
| » code             | integer  | true     | none         |       | none        |
| » data             | object   | true     | none         |       | none        |
| »» support_email   | string   | true     | none         |       | none        |
| »» support_phone   | string   | true     | none         |       | none        |
| »» support_address | string   | true     | none         |       | none        |
| » meta_data        | [string] | true     | none         |       | none        |

# Data Schema
