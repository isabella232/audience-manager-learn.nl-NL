---
title: Migreren van Tracking Server naar Report Suite-Level Server-Side Forwarding
description: Dit artikel en video zullen u tonen hoe te om server-zijhet door:sturen van de Gegevens van Analytics aan Audience Manager op een niveau van de rapportreeks in plaats van op een volgend serverniveau toe te laten.
product: audience manager, analytics
feature: integration with analytics
topics: null
audience: implementer
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1776
translation-type: tm+mt
source-git-commit: dfd549508cc223714bdb07ac6fd2aa31e6ca5586
workflow-type: tm+mt
source-wordcount: '577'
ht-degree: 0%

---


# Migreren van [!UICONTROL Tracking Server] naar [!UICONTROL Report Suite]niveau [!UICONTROL Server-Side Forwarding] {#migrating-from-tracking-server-to-report-suite-level-server-side-forwarding}

In dit artikel en deze video ziet u hoe u [!UICONTROL server-side forwarding] van [!DNL Analytics] Gegevens de Audience Manager op een [!UICONTROL report suite] niveau in plaats van op een [!UICONTROL tracking server] niveau kunt inschakelen.

## Inleiding {#introduction}

Als u Adobe Audience Manager AND Adobe Analytics hebt, kunt u &quot;[!UICONTROL Server-side Forwarding]&quot;van de [!DNL Analytics] gegevens aan Audience Manager uitvoeren. Dit betekent dat in plaats van dat uw pagina 2 hits (een naar [!DNL Analytics] en een naar een Audience Manager) verzendt, er een hit naar kan worden verzonden [!DNL Analytics]en dat de gegevens naar de Audience Manager [!DNL Analytics] worden doorgestuurd. Als u dit al hebt gedaan en dit voor oktober 2017 hebt ingeschakeld/geïmplementeerd, [!UICONTROL server-side forwarding] kan uw toepassing zijn gebaseerd op uw &quot;[!UICONTROL Tracking Server]&quot;, die moet worden ingeschakeld door de klantenservice van Adobe of Adobe-advies. Vanaf oktober 2017, kunt u [!UICONTROL server-side forwarding] zich nu vormen, en het doen op een [!UICONTROL Report Suite] niveau (door:sturen PER [!UICONTROL Report Suite]). Er zijn aanzienlijke voordelen aan verbonden, die hieronder zullen worden besproken.

## [!UICONTROL Tracking Server] Doorsturen {#tracking-server-forwarding}

Uw [!UICONTROL tracking server] is de locatie waarnaar u de [!DNL Analytics] gegevens verzendt en ook het domein waar de afbeeldingsaanvraag en het cookie worden geschreven. Deze moet worden ingesteld in DTM of [!DNL Experience Platform Launch], of in het [!DNL AppMeasurement.js] bestand, en ziet er doorgaans zo uit, met uw site of bedrijfsnaam die &quot;mijnsite&quot; vervangt:

`s.trackingServer = "mysite.sc.omtrdc.net";`

Als [!UICONTROL server-side forwarding] opstelling aan voorwaartse op het [!UICONTROL tracking server] niveau is, zal om het even welke treffer die naar dit wordt verzonden [!UICONTROL tracking server] (ALS de Dienst van identiteitskaart van de Experience Cloud ook wordt toegelaten) door:sturen aan Audience Manager. Dit moest door de Adobe klantendienst of de Raadpleging van de Adobe worden toegelaten. Zij zijn ook degenen die het kunnen onbruikbaar maken, NADAT u aan het [!UICONTROL report suite] door:sturen hebt overgegaan, zoals hieronder beschreven.

Als u niet zeker weet of [!DNL tracking server forwarding] deze functie voor u is ingeschakeld, neemt u contact op met de klantenservice of Adobe Consulting van de Adobe en kan u dit op de hoogte worden gesteld.

## [!UICONTROL Report Suite]-niveau [!UICONTROL Server-Side Forwarding] {#report-suite-level-server-side-forwarding}

Één van de grootste voordelen aan het bewegen aan [!UICONTROL report suite] door:sturen van [!UICONTROL tracking server] het door:sturen is dat u &quot;Audience Analytics&quot;nu zult kunnen gebruiken, die de capaciteit is om Audience Manager [!UICONTROL segments] terug naar Adobe Analytics voor gedetailleerde [!UICONTROL segment] analyse door:sturen. Deze grote eigenschap wordt NIET gesteund als u nog op het door:sturen en niet door:sturen bent. [!UICONTROL tracking server] [!UICONTROL report suite] Meer informatie over Audience Analytics vindt u in de [documentatie](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

>[!VIDEO](https://video.tv.adobe.com/v/23701/?quality=12)

## Belangrijke tip {#additional-resources}

Zoals vermeld in de video hierboven, zodra u alle [!UICONTROL report suites] reeks hebt om door:sturen die u aan Audience Manager wilt door:sturen, zou u de Zorg van de Klant van de Adobe of Adobe die moeten contacteren en hen hebben het [!UICONTROL tracking server] door:sturen onbruikbaar maken. Het is geen noodgeval voor u om dit te doen, omdat het hebben van zowel door:sturen als het [!UICONTROL tracking server] [!UICONTROL report suite] door:sturen NIET in dubbele klappen zal resulteren. Nochtans, is het beste praktijken om slechts het [!UICONTROL report suite] door:sturen te hebben. Als u het door:sturen op verlaat, niet alleen zou het gegevens van door:sturen [!UICONTROL tracking server] die u niet wilt door:sturen, maar in de toekomst, nadat u (en iedereen bij uw bedrijf) bent vergeten dat het [!UICONTROL report suites] door:sturen is, zou u kunnen denken dat de gegevens niet voor een specifiek [!UICONTROL tracking server] (omdat het niet op het niveau van de rapportreeks wordt aangezet) door:sturen, maar de gegevens worden nog steeds door:sturen wegens [!UICONTROL report suite] [!UICONTROL tracking server]. Vervolgens verspilt u tijd en geld om uit te zoeken waarom het wordt doorgestuurd en betaalt u ook voor AAM serveraanroepen die u niet had verwacht. Het is dus verstandig om het [!UICONTROL tracking server] doorsturen uit te schakelen zodra u over alle [!UICONTROL report suites] mogelijkheden beschikt om door te sturen die zinvol zijn voor uw bedrijfsbehoeften.
