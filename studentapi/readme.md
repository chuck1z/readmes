# Instalasi

Clone repository ini dengan perintah berikut:.\
`git clone https://github.com/JavierZam/apiuser`

Masuk ke dalam direktori repository dengan perintah:.\
`cd apiuser`

Jalankan perintah berikut untuk menginstall dependency:.\
`npm install`

Buat file .env di root directory dan isi dengan variabel firebase sebagai berikut:<br>
<br>
FIREBASE_API_KEY=your-api-key<br>
FIREBASE_AUTH_DOMAIN=your-auth-domain<br>
FIREBASE_PROJECT_ID=your-project-id<br>
FIREBASE_STORAGE_BUCKET=your-storage-bucket<br>
FIREBASE_MESSAGING_SENDER_ID=your-messaging-sender-id<br>
FIREBASE_APP_ID=your-app-id

Pastikan untuk mengganti your-api-key, your-auth-domain, your-project-id, your-storage-bucket, 
your-messaging-sender-id, dan your-app-id dengan nilai yang sesuai dari akun Firebase Anda.

# Endpoints

| Method | Endpoint           | Handler                                  |
| ------ | ----------------- | ---------------------------------------- |
| POST   | /register          | registerUser()                           |
| POST   | /login             | loginUser()                              |
| GET    | /user/{uid}        | getUserData()                            |
| POST   | /logout            | logoutUser()                             |
| PUT    | /edit-profile/{uid}| editProfile()                            |


### POST /register
Mendaftarkan user baru ke dalam aplikasi. 

Request body: 
```json
{ 
  "email": "emailuser@contoh.com", 
  "password": "passworduser", 
  "phone": "081234567890" 
} 
```
Response: 

201 Created jika user berhasil didaftarkan. 

Response body:
```json
{
  "message": "User registered",
  "uid": "uiduser"
}
```

400 Bad Request jika terjadi kesalahan pada input data. 

Response body: 
```json
{
  "message": "error message"
} 
```

### POST /login
Melakukan login user ke dalam aplikasi. 

Request body:
```json
{
  "email": "emailuser@contoh.com",
  "password": "passworduser"
}
```
Response:

200 OK jika login berhasil.

Response body:
```json
{
  "uid": "uiduser",
  "email": "emailuser@contoh.com"
}
```

500 Internal Server Error jika terjadi kesalahan pada server.

### GET /user/{uid}
Mengambil informasi user berdasarkan uid.

Request parameter:

uid: uid user
Response:

200 OK jika data user ditemukan. Response body:

```json
{
  "email": "emailuser@contoh.com",
  "phone": "081234567890"
}
```
404 Not Found jika user tidak ditemukan.

500 Internal Server Error jika terjadi kesalahan pada server.

### POST /logout
Melakukan logout user dari aplikasi.

Response:

200 OK jika logout berhasil.

400 Bad Request jika terjadi kesalahan saat melakukan logout.

### PUT /edit-profile/{uid}
Mengubah informasi profil user berdasarkan uid.

Request parameter:

uid: uid user
Request body:
```json
{
  "email": "emailuserbaru@contoh.com",
  "password": "passworduserbaru",
  "phone": "081234567891",
  "currentEmail": "emailuserlama@contoh.com",
  "currentPassword": "passworduserlama"
}
```
Response:

200 OK jika profil berhasil diubah.

403 Forbidden jika user tidak memiliki akses untuk mengubah profil.

500 Internal Server Error jika terjadi kesalahan pada server.