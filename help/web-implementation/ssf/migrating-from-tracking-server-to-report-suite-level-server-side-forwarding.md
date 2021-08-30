---
title: Migreren van Tracking Server naar Report Suite-Level Server-Side Forwarding
description: Dit artikel en video zullen u tonen hoe te om server-zijhet door:sturen van de Gegevens van Analytics aan Audience Manager op een niveau van de rapportreeks in plaats van op een volgend serverniveau toe te laten.
product: audience manager
feature: Adobe Analytics Integration
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1776
role: Developer, Data Engineer
level: Intermediate
exl-id: 08b81e52-a28a-43e4-a284-df2460a43016
source-git-commit: 4d4c12e9f9a33760a89460258c3802fcf3a4e22b
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 0%

---

# Migreren van [!UICONTROL Tracking Server] naar [!UICONTROL Report Suite]-niveau [!UICONTROL Server-Side Forwarding] {#migrating-from-tracking-server-to-report-suite-level-server-side-forwarding}

In dit artikel en deze video wordt getoond hoe u [!UICONTROL server-side forwarding] van [!DNL Analytics] Gegevens kunt inschakelen om op een [!UICONTROL report suite] niveau in plaats van op een [!UICONTROL tracking server] niveau te Audience Managers.

## Inleiding {#introduction}

Als u Adobe Audience Manager AND Adobe Analytics hebt, kunt u &quot;[!UICONTROL Server-side Forwarding]&quot;van de [!DNL Analytics] gegevens aan Audience Manager uitvoeren. Dit betekent dat in plaats van de pagina met twee treffers (één naar [!DNL Analytics] en één naar Audience Manager) een hit kan worden verzonden naar [!DNL Analytics] en dat [!DNL Analytics] de gegevens doorstuurt naar de Audience Manager. Als u dit reeds hebt in werking gesteld, en als u het vóór Oktober 2017 had toegelaten/uitgevoerd, zou uw [!UICONTROL server-side forwarding] op uw &quot;[!UICONTROL Tracking Server]&quot;gebaseerd kunnen zijn, die door de Zorg van de Klant van de Adobe of de Raadpleging van de Adobe moest worden toegelaten. Vanaf oktober 2017 kunt u [!UICONTROL server-side forwarding] nu zelf configureren en op [!UICONTROL Report Suite]-niveau uitvoeren (PER [!UICONTROL Report Suite] doorsturen). Er zijn aanzienlijke voordelen aan verbonden, die hieronder zullen worden besproken.

## [!UICONTROL Tracking Server] Doorsturen {#tracking-server-forwarding}

Uw [!UICONTROL tracking server] is de plaats waarnaar u uw [!DNL Analytics] gegevens, en ook het domein verzendt waarop het beeldverzoek en het koekje worden geschreven. Deze moet worden ingesteld in DTM of [!DNL Experience Platform Launch] of in het [!DNL AppMeasurement.js]-bestand en ziet er doorgaans zo uit, waarbij uw site of bedrijfsnaam &quot;mijnsite&quot; vervangt:

`s.trackingServer = "mysite.sc.omtrdc.net";`

Als [!UICONTROL server-side forwarding] is ingesteld om op [!UICONTROL tracking server] niveau door te sturen, zal om het even welke klap die wordt verzonden naar [!UICONTROL tracking server] (als de Dienst van identiteitskaart van de Experience Cloud ook wordt toegelaten) aan Audience Manager door:sturen. Dit moest door de Adobe klantendienst of de Raadpleging van de Adobe worden toegelaten. Zij zijn ook degenen die het kunnen onbruikbaar maken, NADAT u aan [!UICONTROL report suite] het door:sturen hebt overgegaan, zoals hieronder beschreven.

Als u niet zeker weet of [!DNL tracking server forwarding] voor u is ingeschakeld, neemt u contact op met de klantenservice of Adobe Consulting van de Adobe en u kunt deze op de hoogte stellen.

## [!UICONTROL Report Suite]-niveau  [!UICONTROL Server-Side Forwarding] {#report-suite-level-server-side-forwarding}

Één van de grootste voordelen aan het bewegen aan [!UICONTROL report suite] door:sturen van [!UICONTROL tracking server] is dat u &quot;Audience Analytics&quot;nu kunt gebruiken, die de capaciteit is om Audience Manager [!UICONTROL segments] terug naar Adobe Analytics voor gedetailleerde [!UICONTROL segment] analyse door:sturen. Deze grote eigenschap wordt NIET gesteund als u nog op [!UICONTROL tracking server] door:sturen en niet [!UICONTROL report suite] door:sturen bent. Zie meer informatie over Audience Analytics in [documentatie](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html).

>[!VIDEO](https://video.tv.adobe.com/v/23701/?quality=12)

## Belangrijke tip {#additional-resources}

Zoals vermeld in de video hierboven, zodra u alle [!UICONTROL report suites] hebt geplaatst om door:sturen die u aan Audience Manager wilt door:sturen, zou u de Zorg van de Klant van de Adobe of Adobe die moeten contacteren en hen hebben [!UICONTROL tracking server] het door:sturen onbruikbaar maken. Het is geen noodgeval voor u om dit te doen, omdat het hebben van zowel [!UICONTROL tracking server] door:sturen als [!UICONTROL report suite] door:sturen NIET in dubbele klappen zal resulteren. Nochtans, is het beste praktijken om slechts [!UICONTROL report suite] te hebben door:sturen op. Als u [!UICONTROL tracking server] door:sturen op verlaat, niet alleen zou het gegevens van [!UICONTROL report suites] door:sturen die u niet door:sturen wilt, maar in de toekomst, nadat u (en iedereen bij uw bedrijf) bent vergeten dat [!UICONTROL tracking server] door:sturen is, zou u kunnen denken dat de gegevens niet voor specifieke [!UICONTROL report suite] (omdat het niet op het niveau van de rapportreeks wordt aangezet) door:sturen, maar de gegevens worden toch door:sturen wegens [!UICONTROL tracking server]. Vervolgens verspilt u tijd en geld om uit te zoeken waarom het wordt doorgestuurd en betaalt u ook voor AAM serveraanroepen die u niet had verwacht. Het is dus verstandig om [!UICONTROL tracking server] door:sturen uit te schakelen zodra u alle [!UICONTROL report suites] hebt geplaatst om door:sturen die voor uw bedrijfsbehoeften steek houden.
