## TimesheetManager

Timesheet jest to zbior Entries w danym miesiacu dla danego uzytkownika.
Entry stanowi ilosc przepracowanych godzin w danym dniu.

TimesheetManagerController zawiera zbior operacji na Timesheetach, destepnych tylko dla managera. Wymagana rola: manager.

### findBurnout()

findBurnout() zwraca liste Burnout dla danego projektu. 

Burnout to ilosc przepracowanych dni dla danego Work Orderu.
Dzien pracy w BeOnTime trwa 8 godzin.

|Attribute|	Type|	Required|	Description|
|---|---|---|---|
| projectName | String | yes | @RequestParam |

#### Przyklad zadania:

`GET /manager/timesheets/burnout?projectName=Uniqa HTTP/1.1`  
`Accept: application/json, text/plain, */*`  
`Accept-Encoding: gzip, deflate, br`  
`Accept-Language: pl-PL,pl;q=0.9`  
`Connection: keep-alive`  
`Content-Type: application/json`  
`Cookie: country=poland;`  
`msal.idtoken=eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImtpZCI6Ii1LSTNROW5OUjdiUm9meG1lWm9YcWJIWkdldyJ9.eyJhdWQiOiI2MmVkOTBmYi0zYzA5LTRiZjMtYWMwYy1iNzU4NDYxZGE3MGUiLCJpc3MiOiJodHRwczovL2xvZ2luLm1pY3Jvc29mdG9ubGluZS5jb20vMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhL3YyLjAiLCJpYXQiOjE2Nzg0NDY2NDMsIm5iZiI6MTY3ODQ0NjY0MywiZXhwIjoxNjc4NDUwNTQzLCJhaW8iOiJBVFFBeS84VEFBQUFnSGFxeGlQcjN1U1ZiS0NjdnROM1JSZmVQWG5NcG94dE45UjEvQVVuQjJRbjVjYXdkeW9sL0NZYlBOUmZRdUU4IiwiZW1haWwiOiJtLm9sc3phbmthQGJlLXRzZS5jb20iLCJuYW1lIjoiTWF0ZXVzeiBPbHN6YW5rYSIsIm5vbmNlIjoiMWE4MjAzMjgtNjFkNy00MzczLWExMDQtNjI5MWE3N2UxNjcxIiwib2lkIjoiNGI1NDk5OGUtY2M3NS00MjVhLWFlMjYtZjgxYzQ4MDg2ZTc2IiwicHJlZmVycmVkX3VzZXJuYW1lIjoibS5vbHN6YW5rYUBiZS10c2UuY29tIiwicmgiOiIwLkFZSUFOSGVvRzMtSDEwR2dwdGJ0ZFZ1UC12dVE3V0lKUFBOTHJBeTNXRVlkcHc2Q0FIZy4iLCJzdWIiOiJkeHFQOVhxXzRWYmhNSXlnbF90eENVQXpRZno1NGJieGF1c01GVkl2QW13IiwidGlkIjoiMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhIiwidXRpIjoiY1hoTzQzV2dLVXl3TFVjQXBVR0NBQSIsInZlciI6IjIuMCJ9.pvSA4q1QG2hPprsub7kDcWg88ELxgghUkwUL8vYulBGUKUsOBtmnivlfBOjP06-slGRbwed8S6glOmhHY3D9JDO1b2M75z_FNjSbbTZsiPnFiMCdDhQR_6gPb8X1sEQkDkdzbr_g58vq284mTMst2Ayo9BO0rqWm_GrCorkJWOwuSHdgeZQD5gMI1sr8fW9_mQImnxiS9l-wV3tnXh_MSHh81-nW0jbxyeMGDGe1KEPsv6rJWWouxK84im0-TdPVIyC6z3FFsgWFufx0fkUcN62eYsDKwKoXeTGFbhpRYTzAXBEGngn_tE9pCjVu0GS-sZM9B46Gw3dk0FtaQq401w;`  
`bot-gdpr-consent=true; `  
`bot-token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIyOGRjYmQ5Yy1iYzFkLTExZWQtYWZhMS0wMjQyYWMxMjAwMDIiLCJjb3VudHJ5IjoiUG9sYW5kIiwicm9sZXMiOiJNQU5BR0VSIiwiaXNzIjoiaHR0cDovL2xvY2FsaG9zdDo4MDgwLyIsImV4cCI6MTY3ODQ3NTc0NCwidXVpZCI6IjI4ZGNiZDljLWJjMWQtMTFlZC1hZmExLTAyNDJhYzEyMDAwMiIsImlhdCI6MTY3ODQ0Njk0NH0.GLd1HFqrYcanMZCtGe1XGjM-cAhrZQj0MsJMsLedndJFj6pgy85NptO5PjWsGzkpoJjV3GSxRCfiX_HKr_6mjg`  
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

`[{"workOrderUUID":"d498df22-4285-11ea-91b6-0242ac150002","manDays":23.0},{"workOrderUUID":"760cc47a-0445-44d0-aedc-d7dd3fad7e68","manDays":3.0},{"workOrderUUID":"d498df22-4285-11ea-91b6-0242ac150003","manDays":0.0}]`

