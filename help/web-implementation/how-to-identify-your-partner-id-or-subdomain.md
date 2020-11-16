---
title: Hoe te om uw identiteitskaart van de Partner van de Audience Manager of Subdomain te identificeren
description: Wanneer het uitvoeren van sommige eigenschappen van Experience Cloud, moet u weten wat uw Audience Manager "identiteitskaart van de Partner"is (soms ook als uw "cliënt ID"of "Subdomain"wordt bedoeld). In deze video tonen we u twee plaatsen waar u deze id kunt ophalen in de gebruikersinterface van de Audience Manager.
feature: implementation basics
topics: null
audience: implementer
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 2359
translation-type: tm+mt
source-git-commit: a108c51fdad66f4e7974eb96609b6d8f058cb6ff
workflow-type: tm+mt
source-wordcount: '331'
ht-degree: 0%

---


# Hoe te om uw Audience Manager Subdomain te identificeren {#how-to-identify-your-audience-manager-partner-id-or-subdomain}

Wanneer het uitvoeren van sommige eigenschappen van Experience Cloud, moet u weten wat uw Audience Manager `Subdomain` (ook soms ook als uw `client ID` of `Partner ID`) wordt bedoeld. In deze video zullen we u twee plaatsen tonen waar u deze informatie kunt ophalen in de gebruikersinterface van de Audience Manager.

## Het einde weggeven... {#giving-away-the-ending}

Als u liever gewoon naar de video wilt springen zonder deze korte video te bekijken, vindt u uw video op twee `Partner Subdomain` plaatsen in de interface:

1. Als u al een [!UICONTROL rule-based] [!UICONTROL trait]bestand hebt gemaakt, klikt u op **[!UICONTROL Get Trait URL]**
   [!UICONTROL Get Trait URL] bevindt zich naast de [!UICONTROL trait] naam in de lijst van [!UICONTROL traits] die map en de URL neemt uw subdomein op in de URL.
1. Als u in de interface **[!UICONTROL Tools]** > **[!UICONTROL Tags]** gaat en **[!UICONTROL Get code]** voor uw container klikt, is subdomain tegen het eind van de lijn Akamai

Als u de video niet snel kunt vinden met deze snelle referenties, is de video een korte tijdsreferentie. :)

>[!VIDEO](https://video.tv.adobe.com/v/25922/?quality=12)

>[!IMPORTANT]
>
>Er is een numerieke identiteitskaart die aan elke klant van Adobe Experience Cloud wordt toegewezen, en dit wordt vaak bedoeld als &quot;PID&quot;, of identiteitskaart van de Partner. Dit is niet de id waarover we het in dit artikel en video hebben. In plaats daarvan, is &quot;partnersubdomain&quot;, die soms als partneridentiteitskaart wordt bedoeld, gewoonlijk een versie van de cliëntnaam, en is subdomain van de server waarnaar de gegevens worden verzonden. Bijvoorbeeld, als uw bedrijf &quot;Knopen van Bob&quot;is (alle dingen kleven, natuurlijk, haha), dan is het waarschijnlijk dat uw partner subdomain &quot;bobsknobs&quot;zou zijn, terwijl &quot;PID&quot;iets meer als &quot;12345&quot;zou zijn. U moet typisch niet uw PID kennen, maar uw subdomain is belangrijk om te weten, zodat u uw implementatie van de Audience Manager kunt vormen.

