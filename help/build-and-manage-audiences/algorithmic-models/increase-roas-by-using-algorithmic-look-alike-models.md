---
title: ROAS verhogen door Algorithmic (look-Alike) Models in Audience Manager te gebruiken
description: De echte kracht van look-alike Modeling van de Audience Manager komt wanneer u probeert uw basislijnpubliek tegen een kwaliteit uit te breiden, gloednieuwe reeks gebruikers van de tweede en derde gegevensbronnen. Leer in deze zelfstudie de stappen om een model te maken van deze gegevens.
feature: algoritmische modellen
topics: null
audience: all
activity: use
doc-type: feature video
team: Technical Marketing
thumbnail: 25188.jpg
kt: 1849
translation-type: tm+mt
source-git-commit: 6c81fd73d2c5abd646b0d38b6f4eebde837b09f2
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 0%

---


# ROAS vergroten door algoritme (look-Alike) [!UICONTROL Models] in Audience Manager {#increase-roas-by-using-algorithmic-look-alike-models-in-audience-manager} te gebruiken

De echte kracht van look-alike [!UICONTROL Modeling] van de Audience Manager komt wanneer u probeert om uw basislijnpubliek tegen een kwaliteit uit te breiden, gloednieuwe reeks gebruikers van [!UICONTROL second party] en [!UICONTROL third party] [!UICONTROL data sources]. In deze zelfstudie leert u de stappen die nodig zijn om een [!UICONTROL model] van deze gegevens te maken.

## [!UICONTROL Second Party] of [!UICONTROL Third Party] Gegevensstromen van de Audience Marketplace {#enable-2nd-or-3rd-party-data-streams-from-the-audience-marketplace} inschakelen

Als u [!UICONTROL second party] en [!UICONTROL third party] gegevens in een blik-gelijkaardig [!UICONTROL model] wilt gebruiken, moeten wij eerst deze gegevens in uw interface van de Audience Manager toelaten. Adobe heeft een groot aantal [!UICONTROL second party] en [!UICONTROL third party] gegevensleveranciers waaruit u kunt kiezen. Deze zijn beschikbaar voor u in een zelf-serverinterface in AAM, via de Audience Marketplace. Navigeer naar de Audience Marketplace en blader door de mogelijkheden. In de volgende video ziet u hoe u dit kunt doen, inclusief hoe u gratis streams kunt inschakelen voordat u deze koopt, zodat u zich op de gegevens kunt aanmelden die het nuttigst zijn voor uw organisatie voordat u de prijs van de gegevensaanbieder doorvoert.

Ook, om u te helpen onderzoeken en beslissen over welke gegevensleverancier te gebruiken, is een grote bron [[!DNL Adobe Audience Finder]](https://www.adobe-audience-finder.com/).

>[!VIDEO](https://video.tv.adobe.com/v/25188/?quality=12)

## Een ideale gebruiker identificeren/maken (conversie) [!UICONTROL trait] of [!UICONTROL segment] {#identify-create-an-ideal-user-conversion-trait-or-segment}

Wat probeert u mensen op uw site te laten doen? Wat is uw conversiegebeurtenis? Natuurlijk, zijn er vele verschillende antwoorden op deze vraag, afhankelijk van uw plaatstype/verticaal en uw organisatorische doelstellingen. Het is in ieder geval gebruikelijk in AAM een [!UICONTROL trait] te maken voor bezoekers die aan deze criteria voldoen.

In de video hieronder, zal ik u tonen hoe te om een omzetting [!UICONTROL trait] tot stand te brengen, die u op zijn plaats zult willen hebben aangezien u door dit leerprogramma verdergaat en een blik-gelijkend [!UICONTROL model] creeert.

Wanneer u Adobe Analytics-gebeurtenissen gebruikt om [!UICONTROL traits] te maken, moet u ook rekening houden met een grote gotcha, zodat u niet meer gebruikers verzamelt dan u zou mogen in [!UICONTROL trait]. Bekijk de volgende video voor de grote openbaring. :)

>[!VIDEO](https://video.tv.adobe.com/v/23431/?quality=12)

**NOTA:** In de video hierboven, veronderstelt het voorbeeld dat ik toon dat u Adobe Analytics hebt. Dat is natuurlijk niet het geval. Als u Google Analytics (GA) hebt, hebben wij een module die u kunt gebruiken om gegevens naar AAM (zie [documentatie](https://marketing.adobe.com/resources/help/en_US/aam/dil-google-universal-analytics.html)) te verzenden, en als uw omzettingsactiviteit op uw plaats naar AAM door GA wordt verzonden, dan kunt u uw omzetting [!UICONTROL trait] van dat tot stand brengen. Als u een andere analytische oplossing hebt (of geen analytische oplossing), kunt u nog steeds gegevens naar AAM sturen via onze DIL-code en de functie `submit`, enz. (zie de [documentatie](https://marketing.adobe.com/resources/help/en_US/aam/c_dil.html)). Maak vervolgens de conversie [!UICONTROL trait] op basis van de gegevens die worden verzonden wanneer de conversieactiviteit op de site wordt uitgevoerd.

## Maak een look-alike [!UICONTROL Model] van [!UICONTROL Second Party] of [!UICONTROL Third Party] Data {#create-a-look-alike-model-from-2nd-or-3rd-party-data}

Na het voltooien van de bovenstaande stappen, zijn we nu klaar om een algoritme (look-alike) [!UICONTROL Model] te maken. Tijdens het instellen van de [!UICONTROL model] gebruiken we de conversie [!UICONTROL trait] als onze basis [!UICONTROL trait] (belangrijke bezoekers die we willen dupliceren) en gebruiken we de ingeschakelde [!UICONTROL third party]-gegevensstroom als onze groep mensen die we willen ophalen.

>[!VIDEO](https://video.tv.adobe.com/v/25190/?quality-12)

## Een belangrijke beste praktijk {#an-important-best-practice}

Bij het maken van de algoritmische [!UICONTROL model] in de Audience Manager, willen we natuurlijk dat de [!UICONTROL model] zo effectief mogelijk is. Aangezien [!UICONTROL model] alle [!UICONTROL traits] overweegt dat de leden van uw basis [!UICONTROL trait]/[!UICONTROL segment] deel van uitmaken, helpt het [!UICONTROL model] niet als ALLE mensen in [!UICONTROL trait]/[!UICONTROL segment] zijn. Als u een supergeneriek [!UICONTROL traits] hebt (zoals iedereen die naar uw site is gegaan, of iedereen die een advertentie van u heeft ontvangen, enz.), moet u ervoor zorgen dat [!UICONTROL data source] waartoe ze behoren NIET is opgenomen in [!UICONTROL data sources] in [!UICONTROL model]. In het gebruiksgeval van dit artikel is het onwaarschijnlijk dat u dat zou doen, omdat we ons richten op het bekijken van [!UICONTROL third party]-gegevens voor onze nieuwe look-alies, maar het is de moeite waard om het toch te vermelden, en het is van toepassing op ALLE van uw algoritme [!UICONTROL models].

## Een algoritme [!UICONTROL Trait] {#creating-an-algorithmic-trait} maken

Daarna, zullen wij een Algorithmic [!UICONTROL Trait] moeten creëren, zodat de resultaten van [!UICONTROL model] kunnen worden gebruikt. Als u geen [!UICONTROL trait] maakt, is het model nutteloos. Dus, nadat [!UICONTROL model] looppas, ben zeker om in [!UICONTROL trait] dialoog te gaan en een Algorithmic [!UICONTROL Trait] te creëren. De volgende video doorloopt het en toont een paar uiteinden.

>[!VIDEO](https://video.tv.adobe.com/v/25191/?quality=12)

## Een [!UICONTROL Segment] maken van de [!UICONTROL Model]-gegevens en deze verzenden naar DSP {#creating-a-segment-from-the-model-data-and-sending-it-to-dsps}

Als u eenmaal een algoritme [!UICONTROL Trait] hebt gemaakt, kunt u een nieuwe [!UICONTROL segment] maken om deze in te zetten, zodat u de gegevens kunt activeren (u kunt geen [!UICONTROL trait] activeren, maar een nieuwe één-[!UICONTROL trait] [!UICONTROL segment] maken met het algoritme [!UICONTROL Trait] erin, zodat u [!UICONTROL segment] kunt activeren (gebruiken).

Nadat u een [!UICONTROL segment] van dit algoritme [!UICONTROL trait] hebt gemaakt, hebt u een publiek van potentiële klanten die eruitzien als mensen die al op uw site zijn geconverteerd. Nu kunt u dit [!UICONTROL segment] aan om het even welk van uw DSP [!UICONTROL destinations] in Audience Manager in kaart brengen. U kunt uw marketing richten aan die blik-alikes, die eerder op uw plaats dan enkel het normale publiek zullen omzetten, die uw Terugkeer op Advertentie verhogen. Veel succes!
