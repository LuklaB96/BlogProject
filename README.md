Projrkt powstal w asp.net

Logowanie/rejestracja/wylogowywanie odbywa sie przy pomocy Identity
Podczas rejstreacji e-amil uzytkownika musibyc unikalny, podlega to waalidacji.
Inne pola rowniez sa walidowane a bledy wyswietlane uzytkownikowi.

Aby dzialanie wysyalania emaila dzialalo, musimy skonfigurowac zewnetrzny SMTP 
(moze byc z gmass, lub gmail), w Areas -> Identity -> Pages -> Account -> Register.cs -> SendEmailAsync  umiescic swoje haslo itd. 
Jest opcja ominiecia tego po uruchomieniu aplikacji przejsc do db i zmienic dla uzytkowanika pole EmailComfirmed na True

Sa trzy stopnie dostepu, 
Niezalogowany uzytkownik - widzi tyko posty na stronie glownej.
Zalogowany - to samo co nie zalogowany, moze dodawac posty oraz je wyszukiwac.
Admin - Moze dodawac, wyszukiwac oraz ma dodatkowy panel do edycji/usuwania

Posty - Skladaja sie z Title, content, tag, author, createdAt i AuthorId
Uzytkownika wypelnia tylko title, content oraz tag, reszta jest uzupelniana automatycznie.

Tag jest zahardkodowany w kodzie, jest elementem obiektu post, jest to enum z ktorego mozemy wybrac wartosc.
Na podstawie taga mozemy wyszukac post
Mozemy wyszukiwac po tagach ktore istnieja juz w postach w db
