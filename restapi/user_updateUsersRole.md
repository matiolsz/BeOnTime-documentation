## User

UserController dostarcza metody zwiazane z uzytkownikami.

### updateRole()

updateRole() zmienia role uzytkownika o danym uuid.
Wymagana rola : admin.

|Attribute|	Type|	Required|	Description|
|---|---|---|---|
| uuid | UUID | yes | @PathVariable |
| role | String | yes | @RequestParam |

#### Przyklad zadania:

`PATCH /users/d49b8a3b-4285-11ea-91b6-0242ac150002?role=CONSULTANT HTTP/1.1`  
`Accept: application/json, text/plain, */*`   
`Accept-Encoding: gzip, deflate, br`  
`Accept-Language: pl-PL,pl;q=0.9`  
`Connection: keep-alive`  
`Cookie: country=poland;`  
`bot-gdpr-consent=true; `  
`msal.idtoken=eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImtpZCI6Ii1LSTNROW5OUjdiUm9meG1lWm9YcWJIWkdldyJ9.eyJhdWQiOiI2MmVkOTBmYi0zYzA5LTRiZjMtYWMwYy1iNzU4NDYxZGE3MGUiLCJpc3MiOiJodHRwczovL2xvZ2luLm1pY3Jvc29mdG9ubGluZS5jb20vMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhL3YyLjAiLCJpYXQiOjE2Nzg0NTA1ODAsIm5iZiI6MTY3ODQ1MDU4MCwiZXhwIjoxNjc4NDU0NDgwLCJhaW8iOiJBVFFBeS84VEFBQUFUbUh3L1NubEpjQitFdmhXelZLLzBDVHVMcXErd0JUQktweW5LRGcvSlZPQVpsMTlGRW01WEpGb01ZUzh3WUVUIiwiZW1haWwiOiJtLm9sc3phbmthQGJlLXRzZS5jb20iLCJuYW1lIjoiTWF0ZXVzeiBPbHN6YW5rYSIsIm5vbmNlIjoiMWFjZDkyNDMtODIyYy00N2EyLWFkZjUtYmZiNWI0MDNhNzRlIiwib2lkIjoiNGI1NDk5OGUtY2M3NS00MjVhLWFlMjYtZjgxYzQ4MDg2ZTc2IiwicHJlZmVycmVkX3VzZXJuYW1lIjoibS5vbHN6YW5rYUBiZS10c2UuY29tIiwicmgiOiIwLkFZSUFOSGVvRzMtSDEwR2dwdGJ0ZFZ1UC12dVE3V0lKUFBOTHJBeTNXRVlkcHc2Q0FIZy4iLCJzdWIiOiJkeHFQOVhxXzRWYmhNSXlnbF90eENVQXpRZno1NGJieGF1c01GVkl2QW13IiwidGlkIjoiMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhIiwidXRpIjoiTHFNazJkbFQwRS03aVA3ODlLLVpBQSIsInZlciI6IjIuMCJ9.gfWXe96uy3A5nmz-EVdKv7_1YIIH72thNLh9myCkE3vf-TwA2z5Hzg-Jd4MdgBaA8SqocB1ld0RoqvL30tVvoaKAxi_61Mh65H2Uv_N0pPGhOmSurlo9SCwuprbRbhxjTRid444VVLDTOFsbicXfntttiMf-dJnP5up8e8BV3jSTdhRZckwikDOreS-L4lhoNkEZNUeGFwalEtDteEd7tha2ZDNhcbn0lGLLwSb7ALU1LDvC1lzJEgw6l7t1Fnkl2-cXwtjgVnGAj5qeinxMHRyadVmtXEp5pJUeznf8FUd7mjUspH3L3X0LccdazbqSRlc-W2kLruxvIpx3t2yImw; `  
`bot-token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIyOGRjYmQ5Yy1iYzFkLTExZWQtYWZhMS0wMjQyYWMxMjAwMDIiLCJjb3VudHJ5IjoiUG9sYW5kIiwicm9sZXMiOiJNQU5BR0VSIiwiaXNzIjoiaHR0cDovL2xvY2FsaG9zdDo4MDgwLyIsImV4cCI6MTY3ODQ3OTY4MSwidXVpZCI6IjI4ZGNiZDljLWJjMWQtMTFlZC1hZmExLTAyNDJhYzEyMDAwMiIsImlhdCI6MTY3ODQ1MDg4MX0.UaG6MRnJwMLYlPbqrz9JT1QBuKdAx8LN1l04X0SJunT3UjYGjRVn7ztGa_J27mTandR2_BmD1v5U3a1wAwlBHQ`  
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

#### Przyklad odpowiedzi

`{"uuid":"d49b8a3b-4285-11ea-91b6-0242ac150002","internalId":"1234","firstName":"Bartosz","lastName":"Was","email":"b.was@be-tse.com","active":true,"role":"CONSULTANT","country":"Poland","status":"APPROVED"}`
