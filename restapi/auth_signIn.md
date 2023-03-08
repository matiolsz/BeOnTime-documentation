## Uwierzytelnianie

Najpierw uzytkownik loguje sie do azure ad, uzywajac konta z domeny be-tse.com. Azure po zalogowaniu zwraca id-token(msal id-token). Token ten jest ustawiany w cookie. Backend przechwytuje request, sprawdza msal id-token i jezeli jest poprawny, ustawia w ciasteczku jwt token o nazwie bot-token. W przypadku kiedy token jest expired zwraca 401 a token w ciasteczku jest kasowany.

Country - Przy pierwszym logowaniu uzytkownik zobowiazany jest wybrac country. Konto przechodzi w status PENDING_APPROVAL i wybor country bedzie zatwierdzone przez managera. Manager ma tez mozliwosc zmiany country. 

Na podstawie pola country, manager ma mozliwosc pobrania projektow z salesforca albo dodanie nowego projektu. ( Jest xalezne od tego czy kraj ma synchronizacje z salesforcie.)

Na podstawie country rowniez segregujemy pracownikow.

### signIn()

signIn() 

#### Przyklad zadania:

`GET /authentication/sign-in/poland HTTP/1.1`  
`Accept: application/json, text/plain, */*`  
`Accept-Encoding: gzip, deflate, br`  
`Accept-Language: pl-PL,pl;q=0.9,en-US;q=0.8,en;q=0.7`  
`Connection: keep-alive`  
`Content-Type: application/x-www-form-urlencoded; charset=UTF-8`  
`Cookie: country=poland;`  
`bot-gdpr-consent=true;`  
`msal.idtoken=eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImtpZCI6Ii1LSTNROW5OUjdiUm9meG1lWm9YcWJIWkdldyJ9.eyJhdWQiOiI2MmVkOTBmYi0zYzA5LTRiZjMtYWMwYy1iNzU4NDYxZGE3MGUiLCJpc3MiOiJodHRwczovL2xvZ2luLm1pY3Jvc29mdG9ubGluZS5jb20vMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhL3YyLjAiLCJpYXQiOjE2NzgyNzQ0NDcsIm5iZiI6MTY3ODI3NDQ0NywiZXhwIjoxNjc4Mjc4MzQ3LCJhaW8iOiJBVFFBeS84VEFBQUE2T1lXTUdPVHBEYlFRTXVkTlo3QVlzRjhnWlc1OVFwSk9OK251NGNDeUd4cU9xeVRYNlVzdUtsV3l2akE1SFZ6IiwiZW1haWwiOiJtLm9sc3phbmthQGJlLXRzZS5jb20iLCJuYW1lIjoiTWF0ZXVzeiBPbHN6YW5rYSIsIm5vbmNlIjoiOTkzZTE3MmYtYTllZS00NDcwLTk5NTUtNDg4Nzg1OThhYTIxIiwib2lkIjoiNGI1NDk5OGUtY2M3NS00MjVhLWFlMjYtZjgxYzQ4MDg2ZTc2IiwicHJlZmVycmVkX3VzZXJuYW1lIjoibS5vbHN6YW5rYUBiZS10c2UuY29tIiwicmgiOiIwLkFZSUFOSGVvRzMtSDEwR2dwdGJ0ZFZ1UC12dVE3V0lKUFBOTHJBeTNXRVlkcHc2Q0FIZy4iLCJzdWIiOiJkeHFQOVhxXzRWYmhNSXlnbF90eENVQXpRZno1NGJieGF1c01GVkl2QW13IiwidGlkIjoiMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhIiwidXRpIjoiRHdBLVFYdldyazY2Zm5tRUFVVXdBQSIsInZlciI6IjIuMCJ9.r_ab2mO749WU43zqcW9tFZna8RChay9TYKYJBXaYPTg9MFwHUFFu54C8P1v7AzmbYUbTzJplWQBaZPFqkwhYt_lenbA_6_tL97Hjtuc5-gD5WJvrNcyke4QRBDfdohSIjwaecVWgpmU7-qKL9QK4wpx2CuCNcwoJ2UpEF1VrMTNPGXu49Ry4YPnA1p8f2Ln5MCe5ulM4dcTRStsnKDXuM8mnmYXMiRZA2wLSQ3gpuHy5oQkg_htVDNwbngha7ZTXA5ro2SvyojC357KGGvjcy-9GS7wr4rU36S2zhz19DAIWSeXHBCwrAhdlSm9Ty6--Z-gWmD1gIvAXZSmRbX8rLw`  
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

`{"uuid":"28dcbd9c-bc1d-11ed-afa1-0242ac120002","firstName":"Mateusz","lastName":"Olszanka","email":"m.olszanka@be-tse.com","active":true,"role":"ADMIN","country":"Poland"}`
