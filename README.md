# Rocket.Chat Realtime API Guide

This README provides guidance on how to use the Rocket.Chat Realtime API to register users, log in, and retrieve room and direct message information.

## Getting Started

Before you begin, ensure that your local Rocket.Chat server is running.
Run the following command to start the server:

```bash
$ docker-compose up -d
```

Typically, the server will be running on `http://localhost:3000`.

### Prerequisites

- Rocket.Chat server running locally
- API client to make HTTP requests (e.g., Postman, cURL)

## API Endpoints

Below are the key API endpoints and their usage:

### 1. Register

**Endpoint:** `POST http://localhost:3000/api/v1/users.register`

**Payload:**

```json
{
  "username": "username",
  "name": "name",
  "pass": "pass",
  "email": "email@gmail.com"
}
```

Use this endpoint to register a new user. Replace the values in the payload with the desired username, name, password, and email.

### 2. Login

**Endpoint:** `POST http://localhost:3000/api/v1/login`

**Payload:**

```json
{
  "user": "username",
  "password": {
    "digest": "password_with_hash_sha256",
    "algorithm": "sha-256"
  }
}
```

This endpoint is used for user login. The password needs to be hashed with SHA-256. Replace `username` and `password_with_hash_sha256` with the user's credentials.

### 3. Get Room

**Endpoint:** `GET http://localhost:3000/api/v1/rooms.get`

**Required Headers:**

- `X-User-Id`
- `X-Auth-Token`

Use this endpoint to get information about rooms. The headers `X-User-Id` and `X-Auth-Token` are required, which you will receive after a successful login.

### 4. Get Direct Message

**Endpoint:** `GET http://localhost:3000/api/v1/im.messages?username=123123`

**Required Headers:**

- `X-User-Id`
- `X-Auth-Token`

This endpoint retrieves direct messages for the specified username. Include the `X-User-Id` and `X-Auth-Token` headers for authentication.

## Additional Information

For more detailed information, refer to the [official Rocket.Chat API documentation](https://developer.rocket.chat/reference/api/realtime-api).
