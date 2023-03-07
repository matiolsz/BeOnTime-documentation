
## Departament

Departament jest zlozony z projektow oraz managerow.  
Wszystkie operacje wykonywane na departamentach wymagaja roli **admin**.  

### update()

update() jest uzywana do tworzenia departamentu.

|Attribute|	Type|	Required|	Description|
|---|---|---|---|
| departmentDTO | DepartmentDTO | yes | @RequestBody - Department object |
| departmentUuid | UUID | yes | Department UUID, ktory chcemy zmienic |

#### Przyklad zadania:

`PUT /departments/5c29621e-693c-4e73-a88d-30480b8cbb19 HTTP/1.1`  
`Accept: application/json, text/plain, */*`  
`Accept-Encoding: gzip, deflate, br`  
`Accept-Language: pl-PL,pl;q=0.9,en-US;q=0.8,en;q=0.7`  
`Connection: keep-alive`  
`Cookie: country=poland;`   
`bot-gdpr-consent=true; `  
`msal.idtoken=eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImtpZCI6Ii1LSTNROW5OUjdiUm9meG1lWm9YcWJIWkdldyJ9.eyJhdWQiOiI2MmVkOTBmYi0zYzA5LTRiZjMtYWMwYy1iNzU4NDYxZGE3MGUiLCJpc3MiOiJodHRwczovL2xvZ2luLm1pY3Jvc29mdG9ubGluZS5jb20vMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhL3YyLjAiLCJpYXQiOjE2NzgxODQzMjgsIm5iZiI6MTY3ODE4NDMyOCwiZXhwIjoxNjc4MTg4MjI4LCJhaW8iOiJBVFFBeS84VEFBQUFjK1ZZMW9PL0ZuL3pDWjdjamUxZ0RaZkFaYkxpMWgxb2x6cjRCaW1VOUNlemVzOWJjMnVFYThoVXFtbkt4RW1KIiwiZW1haWwiOiJtLm9sc3phbmthQGJlLXRzZS5jb20iLCJuYW1lIjoiTWF0ZXVzeiBPbHN6YW5rYSIsIm5vbmNlIjoiMTk3OWFkZTUtMTVkYy00ZTYzLWI4M2QtNmYyMTcxNDEzZDkxIiwib2lkIjoiNGI1NDk5OGUtY2M3NS00MjVhLWFlMjYtZjgxYzQ4MDg2ZTc2IiwicHJlZmVycmVkX3VzZXJuYW1lIjoibS5vbHN6YW5rYUBiZS10c2UuY29tIiwicmgiOiIwLkFZSUFOSGVvRzMtSDEwR2dwdGJ0ZFZ1UC12dVE3V0lKUFBOTHJBeTNXRVlkcHc2Q0FIZy4iLCJzdWIiOiJkeHFQOVhxXzRWYmhNSXlnbF90eENVQXpRZno1NGJieGF1c01GVkl2QW13IiwidGlkIjoiMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhIiwidXRpIjoiOXpfRGhhZVF5VWlDT1pHTFUxYzdBQSIsInZlciI6IjIuMCJ9.ZR5gTdW30ZsWHhylq3dmyjAY0iwsWrX17jvwWwHaPaz4Tt_B5IaAN3pPCQdvK7SlNB4IvcirTVv6egPg_0ZmGQhhwUNDqjyFrX_hcY4yBTq2ydtmKtxbh8tQvHOIuej5yPsWoXu5dsc-BWInmF3JQzDwSRXmoFc049Rh65frpEvOVXoDq_sJ2Iu3D5Y6CYRrjYKvJyJIHj2zy1SJ2tsqjEQIr5lJOdsMm1td12_AHeTyGl8NfZEYefBiA9TenQrQUUJD7TqmQRwdJISkxlMgF_DyqYZrizZIzi7rG9BocHvhmzwvDb84Sj2YxZEDBLcie1m0_sAfiRJrDWaKh8MyZA; `  
`bot-token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIyOGRjYmQ5Yy1iYzFkLTExZWQtYWZhMS0wMjQyYWMxMjAwMDIiLCJjb3VudHJ5IjoiUG9sYW5kIiwicm9sZXMiOiJBRE1JTiIsImlzcyI6Imh0dHA6Ly9sb2NhbGhvc3Q6ODA4MC8iLCJleHAiOjE2NzgyMTM0MjgsInV1aWQiOiIyOGRjYmQ5Yy1iYzFkLTExZWQtYWZhMS0wMjQyYWMxMjAwMDIiLCJpYXQiOjE2NzgxODQ2Mjh9.8O50t9r_QD5SXAtMyAkrnUpolwy8ACRXlZAedcelYik0jCDbr8_jsvUdl8F_DQ77zQn0owXbY7xbvoNICiT3Aw`  
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

#### Przyklad odpowiedzi:

`brak`
