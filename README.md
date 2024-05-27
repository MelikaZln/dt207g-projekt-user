# Front-end: User

Front enden har två delar eftersom jag har två separata webbplatser, den ena är till användaren och den andra är till admin. Här vill jag beskriva User delen alltså 
den del som användarna på webbplatsen kan använda.
I denna del har jag en html-fil, istället för att ha flera undersidor och olika html-filer har jag bara en html-fil med olika sektioner för olika delar.
Jag har en css fil som stilar html sidan och en script.js fil.

I package.json har jag skrivit: "start": "http-server", för att sidan ska startas när jag skriver npm start i terminalen.

Script.js filen intergrerar med servern för att hämta menyn, visa den på sidan och skicka bokningsdata till servern. 
Här nere beskriver jag olika funktionerna.

getMenu():  En funktion som anropas för att hämta menyalternativ för varje kategori och visa dem på sidan. Den använder fetch() för att
göra GET-anrop till servern för varje kategori och sedan uppdaterar DOM för att visa menyobjekten.

capitalize(str): är en funktion som kapitaliserar första bokstaven av en sträng.

Eventlyssnare för att hantera klickhändelser på hamburgeikonen (för mindre enheter) och länkar i navigationsmenyn.

bookTable(name, numberOfGuests, phone, date, time):  En funktion för att skicka bokningsinformation till servern genom att göra en 
POST-förfrågan till /api/bookings. Den validerar även användarinput och visar lämpliga felmeddelanden på sidan.

DOMContentLoaded-händelsen: En händelse som triggas när DOM har laddats helt. Inuti denna händelsefunktion anropas getMenu()
för att initialt hämta menyalternativ och eventlyssnare läggs till bokningsformuläret för att fånga in formulärinskickningar
och validera input innan bokningsinformationen skickas till servern.

I fetch-anroparna har jag skrivit url till porten som backend använder. 


