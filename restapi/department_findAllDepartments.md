
## Departament

Department jest zlozony z projektow.  
Wszystkie operacje wykonywane na departamentach wymagaja roli **admin**.  

### findAll()

findAll() jest uzywana do pobrania listy departamentow.

#### Przyklad zadania:

`curl 'http://localhost:8080/departments'  `  
`-H 'Accept: application/json, text/plain, /'  `  
`-H 'Accept-Language: pl-PL,pl;q=0.9,en-US;q=0.8,en;q=0.7'  `  
`-H 'Connection: keep-alive'  `  
`-H 'Cookie: country=poland;   `  
`msal.idtoken=eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImtpZCI6Ii1LSTNROW5OUjdiUm9meG1lWm9YcWJIWkdldyJ9.eyJhdWQiOiI2MmVkOTBmYi0zYzA5LTRiZjMtYWMwYy1iNzU4NDYxZGE3MGUiLCJpc3MiOiJodHRwczovL2xvZ2luLm1pY3Jvc29mdG9ubGluZS5jb20vMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhL3YyLjAiLCJpYXQiOjE2NzgwOTQyMzUsIm5iZiI6MTY3ODA5NDIzNSwiZXhwIjoxNjc4MDk4MTM1LCJhaW8iOiJBVFFBeS84VEFBQUE4aGlBY2ZNSnJUYlRGdW00M3lTZ1BCSkw3MTN3R09HWGdPdlRiQ2FvcHZERjFXSVhpSnRmWm5MaWtvaStjYldUIiwiZW1haWwiOiJtLm9sc3phbmthQGJlLXRzZS5jb20iLCJuYW1lIjoiTWF0ZXVzeiBPbHN6YW5rYSIsIm5vbmNlIjoiMGIyZGE5YWUtZmE5Mi00ZWI4LWJiZmUtZDE3ZDhlNDc0NWFmIiwib2lkIjoiNGI1NDk5OGUtY2M3NS00MjVhLWFlMjYtZjgxYzQ4MDg2ZTc2IiwicHJlZmVycmVkX3VzZXJuYW1lIjoibS5vbHN6YW5rYUBiZS10c2UuY29tIiwicmgiOiIwLkFZSUFOSGVvRzMtSDEwR2dwdGJ0ZFZ1UC12dVE3V0lKUFBOTHJBeTNXRVlkcHc2Q0FIZy4iLCJzdWIiOiJkeHFQOVhxXzRWYmhNSXlnbF90eENVQXpRZno1NGJieGF1c01GVkl2QW13IiwidGlkIjoiMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhIiwidXRpIjoiQ0tuU0VHR1RqRUtSQ29BSE1EY2hBQSIsInZlciI6IjIuMCJ9.iRNdfj74k5LO2URUtkeKcB6aCFIldzxwhXtYxF6b4sp6q3a36qCvhp2q1fnMluux79Bfi_DJAx70NJSvMcoT3iXMlhVMNJ2iFt80uNhrQ4y9-F_9DK2Odz-3HvyPg706jzGteJflX5h0WhepzNfHuJHAspDUSQFmm8AjUxVPc7qZkJcjsVkPqBv0DXw4sH43Su3FrEJ5y5XbxulfKSBDCWcRspk4NLN_d53QJOz_TCi3WOjwqlLGDsZeDQleU1wcS48DTSIcLPP23f2PCFuq6qX7SIQ6eOnYhmk8C9WGUKvpoNZu73zet4uWQcNQ7Zb_xbLzKKleDv5ssBQiipMRMg;  `  
`bot-gdpr-consent=true;   `  
`bot-token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJzdWIiOiJkN2M2M2UxMC1iMWY0LTExZWQtYWZhMS0wMjQyYWMxMjAwMDIiLCJjb3VudHJ5IjoiUG9sYW5kIiwicm9sZXMiOiJBRE1JTiIsImlzcyI6Imh0dHA6Ly9sb2NhbGhvc3Q6ODA4MC8iLCJleHAiOjE2NzgxMjMzMzUsInV1aWQiOiJkN2M2M2UxMC1iMWY0LTExZWQtYWZhMS0wMjQyYWMxMjAwMDIiLCJpYXQiOjE2NzgwOTQ1MzV9.1XUWCU6iA15y313mgPD1rMKkXhlBF1Kbpi6h2mY38PNeIuUoIwVJ4-SxQvzVMtstt_LCSpshP6E9vn36VZ-oNA'  `  
`-H 'Origin: http://localhost:4200'  `  
`-H 'Referer: http://localhost:4200/'  `  
`-H 'Sec-Fetch-Dest: empty'  `  
`-H 'Sec-Fetch-Mode: cors'  `  
`-H 'Sec-Fetch-Site: same-site'  `  
`-H 'User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64)AppleWebKit/537.36 (KHTML, like Gecko) Chrome/110.0.0.0 Safari/537.36'  `  
`-H 'sec-ch-ua: "Chromium";v="110", "Not A(Brand";v="24", "Google Chrome";v="110"'  `  
`-H 'sec-ch-ua-mobile: ?0'  `  
`-H 'sec-ch-ua-platform: "Windows"'
--compressed  `  

#### Przyklad odpowiedzi:

`[{"uuid":"ea84572c-0edd-4ed1-910d-6d3c4eb166bb", `  
`"name":"Digital","salesforceEnabled":true}, `  
`{"uuid":"22393876-2885-49c8-b321-e58119dda98b",`  
`"name":"Capital Markets","salesforceEnabled":true}]`
