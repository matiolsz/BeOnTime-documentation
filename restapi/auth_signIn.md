## Uwierzytelnianie

Najpierw uzytkownik loguje sie do azure ad, uzywajac konta z domeny be-tse.com. Azure po zalogowaniu zwraca id-token(msal id-token). Token ten jest ustawiany w cookie. Backend przechwytuje request, sprawdza msal id-token i jezeli jest poprawny, ustawia w ciasteczku jwt token o nazwie bot-token. W przypadku kiedy token jest expired zwraca 401 a token w ciasteczku jest kasowany.

Country - Przy pierwszym logowaniu uzytkownik zobowiazany jest wybrac country. Konto przechodzi w status PENDING_APPROVAL i wybor country bedzie zatwierdzone przez managera. Manager ma tez mozliwosc zmiany country. 

Na podstawie pola country, manager ma mozliwosc pobrania projektow z salesforca albo dodanie nowego projektu. ( Jest xalezne od tego czy kraj ma synchronizacje z salesforcie.)

Na podstawie country rowniez segregujemy pracownikow.

### signIn()

signIn() [inprogress] 

#### Przyklad zadania:


#### Przyklad odpowiedzi:
