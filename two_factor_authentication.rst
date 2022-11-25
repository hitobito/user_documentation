Zwei-Faktor-Authentifizierung
========================

Hitobito unterstützt die Zwei-Faktor-Authentifizierung mit folgender Methode:

- TOTP mittels Authenticator-App und sechsstelligem Code

Voraussetzungen
-------------------------------

Für die Zwei-Faktor-Authentifizierung wird ein Smartphone und eine Authenticator-App benötigt. Die Zwei-Faktor-Authentifizierung wurde mit der kostenfreien freeOTP App (https://freeotp.github.io/) entwickelt und getestet, sollte aber grundsätzlich auch mit anderen ähnlichen Apps wie andOTP (https://github.com/andOTP/andOTP) oder Google Authenticator funktionieren.

Einrichten
------------------------------

Um die Zwei-Faktor-Authentifizierung einzurichten, muss man sich erst in Hitobito anmelden. Auf dem eigenen Profil kann man nun im Dropdown "Login" den Knopf "Zwei Faktor Authentifizierung einrichten" sehen. Durch Klicken auf diesen Knopf landet man auf einer Seite mit einem QR-Code.

In der freeOTP App auf dem Smartphone klickt man nun auf den QR-Code-Knopf in der Kopfzeile. Dadurch öffnet sich die Kamera mit einem Quadrat in der Mitte. Der QR-Code in hitobito kann nun mit der Kamera gescannt werden.

Sobald der Code gescannt wurde, schliesst sich die Kamera und ein neues Element in der Liste sollte auf der App ersichtlich sein. Dies erkennt man anhand der Bezeichnung ''hitobito'' und der E-Mail-Adresse. Durch einen Klick auf den Eintrag wird ein sechsstelliger Code wird angezeigt.

Dieser Code ändert sich alle paar Sekunden. Nun tippt man den Code in hitobito ein und klickt auf "Absenden". Sollte der Code inkorrekt sein, wird eine enstprechende Nachricht angezeigt und mann muss es erneut versuchen. Sobald der Code korrekt und rechtzeitig eingegeben wurde, wird man auf das Profil zurückgeleitet, und die Zwei-Faktor-Authentifizierung ist eingerichtet.

Login mit Zwei-Faktor-Authentifizierung
-----------------------------------------------

Sobald die Zwei-Faktor-Authentifizierung eingerichtet ist, muss der Code von der App bei jedem Login eingegeben werden. Nach der Eingabe von E-Mail und Passwort wird man auf eine Seite mit einer Eingabeaufforderung weitergeleitet. Hier tippt man nun wieder den Code aus der freeOTP App ab und klickt auf "Absenden". Sollte der Code nicht korrekt oder bereits abgelaufen sein, wird eine entsprechende Nachricht angezeigt. Ist der Code jedoch korrekt, wird man authentifiziert und in hitobito weitergeleitet.

Zurücksetzen und deaktivieren
--------------------------------------

Administratoren können die Zwei-Faktor-Authentifizierung einer Person auf deren Profil zurücksetzen oder deaktivieren. Dort erscheinen unter dem Dropdown "Login" zwei Knöpfe "Zwei Faktor Authentifizierung zurücksetzen" und "Zwei Faktor Authentifizierung deaktivieren".

Wird die Zwei-Faktor-Authentifizierung zurückgesetzt, wird der Nutzer beim nächsten Login einen neuen QR Code scannen müssen.

Bei der Deaktivierung wird der Nutzer nicht mehr zur Zwei-Faktor-Authentifizierung aufgefordert.
