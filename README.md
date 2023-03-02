
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

### 1. Backend <a name="be"></a>

![Schemat architektury](https://github.com/matiolsz/BeOnTime-documentation/blob/main/schema1.png)

#### Schemat Encji

Baza danych sklada sie z trzech schematow:

PROJECT_DB 
![PROJECT_DB](https://github.com/matiolsz/BeOnTime-documentation/blob/main/Project-db.png)

USER_DB
![USER_DB](https://github.com/matiolsz/BeOnTime-documentation/blob/main/User-db.png)

TIMESHEET_DB
![TIMESHEET_DB](https://github.com/matiolsz/BeOnTime-documentation/blob/main/Timesheet-db.png)



#### Autoryzacja i Uwierzytelnianie

BeOnTime wykorzystuje do autoryzacji i uwierzytelniania Azure Active Directory.

    
### 2. Frontend <a name="fe"></a>

