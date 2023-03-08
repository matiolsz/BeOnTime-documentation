## Project

Projekty naleza do danego departamentu. Sa importowane do BeOnTime przez integracje z Salesforcem. 

### findAll()

findAll() jest uzywana w celu znalezienia projektow, ktore nie sa przypisane do departamentu. Wymagana jest rola admina.

#### Przyklad zadania:

`GET /projects?isAssigned=false HTTP/1.1`  
`Accept: application/json, text/plain, */*`  
`Accept-Encoding: gzip, deflate, br`  
`Accept-Language: pl-PL,pl;q=0.9,en-US;q=0.8,en;q=0.7`  
`Connection: keep-alive`  
`Content-Type: application/json`  
`Cookie: country=poland; bot-gdpr-consent=true; msal.idtoken=eyJ0eXAiOiJKV1QiLCJhbGciOiJSUzI1NiIsImtpZCI6Ii1LSTNROW5OUjdiUm9meG1lWm9YcWJIWkdldyJ9.eyJhdWQiOiI2MmVkOTBmYi0zYzA5LTRiZjMtYWMwYy1iNzU4NDYxZGE3MGUiLCJpc3MiOiJodHRwczovL2xvZ2luLm1pY3Jvc29mdG9ubGluZS5jb20vMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhL3YyLjAiLCJpYXQiOjE2NzgyNzQ0NDcsIm5iZiI6MTY3ODI3NDQ0NywiZXhwIjoxNjc4Mjc4MzQ3LCJhaW8iOiJBVFFBeS84VEFBQUFkVWlFZVk3akRmRXJLb29qTDRWVFJTUEQvUGthNnNBZEFyMlRXdDl6akpZQTFreFl2SUxzbjM1ZDlWYldDU3E1IiwiZW1haWwiOiJtLm9sc3phbmthQGJlLXRzZS5jb20iLCJuYW1lIjoiTWF0ZXVzeiBPbHN6YW5rYSIsIm5vbmNlIjoiNjk5YjQzMDktNzc5MS00MjViLTkzOWQtYjlhZmU2NjA5OTZlIiwib2lkIjoiNGI1NDk5OGUtY2M3NS00MjVhLWFlMjYtZjgxYzQ4MDg2ZTc2IiwicHJlZmVycmVkX3VzZXJuYW1lIjoibS5vbHN6YW5rYUBiZS10c2UuY29tIiwicmgiOiIwLkFZSUFOSGVvRzMtSDEwR2dwdGJ0ZFZ1UC12dVE3V0lKUFBOTHJBeTNXRVlkcHc2Q0FIZy4iLCJzdWIiOiJkeHFQOVhxXzRWYmhNSXlnbF90eENVQXpRZno1NGJieGF1c01GVkl2QW13IiwidGlkIjoiMWJhODc3MzQtODc3Zi00MWQ3LWEwYTYtZDZlZDc1NWI4ZmZhIiwidXRpIjoiWHItWWFyNFdYa2FsTUMzVERDVWNBQSIsInZlciI6IjIuMCJ9.G-s1gum9QwMNW8Pi_I8a8kySOW7UzKaAdMynvG_OGJ6AHdrWlG3AksIT15IOstz9M_ouGVsLgruiGLKXxr9aCeujUqoP2K82ueoWHGUXodP52g_UOpIaqd5WJZcDjbdJJFgWgioXla0DWEEy4gQ4Vgu0r8iQHPUjcQxqF_9sIzHz605XeXoZc9uBY3yNYsn5xTXfjFR4I0OehJgbcmENK2QGCgvCEPDBfYIVxJ1El5Dr0P89R1pK76di0-EKtdOiGVQLJvHotSJk0takeCBlOBjLCVkvnb5GRR9pnlSWCjnhq_mAAiMYb9Hc8QPlU3Hbi17n5i9R3lqj4mIgpj9jmQ; bot-token=eyJ0eXAiOiJKV1QiLCJhbGciOiJIUzUxMiJ9.eyJzdWIiOiIyOGRjYmQ5Yy1iYzFkLTExZWQtYWZhMS0wMjQyYWMxMjAwMDIiLCJjb3VudHJ5IjoiUG9sYW5kIiwicm9sZXMiOiJBRE1JTiIsImlzcyI6Imh0dHA6Ly9sb2NhbGhvc3Q6ODA4MC8iLCJleHAiOjE2NzgzMDM1NDgsInV1aWQiOiIyOGRjYmQ5Yy1iYzFkLTExZWQtYWZhMS0wMjQyYWMxMjAwMDIiLCJpYXQiOjE2NzgyNzQ3NDh9.b1RNC-s4VSp4Di7bquEZnP58hVzH3C5bstFVMYBtkiQ2jm2joGT_TFYQonaOwbbO0Uox6Lk227cbGvP8jxPy-w`  
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

json list of projects
