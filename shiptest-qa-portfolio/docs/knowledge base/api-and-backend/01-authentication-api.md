# Authentication API

The application uses a session cookie named `auth_session`, valid for up to 30 days. Retain it after registration or login. Successful user responses omit the password.

| Method and path | Request | Success | Other responses | Database effect |
| --- | --- | --- | --- | --- |
| POST /api/auth/register | JSON with all eight fields below | 201 `{message: "Registered successfully", user}`, sets session cookie | 400 missing or invalid input, 409 duplicate email, 500 registration failure | Insert User |
| POST /api/auth/login | `{"email":"qa@example.com","password":"QaSample123"}` | 200 `{message: "Logged in successfully", user}`, sets session cookie | 400 missing credentials, 401 incorrect credentials, 500 failure | Read User |
| POST /api/auth/logout | No body | 200 `{"message":"Logged out successfully"}`, clears cookie | Handler has no custom error response | No write |
| GET /api/auth/me | No body, session cookie | 200 `{user}` | 401 `{"error":"Unauthorized"}` | Read signed-in User |

## Registration request and validation

```json
{"email":"qa@example.com","password":"QaSample123","fullName":"Sample Tester","phone":"0501234567","country":"Saudi Arabia","city":"Riyadh","street":"Example Street","postalCode":"12345"}
```

Fields are strings. The handler requires email format and a password of at least six characters. Name and city have a two-character minimum. Street has a five-character minimum, postal code is 3–10 characters, and registration checks phone length as 10–15 characters. Email is stored lowercase and uniqueness is checked using that value.

## Shared user response object

```json
{"id":1,"email":"qa@example.com","fullName":"Sample Tester","phone":"0501234567","country":"Saudi Arabia","city":"Riyadh","street":"Example Street","postalCode":"12345","createdAt":"2026-11-18T12:00:00.000Z","updatedAt":"2026-11-18T12:00:00.000Z"}
```

QA flow. Register → call `me` with the same cookie → log out → call `me` again and expect 401.

## Sources

- [src/routes/api/auth/login/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/auth/login/%2Bserver.ts)
- [src/routes/api/auth/logout/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/auth/logout/%2Bserver.ts)
- [src/routes/api/auth/me/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/auth/me/%2Bserver.ts)
- [src/routes/api/auth/register/+server.ts](https://github.com/mohamedaabdelbaki/ship-app/blob/447c72c4b4eca87f1b4906052eecb4fdd8bd6373/src/routes/api/auth/register/%2Bserver.ts)
