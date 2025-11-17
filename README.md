## Background

Testing sanctum to use with nextjs.

## To use

http://127.0.0.1:8000/api/register

request

{
	"name": "ayam",
	"email": "ayam@mampus.com",
	"password": "password"
}

response

{
	"respose_code": 201,
	"message": "User registered successfully",
	"data": {
		"name": "ayam",
		"email": "ayam@mampus.com",
		"updated_at": "2025-11-17T00:04:01.000000Z",
		"created_at": "2025-11-17T00:04:01.000000Z",
		"id": 1
	}
}

http://127.0.0.1:8000/api/login

request

{
	"email": "ayam@mampus.com",
	"password": "password"
}

result

{
	"response_code": 200,
	"message": "Login successful",
	"data": {
		"id": 1,
		"name": "ayam",
		"email": "ayam@mampus.com",
		"email_verified_at": null,
		"created_at": "2025-11-17T00:04:01.000000Z",
		"updated_at": "2025-11-17T00:04:01.000000Z"
	},
	"token": "1|fzkLUa1kj8pHriu32A8jfaBLEJvMzYwfae4ymQr58baece43",
	"token_type": "Bearer"
}

http://127.0.0.1:8000/api/users

request 

header
Authorization : Bearer [token]

response

{
	"response_code": 200,
	"message": "Profile fetched successfully",
	"users": {
		"current_page": 1,
		"data": [
			{
				"id": 1,
				"name": "ayam",
				"email": "ayam@mampus.com",
				"email_verified_at": null,
				"created_at": "2025-11-17T00:04:01.000000Z",
				"updated_at": "2025-11-17T00:04:01.000000Z"
			}
		],
		"first_page_url": "http://127.0.0.1:8000/api/profile?page=1",
		"from": 1,
		"last_page": 1,
		"last_page_url": "http://127.0.0.1:8000/api/profile?page=1",
		"links": [
			{
				"url": null,
				"label": "&laquo; Previous",
				"page": null,
				"active": false
			},
			{
				"url": "http://127.0.0.1:8000/api/profile?page=1",
				"label": "1",
				"page": 1,
				"active": true
			},
			{
				"url": null,
				"label": "Next &raquo;",
				"page": null,
				"active": false
			}
		],
		"next_page_url": null,
		"path": "http://127.0.0.1:8000/api/profile",
		"per_page": 10,
		"prev_page_url": null,
		"to": 1,
		"total": 1
	}
}

http://127.0.0.1:8000/api/profile/{id}

request 

Authorization : Bearer [token]

response

{
	"response_code": 200,
	"message": "Profile fetched successfully",
	"user": {
		"id": 1,
		"name": "ayam",
		"email": "ayam@mampus.com",
		"email_verified_at": null,
		"created_at": "2025-11-17T00:04:01.000000Z",
		"updated_at": "2025-11-17T00:04:01.000000Z"
	}
}


http://127.0.0.1:8000/api/logout

request 

Authorization : Bearer [token]

response

{
	"response_code": 200,
	"message": "Logout successful"
}

