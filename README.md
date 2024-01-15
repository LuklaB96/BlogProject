Projrkt powstal w asp.net

WAŻNE! Przed odpaleniem projektu zrobić update-database 


Logowanie/rejestracja/wylogowywanie odbywa sie przy pomocy Identity
Podczas rejstreacji e-amil uzytkownika musibyc unikalny, podlega to waalidacji.
Inne pola rowniez sa walidowane a bledy wyswietlane uzytkownikowi.

Aby można było wysyłać e-mail z potwierdzeniem rejestracji trzeba skonfigurować klienta SMTP:
1. Areas -> Identity -> Pages -> Account -> Register.cshtml.cs -> SendEmailAsync umieszczamy realne dane serwera SMTP (Gmail etc.)
2. Wchodzimy w Program.cs i w linijcie 21 zmieniamy
   ```
   options.SignIn.RequireConfirmedAccount = false
   ```
   na
   ```
   options.SignIn.RequireConfirmedAccount = true
   ```
I powinno działać.

Sa trzy stopnie dostepu, 
Niezalogowany uzytkownik - widzi tyko posty na stronie glownej.
Zalogowany - to samo co nie zalogowany, moze dodawac posty oraz je wyszukiwac.
Admin - Moze dodawac, wyszukiwac oraz ma dodatkowy panel do edycji/usuwania

Posty - Skladaja sie z Title, content, tag, author, createdAt i AuthorId
Uzytkownika wypelnia tylko title, content oraz tag, reszta jest uzupelniana automatycznie.

Tag jest zahardkodowany w kodzie, jest elementem obiektu post, jest to enum z ktorego mozemy wybrac wartosc.
Na podstawie taga mozemy wyszukac post
Mozemy wyszukiwac po tagach ktore istnieja juz w postach w db
