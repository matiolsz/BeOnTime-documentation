## Project

Projekty naleza do danego departamentu. Sa importowane do BeOnTime przez integracje z Salesforcem oraz tworzone recznie.

### edit()

edit() jest uzywana w celu edycji projektu. Wymagana rola: admin lub manager.

|Attribute|	Type|	Required|	Description|
|---|---|---|---|
| uuid | UUID | yes | @PathVariable - UUID of project we want to edit |
| projectDTO | ProjectDTO | yes | @RequestBody - Project object |

#### Przyklad zadania:

`PUT /projects/ada8c53c-a167-11ed-a8fc-0242ac120002 HTTP/1.`  
`Accept: application/json, text/plain, */*`  
`Accept-Encoding: gzip, deflate, br`  
`Accept-Language: pl-PL,pl;q=0.9,en-US;q=0.8,en;q=0.7`  
`Connection: keep-alive`  
`Content-Type: application/json`  
`Cookie: country=poland;` 
`msal.idtoken=eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImtpZCI6Ii1LSTNROW5OUjdiUm9meG1lWm9YcWJIWkdldyJ9.eyJhdWQiOiI2MmVkOTBmYi0zYzA5LTRiZjMtYWMwYy1iNzU4NDYxZGE3MGUiLCJpc3MiOiJodHRwczovL2xvZ2luLm1pY3Jvc29mdG9ubGluZS5jb20vMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhL3YyLjAiLCJpYXQiOjE2NzgzNTE2OTEsIm5iZiI6MTY3ODM1MTY5MSwiZXhwIjoxNjc4MzU1NTkxLCJhaW8iOiJBVFFBeS84VEFBQUF2aHBsaGFzT1pIT1J4by9DdG41eFlIVE4yaEl1eEhzZys0TXUxRmFSSDZUU1ZNZmY2bW5pNzRwVnFjNUhBQmxEIiwiZW1haWwiOiJtLm9sc3phbmthQGJlLXRzZS5jb20iLCJuYW1lIjoiTWF0ZXVzeiBPbHN6YW5rYSIsIm5vbmNlIjoiYmJmYjNkOWUtNzMxMi00YzM1LWExYTAtMzQ4ZmRiYzgyMGMyIiwib2lkIjoiNGI1NDk5OGUtY2M3NS00MjVhLWFlMjYtZjgxYzQ4MDg2ZTc2IiwicHJlZmVycmVkX3VzZXJuYW1lIjoibS5vbHN6YW5rYUBiZS10c2UuY29tIiwicmgiOiIwLkFZSUFOSGVvRzMtSDEwR2dwdGJ0ZFZ1UC12dVE3V0lKUFBOTHJBeTNXRVlkcHc2Q0FIZy4iLCJzdWIiOiJkeHFQOVhxXzRWYmhNSXlnbF90eENVQXpRZno1NGJieGF1c01GVkl2QW13IiwidGlkIjoiMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhIiwidXRpIjoiX3FXaE5YVWNTVU93NjB3MTZZVi1BQSIsInZlciI6IjIuMCJ9.aPbRfIRBvfkvNyCbzZOUd1kwMRiozBmtEjJNp3Bi0sR6OK4T_xSIdoegW3DFsJzrpjguKEnH5K8JkLv9AVanon3sJucBQKowhBGo4x7z5Wn5r_jzt_LkTtsUHxOOhRcxEYRkK58Bjfa70kXv7GZ4wqEHa5OP8Baxxt_7sflDdRwlV5Hn-_TV90Ugr7FqWODDegcHQsiyCHcOJSZp0f1MWKhYDxZ8xp_Rp5ENXHhB3O4CCiU5WGqN9ER2OAOD4RKw2q4Xi6MMktWCT-t7qvKez7n06byooRLBA_Bgxx4CF_97LcmgMTbTLW8OInO5O2H2EIiphpxtm0AIVzCxTHNWVA;`  
`bot-token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIyOGRjYmQ5Yy1iYzFkLTExZWQtYWZhMS0wMjQyYWMxMjAwMDIiLCJjb3VudHJ5IjoiUG9sYW5kIiwicm9sZXMiOiJBRE1JTiIsImlzcyI6Imh0dHA6Ly9sb2NhbGhvc3Q6ODA4MC8iLCJleHAiOjE2NzgzODA3OTIsInV1aWQiOiIyOGRjYmQ5Yy1iYzFkLTExZWQtYWZhMS0wMjQyYWMxMjAwMDIiLCJpYXQiOjE2NzgzNTE5OTJ9.k-3T8VL_zEsI2G8Ri2ElZhs4EUJN0O9I-hmrICe0TvtDhEIc0MbO6NTfukGSG8el_asocNYCSAROSp9L0pPFuw; bot-gdpr-consent=true`  
`Host: localhost:8080`  
`Origin: http://localhost:4200`  
`Referer: http://localhost:4200/`  
`Sec-Fetch-Dest: empty`  
`Sec-Fetch-Mode: cors`  
`Sec-Fetch-Site: same-site`  
`User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/110.0.0.0 Safari/537.36`  
`sec-ch-ua: "Chromium";v="110", "Not A(Brand";v="24", "Google Chrome";v="110"`  
`sec-ch-ua-mobile: ?0`  
`sec-ch-ua-platform: "Windows"`  

#### Przyklad body:

`{`  
	`"uuid": "ada8c53c-a167-11ed-a8fc-0242ac120002",`  
	`"name": "testowy",`  
	`"mbmCode": "f323",`  
	`"epvCode": "f23f32",`  
    `"capacity": "0"`  
`}`

#### Przyklad odpowiedzi:

`{`  
	`"uuid": "ada8c53c-a167-11ed-a8fc-0242ac120002",`  
	`"name": "testowy",`  
	`"mbmCode": "f323",`  
	`"epvCode": "f23f32",`  
    `"capacity": "100000"`  
`}`
