Aby dzialanie wysyalania emaila dzialalo, musimy skonfigurowac zewnetrzny SMTP 
(moze byc z gmass, lub gmail), w Areas -> Identity -> Pages -> Account -> Register.cs -> SendEmailAsync  umiescic swoje haslo itd. 
Jest opcja ominiecia tego po uruchomieniu aplikacji przejsc do db i zmienic dla uzytkowanika pole EmailComfirmed na True

Do postow mozemy dodac tagi ktore sa zahardkodowane w kodzie, sa wymagane, mozemy wyszukaci po tagach. Bedziemy miec mozliwosc szukanie 
po tagach ktore w postach wystepuja w db.
