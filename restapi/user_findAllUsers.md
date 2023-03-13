## User

UserController dostarcza metody zwiazane z uzytkownikami.

### findAll()

findAll() zwraca liste z wszystkimi uzytkownikami.
Wymagana rola : manager lub admin.

#### Przyklad zadania:


`GET /users HTTP/1.1`  
`Accept: application/json, text/plain, */*`  
`Accept-Encoding: gzip, deflate, br`  
`Accept-Language: pl-PL,pl;q=0.9`  
`Connection: keep-alive`  
`Content-Type: application/json`  
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

`[{"uuid":"d499f955-4285-11ea-91b6-0242ac150002","internalId":"4321","firstName":"Maciej","lastName":"Mitura","email":"m.mitura@be-tse.com","active":true,"role":"CONSULTANT","country":"Poland","status":"APPROVED"},{"uuid":"d49b8a3b-4285-11ea-91b6-0242ac150002","internalId":"1234","firstName":"Bartosz","lastName":"Was","email":"b.was@be-tse.com","active":true,"role":"MANAGER","country":"Poland","status":"APPROVED"},{"uuid":"658dab90-ed68-4c01-886e-4ec7d34b0b56","internalId":"6573","firstName":"Grzegorz","lastName":"Kedzierski","email":"g.kedzierski@be-tse.it","active":true,"role":"MANAGER","country":"Poland","status":"APPROVED"},{"uuid":"5c578189-fc7b-47c2-9915-68dad34b5cd5","internalId":"9873","firstName":"Renata","lastName":"Widynska","email":"r.widynska@be-tse.com","active":true,"role":"CONSULTANT","country":"Poland","status":"APPROVED"},{"uuid":"d49b8a3b-4285-11ea-91b6-0242ac150009","internalId":"7777","firstName":"Kamil","lastName":"Dylewski","email":"k.dylewski@be-tse.com","active":true,"role":"CONSULTANT","country":"Poland","status":"APPROVED"},{"uuid":"480ee9dc-7824-11ea-bc55-0242ac130003","internalId":"3475","firstName":"Dorota","lastName":"Dabrowska-Kowalska","email":"d.Dabrowska-Kowalska@be-tse.com","active":true,"role":"ADMIN","country":"Poland","status":"APPROVED"},{"uuid":"367b2186-7824-11ea-bc55-0242ac130003","internalId":"9342","firstName":"Marta","lastName":"Czarnecka","email":"m.czarnecka@be-tse.com","active":true,"role":"ADMIN","country":"Poland","status":"APPROVED"},{"uuid":"3020027e-780d-4447-9421-89f5399a0c7d","internalId":"9821","firstName":"Olena","lastName":"Kuzmenko","email":"o.kuzmenko@be-tse.com","active":true,"role":"MANAGER","country":"Poland","status":"APPROVED"},{"uuid":"62a6b72d-7f12-4622-bef3-6718d6aca49d","internalId":"9112","firstName":"Jakub","lastName":"Karaszkiewicz","email":"j.karaszkiewicz@be-tse.com","active":true,"role":"MANAGER","country":"Poland","status":"APPROVED"},{"uuid":"f7822944-78bd-11ea-bc55-0242ac130003","internalId":"9721","firstName":"Jon","lastName":"Doe","email":"j.doe@be-tse.com","active":true,"role":"CONSULTANT","country":"Poland","status":"APPROVED"},{"uuid":"81ec151e-c4a0-40f6-a84e-a8717e441e80","internalId":"1111","firstName":"Jane","lastName":"Doe","email":"jn.doe@be-tse.com","active":true,"role":"CONSULTANT","country":"Poland","status":"APPROVED"},{"uuid":"7f58da09-9583-47be-9ddb-aad5e2a58fb4","internalId":"10333","firstName":"Vitalii","lastName":"Kovalenko","email":"v.kovalenko@be-tse.com","active":true,"role":"MANAGER","country":"Poland","status":"APPROVED"},{"uuid":"28dcbd9c-bc1d-11ed-afa1-0242ac120002","internalId":"666","firstName":"Mateusz","lastName":"Olszanka","email":"m.olszanka@be-tse.com","active":true,"role":"MANAGER","country":"Poland","status":"APPROVED"}]`

