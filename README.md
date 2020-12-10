# Node Auth

Template for Node refresh token login.

## Installation:

**1. Pull Git Repo**

```bash
git pull https://github.com/shashank23p/node-auth
```

**2. Install dependencies**

```bash
npm install
```

**3. Creating MongoDb**<br>
create a mongo instance and create collection with name **_users_** and insert a dummy admin user data provided below

```json
{
  "groups": ["admin"],
  "is_admin": true,
  "name": "admin",
  "email": "admin@admin.com",
  "password": "$2a$10$p3uvFJkPVJ.hsOaU7o2FDeCyQZLi4LqkHCvk5u2oksWNzYlzOmyhy",
  "date": {
    "$date": "2020-07-24T23:01:01.465Z"
  }
}
```

It will create admin user with following login credentials

```
email:"admin@admin.com"
password:"passowrd"
```

**4. Creating Environment variables**<br>
Create file with name **_.env_** in root folder and add following details

```bash
DB_CONNECTION= mongoConnectionString
TOKEN_SEC= authTokenSecret
TOKEN_EXPIRY=10m // token expiration_time
REFRESH_SEC= refreshTokenSecret  //must be diffent from TOKEN_SEC
```

you can use following command to genrate tokens in node

```bash
node
crypto.randomBytes(64).toString('hex');

```

**5. Running developer servers**<br>
run dev server. Node server will start on port 5000.

```bash
npm start
```
