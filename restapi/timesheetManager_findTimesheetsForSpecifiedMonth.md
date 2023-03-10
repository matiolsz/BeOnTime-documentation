## TimesheetManager

Timesheet jest to zbior Entries w danym miesiacu dla danego uzytkownika.
Entry stanowi ilosc przepracowanych godzin w danym dniu.

TimesheetManagerController zawiera zbior operacji na Timesheetach, destepnych tylko dla managera. Wymagana rola: manager.

### find()

find() zwraca liste Timesheetow dla danego miesiaca.

|Attribute|	Type|	Required|	Description|
|---|---|---|---|
| month | int | yes | @RequestParam |
| year | int | yes | @RequestParam |

#### Przyklad zadania:

`GET /manager/timesheets?month=3&year=2023 HTTP/1.1`  
`Accept: application/json, text/plain, */*`  
`Accept-Encoding: gzip, deflate, br`  
`Accept-Language: pl-PL,pl;q=0.9,en-US;q=0.8,en;q=0.7`  
`Connection: keep-alive`  
`Content-Type: application/json`  
`Cookie: country=poland;`  
`bot-gdpr-consent=true;`  
`msal.idtoken=eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImtpZCI6Ii1LSTNROW5OUjdiUm9meG1lWm9YcWJIWkdldyJ9.eyJhdWQiOiI2MmVkOTBmYi0zYzA5LTRiZjMtYWMwYy1iNzU4NDYxZGE3MGUiLCJpc3MiOiJodHRwczovL2xvZ2luLm1pY3Jvc29mdG9ubGluZS5jb20vMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhL3YyLjAiLCJpYXQiOjE2NzgzNTc1MzcsIm5iZiI6MTY3ODM1NzUzNywiZXhwIjoxNjc4MzYxNDM3LCJhaW8iOiJFMlpnWUxndG9aKzB0MlNiVm9sT2t0VFpoWkdzL0ZYWjFSZjlJc3Q1T3VmZHFXVHlUYnd0TytOTDl5ZmxKcXR1OVVpZTdwT1JBQT09IiwiZW1haWwiOiJtLm9sc3phbmthQGJlLXRzZS5jb20iLCJuYW1lIjoiTWF0ZXVzeiBPbHN6YW5rYSIsIm5vbmNlIjoiMWVjNDZmYWYtZTE0OS00OTIyLWE5ZDctNjRiMjEyZGJkOTc3Iiwib2lkIjoiNGI1NDk5OGUtY2M3NS00MjVhLWFlMjYtZjgxYzQ4MDg2ZTc2IiwicHJlZmVycmVkX3VzZXJuYW1lIjoibS5vbHN6YW5rYUBiZS10c2UuY29tIiwicmgiOiIwLkFZSUFOSGVvRzMtSDEwR2dwdGJ0ZFZ1UC12dVE3V0lKUFBOTHJBeTNXRVlkcHc2Q0FIZy4iLCJzdWIiOiJkeHFQOVhxXzRWYmhNSXlnbF90eENVQXpRZno1NGJieGF1c01GVkl2QW13IiwidGlkIjoiMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhIiwidXRpIjoiRFpTS2NkUl9GRXlQb0F4WG04TnVBQSIsInZlciI6IjIuMCJ9.OMGfNCXS8EY3qQrN0bJ2vXgHxzLnxyuA9HHCGUuvbXGxAEbvfpD1iXUQGegXKhPkG1P4Qqbxr_vwWfjVHEH0g3JdUdTAz9tJp4OzOm249um0y-GX0VlKNjIqzTw_ihKaKy02mRx3-7TEoR-qA0fcHlnswaezslRIxFFoH493UaGJB5uxUTh181HXndiUgAwtvXfKTFEZ_mRww4wOpS9iHMiQMpbNV-pAZTbtxobg_3kCZg0_gejXXbuf0TQgzQCOTWg8C7IRD32iumIEn6QUa7M3JZtajJtCPAsk_nQqRGOXYl9YTs49K6_AZeI_Hvq9V_skpe28m0TALOgIiuCHqA;`  
`bot-token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIyOGRjYmQ5Yy1iYzFkLTExZWQtYWZhMS0wMjQyYWMxMjAwMDIiLCJjb3VudHJ5IjoiUG9sYW5kIiwicm9sZXMiOiJNQU5BR0VSIiwiaXNzIjoiaHR0cDovL2xvY2FsaG9zdDo4MDgwLyIsImV4cCI6MTY3ODM4NjYzNywidXVpZCI6IjI4ZGNiZDljLWJjMWQtMTFlZC1hZmExLTAyNDJhYzEyMDAwMiIsImlhdCI6MTY3ODM1NzgzN30.DCYBG-ihKbG3aR5ooglJaFuViLhrmn6lrrzbGi3sI42f7rOyhVa5QCNsgkAorCY7ru16WYNs1HTT9mRtT75fbA`  
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

`{"expectedHours":184.0,"userTimesheets":[{"userUuid":"d49b8a3b-4285-11ea-91b6-0242ac150009","email":"k.dylewski@be-tse.com","firstName":"Kamil","lastName":"Dylewski","totalHours":0.0,"status":"NOT_CREATED"},{"userUuid":"28dcbd9c-bc1d-11ed-afa1-0242ac120002","email":"m.olszanka@be-tse.com","firstName":"Mateusz","lastName":"Olszanka","totalHours":24.0,"status":"SUBMITTED"},{"userUuid":"d499f955-4285-11ea-91b6-0242ac150002","email":"m.mitura@be-tse.com","firstName":"Maciej","lastName":"Mitura","totalHours":0.0,"status":"NOT_CREATED"},{"userUuid":"367b2186-7824-11ea-bc55-0242ac130003","email":"m.czarnecka@be-tse.com","firstName":"Marta","lastName":"Czarnecka","totalHours":0.0,"status":"NOT_CREATED"},{"userUuid":"480ee9dc-7824-11ea-bc55-0242ac130003","email":"d.Dabrowska-Kowalska@be-tse.com","firstName":"Dorota","lastName":"Dabrowska-Kowalska","totalHours":0.0,"status":"NOT_CREATED"},{"userUuid":"d49b8a3b-4285-11ea-91b6-0242ac150002","email":"b.was@be-tse.com","firstName":"Bartosz","lastName":"Was","totalHours":0.0,"status":"NOT_CREATED"}]}`