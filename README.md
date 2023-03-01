
# BeOnTime

## Table of Content:
- [Getting Started](#getting-started)
- [Getting Started For Developers](#getting-started-for-developers)
- [Use BeOnTime](#use-beontime)
  - [Consultant](#consultant)
    - bla
  - [Manager](#manager)
    - bla
  - [Administrator](#administrator)
    - bla 
- [Technical Documentation](#technical-documentation)

## Getting Started <a name="getting-started"></a>

**BeOnTime** służy do raportowania czasu pracy konsultantów i managerów oraz generowania raportów przedstawiających czas pracy. 

Rejestrowany czas pracy musi być przyporządkowany do projektu (w którym dany konsultant pracuje).
 Z tego powodu rozróżniamy w aplikacji podział na:

- Departament
- Projekt
- Work Order 
- Timesheet

**Departament** składa się z projektów oraz managerów. 

**Projekty** składają się z Work Orderów, konsultantów i managerów.

**Work Order** określa przedział czasu oraz konsultantów lub managerów należących do Work Orderu.
Aby konsultant mógł rejestrować godziny czasu w danym okresie czasu i do danego projektu musi zostać dodany do odpowiedniego Work Orderu(należącego do wspomnianego projektu oraz mieszczącego się we wspomnianym okresie czasu.)

**Timesheet** przedstawia miesięczny wykaz godzin pracy dla danego konsultanta lub managera w Work Orderze, w którym konsultant zarejestrował czas pracy.

Istnieje podział na trzy role (consultant, manager oraz admin).

**Consultant** ma możliwość rejestracji godzin czasu w Work Orderze, co za tym idzie w Projekcie, w którym pracuje.

**Manager** może przypisywać użytkowników do projektów, generować raporty ich czasu pracy w danym projekcie oraz rejestrować swoje godziny pracy dla projektu w którym pracuje.

**Administrator** może nadać zwykłemu konsultantowi role managera, dezaktywować konsultanta lub stworzyć departament. (Każdy projekt oraz manager musi należeć do wybranego departamentu.)

Aby lepiej zrozumieć jak działa Be On Time zobacz animacje.


[![BeOnTime Intro](https://github.com/matiolsz/BeOnTime-documentation/blob/main/be.png)](https://youtu.be/lTmHzP2kh4M)

## Getting Started For Developers <a name="getting-started-for-developers"></a>

## Use BeOnTime <a name="use-beontime"></a>

## Technical Documentation <a name="technical-documentation"></a>

    
