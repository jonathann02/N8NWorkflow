Byggde ett AI-assisterat n8n-workflow för ärendehantering där inkommande ärenden normaliseras, klassificeras med AI, valideras med regelbaserad completeness check, loggas i data table och routas till Slack eller manuell e-postgranskning. Implementerade även separat error workflow för felsökning och spårbarhet. 



Under projektet stötte jag på flera typiska problem som kan uppstå i automatiseringsflöden:


- Slack-integrationen krävde rätt bot-token, scopes och att botten bjöds in till rätt kanal.
- Data Table-noderna saknade först valda tabeller, vilket gjorde att workflowet inte kunde exekveras.
- Vissa fält blev tomma i loggar och e-post eftersom fältnamn inte matchade mellan noder
- AI-klassificeringen fungerade, men resultatet skickades inte vidare korrekt förrän outputen mappades tydligt i merge-steget.
- Completeness-checken var först för beroende av AI:ns bedömning, så jag ändrade den till en regelbaserad kontroll.
- Slack Blocks gav syntaxfel, så jag förenklade notifieringen till ett vanligt textmeddelande för bättre stabilitet.

Den viktigaste lärdomen var att ett fungerande RPA-flöde behöver tydliga dataformat mellan varje steg, stabil felhantering och regler för alla beslut. 



Mer bilder finns under /screenshots

<img width="2048" height="1158" alt="image" src="https://github.com/user-attachments/assets/4d5de0a7-18a2-440a-92b3-da9f0c8fb4d9" />
