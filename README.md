
# BeOnTime

## Table of Content:
- [Getting Started](#getting-started)
- [Getting Started For Developers](#getting-started-for-developers)
- [Use BeOnTime](#use-beontime)

  [1. Konsultant](#consultant)
    
    - [Zarejestruj swoj czas pracy](#c1)

  [2. Manager](#manager)

    - [Dodaj Work Order](#m1)
    - [Edytuj Work Order](#m2)
    - [Dodaj konsultanta do Work Order](#m3)
    - [Zaakceptuj Timesheet konsultanta](#m4)
    - [Wygeneruj raport miesięczny dla konsultanta](#m5)
    - [Wygeneruj raport dla projektu](#m6)

  [3. Administrator](#administrator)

    - [Stworz departament](#a1)
    - [Dodaj projekt do departamentu](#a2)
    - [Dodaj managera do departamentu](#a3)
    - [Stworz managera](#a4)
    - [Deaktywuj konsultanta](#a5) 

  [4. FAQ](#faq)

    - [Konsultant nie widzi swojego Timesheetu](#f1)
    -  

- [Dokumentacja Techniczna](#technical-documentation)

  [1. Backend](#be)

  [2. Frontend](#fe)

## Getting Started <a name="getting-started"></a>

**BeOnTime** służy do raportowania czasu pracy konsultantów i managerów oraz generowania raportów przedstawiających czas pracy. 

Rejestrowany czas pracy musi być przyporządkowany do projektu (w którym dany konsultant pracuje).
 Z tego powodu rozróżniamy w aplikacji podział na:

- Departament
- Projekt
- Work Order 
- Timesheet
- Entry

**Departament** składa się z projektów oraz managerów. 

**Projekty** składają się z Work Orderów, konsultantów i managerów.

**Work Order** określa przedział czasu oraz konsultantów lub managerów należących do Work Orderu.
Aby konsultant mógł rejestrować godziny czasu w danym okresie czasu i do danego projektu musi zostać dodany do odpowiedniego Work Orderu(należącego do wspomnianego projektu oraz mieszczącego się we wspomnianym okresie czasu.)

**Timesheet** przedstawia miesięczny wykaz godzin pracy dla danego konsultanta lub managera w Work Orderze, w którym konsultant zarejestrował czas pracy.

**Entry** to ilosc godzin wpisanych do jednego dnia.

Istnieje podział na trzy role (consultant, manager oraz admin).

**Consultant** ma możliwość rejestracji godzin czasu w Work Orderze, co za tym idzie w Projekcie, w którym pracuje.

**Manager** może przypisywać użytkowników do projektów, generować raporty ich czasu pracy w danym projekcie oraz rejestrować swoje godziny pracy dla projektu w którym pracuje.

**Administrator** może nadać zwykłemu konsultantowi role managera, dezaktywować konsultanta lub stworzyć departament. (Każdy projekt oraz manager musi należeć do wybranego departamentu.)

Aby lepiej zrozumieć jak działa Be On Time zobacz animacje.


[![BeOnTime Intro](https://github.com/matiolsz/BeOnTime-documentation/blob/main/be.png)](https://youtu.be/lTmHzP2kh4M)

## Getting Started For Developers <a name="getting-started-for-developers"></a>

#### 1. Setting up backend

Pod [tym linkiem](https://github.com/Be-Poland/bot_backend) znajdziesz kod backendowy BeOnTime oraz informacje jak uruchomic aplikacje lokalnie.


#### 2. Setting up frontend
Pod [tym linkiem](https://github.com/Be-Poland/bot_frontend) znajdziesz kod frontendowy BeOnTime oraz informacje jak uruchomic aplikacje lokalnie.


## Use BeOnTime <a name="use-beontime"></a>

#### 1. Konsultant <a name="consultant"></a>

- Zarejestruj swoj czas pracy<a name="c1"></a>

#### 2. Manager <a name="manager"></a>

- Dodaj Work Order<a name="m1"></a>
- Edytuj Work Order<a name="m2"></a>
- Dodaj konsultanta do Work Order<a name="m3"></a>
- Zaakceptuj Timesheet konsultanta<a name="m4"></a>
- Wygeneruj raport miesięczny dla konsultanta<a name="m5"></a>
- Wygeneruj raport dla projektu<a name="m6"></a>

#### 3. Administrator <a name="administrator"></a>

- Stworz departament<a name="a1"></a>
- Dodaj projekt do departamentu<a name="a2"></a>
- Dodaj managera do departamentu<a name="a3"></a>
- Stworz managera<a name="a4"></a>
- Deaktywuj konsultanta<a name="a5"></a>

#### 4. FAQ <a name="faq"></a>

- Konsultant nie widzi swojego Timesheetu<a name="f1"></a>

## Dokumentacja Techniczna <a name="technical-documentation"></a>

## 1. Backend <a name="be"></a>

![Schemat architektury](https://github.com/matiolsz/BeOnTime-documentation/blob/main/schema1.png)

### Schemat Encji

Baza danych sklada sie z trzech schematow:

PROJECT_DB 
![PROJECT_DB](https://github.com/matiolsz/BeOnTime-documentation/blob/main/Project-db.png)

USER_DB
![USER_DB](https://github.com/matiolsz/BeOnTime-documentation/blob/main/User-db.png)

TIMESHEET_DB
![TIMESHEET_DB](https://github.com/matiolsz/BeOnTime-documentation/blob/main/Timesheet-db.png)



### Autoryzacja i Uwierzytelnianie

BeOnTime wykorzystuje do autoryzacji i uwierzytelniania Azure Active Directory.

    
### REST API

Dostepne zasoby dla BeOnTime dzielimy na ponizsze kontrolery:

- Authentication
- Departament
- Manager
- Project
- Report
- Timesheet
- TimesheetManager
- User
- WorkOrder

#### Authentication
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera Authentication 

| Zasoby | Endpoint | Request Method |
| --- | --- | --- |
| [Sign In](restapi/auth_signIn) | `/authentication/sign-in/{country}` | GET |

#### Departament
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera Departament 

| Zasoby | Endpoint | Request Method |
| --- | --- | --- |
| Find All Departments | `/departments` | GET |
| Find All Managers | `/departments/{uuid}/managers` | GET |
| Assign Manager | `/departments/{departmentUuid}/managers/{managerUuid}` | POST |
| Dismiss Manager | `/departments/{departmentUuid}/managers/{managerUuid}` | DELETE |
| Find All Projects | `/departments/{uuid}/projects` | GET |
| Create Department | `/departments` | POST |
| Update Department | `/departments/{departmentUuid}` | PUT |
| Delete Department | `/departments/{departmentUuid}` | DELETE |
| Assign Project | `/departments/{departmentUuid}/projects/{projectName}` | POST |
| Unassign Project | `/departments/{departmentUuid}/projects/{projectName}` | DELETE |

#### Manager
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera Manager 

| Zasoby | Endpoint | Request Method |
| --- | --- | --- |
| Unassign Manager From Departments | `/managers/{managerUuid}/departments` | DELETE |

#### Project
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera Project 

| Zasoby | Endpoint | Request Method |
| --- | --- | --- |
| Find All Projects For Manager | `/projects` | GET |
| Find All Projects | `/projects?isAssigned=boolean` | GET |
| Get Projects From Salesforce | `/projects/salesforce` | GET |
| Add Project | `/projects` | POST |
| Update Project | `/projects/{uuid}` | PUT |
| Delete Project | `/projects/{uuid}` | DELETE |


#### Report
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera Report 

| Zasoby | Endpoint | Request Method |
| --- | --- | --- |
| Generate Excel Report For User - specified month | `/manager/timesheets/report?userUUid=UUID&month=int&year=int` | GET |
| Generate Excel Report For Project - specified month| `/manager/timesheets/report?projectName=String&month=int&year=int` | GET |
| Generate Excel Report For Projects - specified month| `/manager/timesheets/report?projectNames=List<String>&month=int&year=int` | GET |
| Generate Excel Report for Projects - manual date| `/manager/timesheets/reportreport?projectNames=List<String>&fromDate=LocalDate&toDate=LocalDate` | GET |
| Generate CSV Report - specified month | `/manager/timesheets/report?month=int&year=int` | GET |
| Send Reports To Salesforce - specified month | `/manager/timesheets/report/salesforce?month=int&year=int` | POST |

#### Timesheet
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera Timesheet 

| Zasoby | Endpoint | Request Method |
| --- | --- | --- |
| Find Timesheet | `/timesheets?userUUid=UUID&month=int&year=int` | GET |
| Update Timesheet | `/timesheets/{uuid}` | PATCH |
| Create Timesheet | `/timesheets?userUUid=UUID&month=int&year=int` | POST |

#### TimesheetManager
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera TimesheetManager 

| Zasoby | Endpoint | Request Method |
| --- | --- | --- |
| Find Work Orders For Project - specified month | `/manager/timesheets/work-orders?projectUUid=UUID&month=int&year=int` | GET |
| Find Timesheets for specified month | `/manager/timesheets?month=int&year=int` | GET |
| Find Burnout for Project | `/manager/timesheets/burnout?projectName=string` | GET |
| Update Status Of Timesheet | `/manager/timesheets/{uuid}?status=string` | PATCH |
| Update (hasLocationBasedRate) for Timesheet | `/manager/timesheets?workOrderUuid=uuid&hasLocationBasedRate=boolean` | PATCH |
| Check if Entries exists  | `/manager/timesheets/entries?workOrderUUID=uuid` | HEAD |
| Delete Entries | `/manager/timesheets?userUUid=UUID&workOrderUuid=uuid&start=LocalDate&end=LocalDate&projectName=string` | DELETE |

#### User
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera User 

| Zasoby | Endpoint | Request Method |
| --- | --- | --- |
| Find all Users | `/users` | GET |
| Find User by name | `/users/email` | GET |
| Find User by UUID | `/users/{uuid}` | GET |
| Create User | `/users` | POST |
| Update User's role | `/users/{uuid}?role=string` | PATCH |
| Update User's activity | `/users/status/{userUuid}` | PATCH |
| Approve User | `/users/{uuid}/approve` | PATCH |
| Update User's Country | `/users/{uuid}?country=string` | PATCH |

#### WorkOrder
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera WorkOrder 

| Zasoby | Endpoint | Request Method |
| --- | --- | --- |
| Find Project's Work Orders | `/work-orders/projectUUID?projectUUID=UUID` | GET |
| Find User's Work Orders - specified month | `/work-orders?userUUid=UUID&month=int&year=int` | GET |
| Find Work Order By It's UUID| `/work-orders/{uuid}` | GET |
| Find Project's Work Orders - specified month | `/work-orders/users?projectUUID=UUID&month=int&year=int` | GET |
| Assign User to Work Order | `/work-orders/{workOrderUuid}/users/{userUuid}` | POST |
| Dismiss User from Work Order | `/work-orders/{workOrderUuid}/users/{userUuid}` | DELETE |
| Set Work Order's editable field | `/work-orders/{workOrderUuid}?isEditable=boolean` | PATCH |
| Update Work Order | `/work-orders/{workOrderUuid}&workOrderUuid=uuid` | PUT |
| Create Work Order | `/work-orders` | POST |
| Delete Work Order | `/work-orders/{workOrderUuid}` | DELETE |


## 2. Frontend <a name="fe"></a>

