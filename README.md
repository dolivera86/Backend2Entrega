Entrega Nº 1 del curso, implementando:

    Modelo de Usuario con campos: first_name, last_name, email (único), age, password (hash), cart, role (por defecto 'user').
    Encriptación de contraseña con bcrypt.
    Estrategias de Passport para autenticación JWT.
    Sistema de login que genera token JWT.
    Ruta protegida /api/sessions/current para validar token y obtener datos del usuario logueado.

Tecnologías

    Node.js
    Express
    Passport
    Passport-JWT
    JSON Web Tokens (JWT)
    bcrypt
    dotenv

Estructura

app/
├── src/
│   ├── config/
│   │   └── passport.js
│   ├── controllers/
│   │   └── session.controller.js
│   ├── models/
│   │   └── User.js
│   ├── routes/
│   │   └── sessions.router.js
│   ├── utils/
│   │   ├── generateToken.js
│   │   └── hash.js
│   └── app.js
├── .env
├── .gitignore
├── package.json
├── server.js
└── README.md


Registro de usuario

    URL: /api/sessions/register
    Método: POST
    Body (JSON):

{
  "first_name": "Ana",
  "last_name": "Gomez",
  "email": "ana@mail.com",
  "age": 28,
  "password": "123456"
}

Login

    URL: /api/sessions/login
    Método: POST
    Body (JSON):

{
  "email": "ana@mail.com",
  "password": "123456"
}

    Respuesta:

{
  "token": "<token_JWT_generado>"
}

Obtener usuario actual

    URL: /api/sessions/current
    Método: GET
    Headers:

Authorization: Bearer <token_JWT>

    Respuesta:

{
  "user": {
    "_id": 1,
    "first_name": "Ana",
    "last_name": "Gomez",
    "email": "ana@mail.com",
    "age": 28,
    "cart": null,
    "role": "user"
  }
}
