Zwei Faktor Authentifizierung
========================

Hitobito unterstützt die Zwei Faktor Authentifizierung mit folgenden Methoden:

- TOTP mittels QR Code und sechsstelligem Code

TOTP
========================

Voraussetzungen
-------------------------------

Für die zwei Faktor Authentifizierung wird ein Smartphone und die freeOTP App: https://freeotp.github.io/ benötigt. Zum Herunterladen der App benötigen Sie eine Internetverbindung und evtl. ein Konto bei Ihrem App Store. Die App ist komplett kostenfrei.

Einrichten
------------------------------

Um die zwei Faktor Authentifizierung einzurichten, müssen Sie sich erst in Hitobito anmelden. Navigieren Sie anschliessend mittels ihrem Namen als Link oben rechts auf ihr Profil. Sie sollten nun unter dem Dropdown "Login" den Knopf "Zwei Faktor Authentifizierung einrichten" sehen. Sobald Sie den entsprechenden Knopf drücken, landen Sie auf einer neuen Seite mit einem QR Code.

Öffnen Sie nun die freeOTP App auf Ihrem Smartphone und drücken Sie auf den QR Code Knopf in der Kopfzeile der App. Nun öffnet sich die Kamera mit einem Quadrat in der Mitte. Scannen Sie den QR Code indem sie das Quadrat in der Kamera über den QR Code halten.

Sobald der Code gescannt wurde, schliesst sich die Kamera und ein neues Element in der Liste sollte auf der App ersichtlich sein. Dies erkennen Sie anhand der Bezeichnung ''hitobito'' und ihrer E-Mail. Klicken Sie nun auf den Eintrag und ein sechsstelliger Code wird angezeigt.

Dieser Code ändert sich alle paar Sekunden. Tippen Sie den Code in Hitobito ab und klicken Sie auf "Absenden". Sollte der Code inkorrekt sein, wird eine enstprechende Nachricht angezeigt und Sie müssen es erneut versuchen. Sobald der Code korrekt eingegeben wurde, werden Sie auf Ihr Profil zurückgeleitet und die zwei Faktor Authentifizierung ist eingerichtet.

Login mit zwei Faktor Authentifizierung
-----------------------------------------------

Sobald Sie die zwei Faktor Authentifizierung eingerichtet haben, müssen Sie den Code auf der App bei jedem Login eingeben. Nach der Eingabe Ihrer E-Mail und Passwort werden Sie auf eine Seite mit einer Eingabeaufforderung weitergeleitet. Tippen Sie nun wieder den Code aus Ihrer freeOTP App ab und klicken Sie auf "Absenden". Sollte der Code nicht korrekt sein, wird eine entsprechende Nachricht angezeigt. Ist der Code jedoch korrekt, werden Sie authentifiziert und in Hitobito weitergeleitet.

Zurücksetzen und Deaktivieren
--------------------------------------

Admins können die Zwei Faktor Authentifizierung einer Person zurücksetzen oder deaktivieren, indem Sie auf das Profil einer Person navigieren. Dort erscheinen unter dem Dropdown "Login" zwei Knöpfe "Zwei Faktor Authentifizierung zurücksetzen" & "Zwei Faktor Authentifizierung deaktivieren".

Wird die 2FA zurückgesetzt, wird der Nutzer beim nächsten Login einen neuen QR Code scannen müssen.

Bei der Deaktivierung wird der Nutzer nicht mehr zur 2FA aufgefordert.
