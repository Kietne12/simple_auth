# simple_auth
*Test Basic Auth
1. Gửi request:  
GET http://localhost:3000/  
![Public Root](public/results/public_root.png)

2. Gửi request:  
GET http://localhost:3000/public  
![Public Second](public/results/public_second.png)

3. Gửi request:  
GET http://localhost:3000/secure  
![No Auth](public/results/secure_no_auth.png)

4. Trong Postman → tab Authorization  
- Chọn Basic Auth  
- Username: abc  
- Password: 123  
- Gửi request GET http://localhost:3000/secure  
![Wrong Auth](public/results/secure_wrong_auth.png)

5. Trong Postman → tab Authorization  
- Chọn Basic Auth  
- Username: admin  
- Password: 12345  
- Gửi request GET http://localhost:3000/secure  
![Success](public/results/secure_success.png)

*Test cookie_auth
1. Tạo request:
POST http://localhost:3001/login
Tab Body → chọn raw, JSON → nhập:
{
  "username": "admin",
  "password": "12345"
}
![Login Request](public/results/login.png)

2. Kiểm tra cookie trong MongoDB
![Cookie in DB](public/results/cookie_in_db.png)

3. Gửi request:
GET http://localhost:3001/profile
![Profile Response](public/results/profile.png)

4. Gửi request:
POST http://localhost:3001/logout
![Logout Response](public/results/logout.png)

5. Truy cập profile sau khi logout
GET http://localhost:3001/profile
![Profile After Logout](public/results/profile_after_logout.png)