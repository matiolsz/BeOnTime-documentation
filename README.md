
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

| Zasoby | Endpoint |
| --- | --- |
| Sign In | `/authentication/sign-in/{country}` |

#### Departament
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera Departament 

| Zasoby | Endpoint |
| --- | --- |
| Find All Departments | `/departments` |
| Find All Managers | `/departments/{uuid}/managers` |
| Assign Manager | `/departments/{departmentUuid}/managers/{managerUuid}` |
| Dismiss Manager | `/departments/{departmentUuid}/managers/{managerUuid}` |
| Find All Projects | `/departments/{uuid}/projects` |
| Create Department | `/departments` |
| Update Department | `/departments/{departmentUuid}` |
| Delete Department | `/departments/{departmentUuid}` |
| Assign Project | `/departments/{departmentUuid}/projects/{projectName}` |
| Unassign Project | `/departments/{departmentUuid}/projects/{projectName}` |

#### Manager
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera Manager 

| Zasoby | Endpoint |
| --- | --- |
| Unassign Manager From Departments | `/managers/{managerUuid}/departments` |

#### Project
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera Project 

| Zasoby | Endpoint |
| --- | --- |
| Find All Projects For Manager | `/projects` |
| Find All Projects | `/projects?isAssigned=boolean` |
| Get Projects From Salesforce | `/projects/salesforce` |
| Add Project | `/projects` |
| Update Project | `/projects/{uuid}` |
| Delete Project | `/projects/{uuid}` |


#### Report
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera Report 

| Zasoby | Endpoint |
| --- | --- |
| Generate Excel Report For User - specified month | `/manager/timesheets/report?userUUid=UUID&month=int&year=int` |
| Generate Excel Report For Project - specified month| `/manager/timesheets/report?projectName=String&month=int&year=int` |
| Generate Excel Report For Projects - specified month| `/manager/timesheets/report?projectNames=List<String>&month=int&year=int` |
| Generate Excel Report for Projects - manual date| `/manager/timesheets/reportreport?projectNames=List<String>&fromDate=LocalDate&toDate=LocalDate` |
| Generate CSV Report - specified month | `/manager/timesheets/report?month=int&year=int` |
| Send Reports To Salesforce - specified month | `/manager/timesheets/report/salesforce?month=int&year=int` |

#### Timesheet
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera Timesheet 

| Zasoby | Endpoint |
| --- | --- |
| Find Timesheet | `/timesheets?userUUid=UUID&month=int&year=int` |
| Update Timesheet | `/timesheets/{uuid}` |
| Create Timesheet | `/timesheets?userUUid=UUID&month=int&year=int` |

#### TimesheetManager
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera TimesheetManager 

| Zasoby | Endpoint |
| --- | --- |
| Find Work Orders For Project - specified month | `/manager/timesheets/work-orders?projectUUid=UUID&month=int&year=int` |
| Find Timesheets for specified month | `/manager/timesheets?month=int&year=int` |
| Find Burnout for Project | `/manager/timesheets/burnout?projectName=string` |
| Update Status Of Timesheet | `/manager/timesheets/{uuid}?status=string` |
| Update (hasLocationBasedRate) for Timesheet | `/manager/timesheets?workOrderUuid=uuid&hasLocationBasedRate=boolean` |
| Check if Entries exists  | `/manager/timesheets/entries?workOrderUUID=uuid` |
| Delete Entries | `/manager/timesheets?userUUid=UUID&workOrderUuid=uuid&start=LocalDate&end=LocalDate&projectName=string` |

#### User
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera User 

| Zasoby | Endpoint |
| --- | --- |
| Find all Users | `/users` |
| Find User by name | `/users/email` |
| Find User by UUID | `/users/{uuid}` |
| Create User | `/users` |
| Update User's role | `/users/{uuid}?role=string` |
| Update User's activity | `/users/status/{userUuid}` |
| Approve User | `/users/{uuid}/approve` |
| Update User's Country | `/users/{uuid}?country=string` |

#### WorkOrder
Ponizsza tabela przedstawia dostepne zasoby dla kontrolera WorkOrder 

| Zasoby | Endpoint |
| --- | --- |
| Find Project's Work Orders | `/work-orders/projectUUID?projectUUID=UUID` |
| Find User's Work Orders - specified month | `/work-orders?userUUid=UUID&month=int&year=int` |
| Find Work Order By It's UUID| `/work-orders/{uuid}` |
| Find Project's Work Orders - specified month | `/work-orders/users?projectUUID=UUID&month=int&year=int` |
| Assign User to Work Order | `/work-orders/{workOrderUuid}/users/{userUuid}` |
| Dismiss User from Work Order | `/work-orders/{workOrderUuid}/users/{userUuid}` |
| Set Work Order's editable field | `/work-orders/{workOrderUuid}?isEditable=boolean` |
| Update Work Order | `/work-orders/{workOrderUuid}&workOrderUuid=uuid` |
| Create Work Order | `/work-orders` |
| Delete Work Order | `/work-orders/{workOrderUuid}` |


## 2. Frontend <a name="fe"></a>

