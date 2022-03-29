---
title: Hoe te om uw partneridentiteitskaart of subdomain te identificeren
description: Leer hoe te om uw partneridentiteitskaart of subdomain te identificeren wanneer het uitvoeren van sommige eigenschappen van Experience Cloud, en over twee plaatsen u deze identiteitskaart in Audience Manager UI kunt krijgen.
feature: Implementation Basics
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2359
role: Developer, Data Engineer
level: Intermediate
exl-id: d3f4a12d-acc5-47b7-a38a-a6a14152bf3a
source-git-commit: 62b43b5627dabf754cf821f974a56c60989ef7ef
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 0%

---

# Hoe te om uw Audience Manager Subdomain te identificeren {#how-to-identify-your-audience-manager-partner-id-or-subdomain}

Wanneer het uitvoeren van sommige eigenschappen van Experience Cloud, moet u weten wat uw Audience Manager `Subdomain` wordt (ook wel uw `client ID` of `Partner ID`). In deze video zullen we u twee plaatsen tonen waar u deze informatie kunt ophalen in de gebruikersinterface van de Audience Manager.

## Het einde weggeven... {#giving-away-the-ending}

Als u liever gewoon naar de video wilt springen zonder deze korte video te bekijken, kunt u uw `Partner Subdomain` op twee plaatsen in de gebruikersinterface:

1. Als u al een [!UICONTROL rule-based] eigenschap, klikken **[!UICONTROL Get Trait URL]**
   [!UICONTROL Get Trait URL] Deze bevindt zich naast de eigenschap in de lijst met kenmerken in die map en de URL neemt het subdomein in de URL op.
1. Als u in de **[!UICONTROL Tools]** > **[!UICONTROL Tags]** interface en klik **[!UICONTROL Get code]** voor uw container, is subdomain tegen het eind van de lijn Akamai

Als u de video niet snel kunt vinden met deze snelle referenties, is de video een korte tijdsreferentie. :)

>[!VIDEO](https://video.tv.adobe.com/v/25922/?quality=12)

>[!IMPORTANT]
>
>Er is een numerieke identiteitskaart die aan elke klant van Adobe Experience Cloud wordt toegewezen, en dit wordt vaak bedoeld als &quot;PID&quot;, of identiteitskaart van de Partner. Dit is niet de id waarover we het in dit artikel en video hebben. In plaats daarvan, is &quot;partnersubdomain&quot;, die soms als partneridentiteitskaart wordt bedoeld, gewoonlijk een versie van de cliëntnaam, en is subdomain van de server waarnaar de gegevens worden verzonden. Bijvoorbeeld, als uw bedrijf &quot;Knopen van Bob&quot;is (alle dingen kleven, natuurlijk, haha), dan is het waarschijnlijk dat uw partner subdomain &quot;bobsknobs&quot;zou zijn, terwijl &quot;PID&quot;iets meer als &quot;12345&quot;zou zijn. U moet typisch niet uw PID kennen, maar uw subdomain is belangrijk om te weten, zodat u uw implementatie van de Audience Manager kunt vormen.
