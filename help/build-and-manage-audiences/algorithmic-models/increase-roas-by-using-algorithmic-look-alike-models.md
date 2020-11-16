---
title: ROAS verhogen door Algorithmic (look-Alike) Models in Audience Manager te gebruiken
description: De echte kracht van look-alike Modeling van de Audience Manager komt wanneer u probeert uw basislijnpubliek tegen een kwaliteit uit te breiden, gloednieuwe reeks gebruikers van de tweede en derde gegevensbronnen. Leer in deze zelfstudie de stappen om een model te maken van deze gegevens.
feature: algorithmic models
topics: null
audience: all
activity: use
doc-type: feature video
team: Technical Marketing
kt: 1849
translation-type: tm+mt
source-git-commit: a108c51fdad66f4e7974eb96609b6d8f058cb6ff
workflow-type: tm+mt
source-wordcount: '860'
ht-degree: 0%

---


# ROAS verhogen door Algorithmic (look-Alike) [!UICONTROL Models] in Audience Manager te gebruiken {#increase-roas-by-using-algorithmic-look-alike-models-in-audience-manager}

De echte kracht van look-alike van de Audience Manager [!UICONTROL Modeling] komt wanneer u probeert om uw basislijnpubliek tegen een kwaliteit uit te breiden, gloednieuwe reeks gebruikers van [!UICONTROL second party] en [!UICONTROL third party] [!UICONTROL data sources]. Leer in deze zelfstudie de stappen die nodig zijn om een [!UICONTROL model] formulier te maken van deze gegevens.

## Gegevensstromen inschakelen [!UICONTROL Second Party] of [!UICONTROL Third Party] uit de Audience Marketplace {#enable-2nd-or-3rd-party-data-streams-from-the-audience-marketplace}

Om [!UICONTROL second party] en [!UICONTROL third party] gegevens in blik-gelijkaardig te gebruiken [!UICONTROL model], moeten wij eerst deze gegevens in uw interface van de Audience Manager toelaten. Adobe heeft een groot aantal [!UICONTROL second party] en [!UICONTROL third party] gegevensleveranciers waaruit u kunt kiezen. Deze zijn beschikbaar voor u in een zelf-serverinterface in AAM, via de Audience Marketplace. Navigeer naar de Audience Marketplace en blader door de mogelijkheden. In de volgende video ziet u hoe u dit kunt doen, inclusief hoe u gratis streams kunt inschakelen voordat u deze koopt, zodat u zich op de gegevens kunt aanmelden die het nuttigst zijn voor uw organisatie voordat u de prijs van de gegevensaanbieder doorvoert.

Ook, om u te helpen onderzoeken en beslissen over welke gegevensleverancier aan gebruik is, is een groot middel [[!DNL Adobe Audience Finder]](https://www.adobe-audience-finder.com/).

>[!VIDEO](https://video.tv.adobe.com/v/25188/?quality=12)

## Een ideale gebruiker (conversie) identificeren/maken [!UICONTROL trait] of [!UICONTROL segment] {#identify-create-an-ideal-user-conversion-trait-or-segment}

Wat probeert u mensen op uw site te laten doen? Wat is uw conversiegebeurtenis? Natuurlijk, zijn er vele verschillende antwoorden op deze vraag, afhankelijk van uw plaatstype/verticaal en uw organisatorische doelstellingen. Het is in ieder geval gebruikelijk om een AAM te creëren [!UICONTROL trait] voor bezoekers die aan deze criteria hebben voldaan.

In de onderstaande video laat ik u zien hoe u een conversie maakt [!UICONTROL trait]die u tijdens het doorlopen van deze zelfstudie wilt gebruiken om een look-alike te maken [!UICONTROL model].

Wanneer u Adobe Analytics-gebeurtenissen gebruikt om te maken, [!UICONTROL traits][!UICONTROL trait]moet u ook rekening houden met een grote gotcha, zodat u niet meer gebruikers verzamelt dan u zou moeten doen. Bekijk de volgende video voor de grote openbaring. :)

>[!VIDEO](https://video.tv.adobe.com/v/23431/?quality=12)

**OPMERKING:** In de video hierboven gaat het voorbeeld dat ik toon ervan uit dat je Adobe Analytics hebt. Dat is natuurlijk niet het geval. Als u Google Analytics (GA) hebt, hebben wij een module die u kunt gebruiken om gegevens naar AAM te verzenden (zie de [documentatie](https://marketing.adobe.com/resources/help/en_US/aam/dil-google-universal-analytics.html)), en als uw omzettingsactiviteit op uw plaats naar AAM door GA wordt verzonden, dan kunt u uw omzetting [!UICONTROL trait] van dat tot stand brengen. Als u een andere analytische oplossing hebt (of geen analytische oplossing), kunt u nog steeds gegevens naar AAM sturen via onze DIL-code en de `submit` functie, enzovoort. (zie de [documentatie](https://marketing.adobe.com/resources/help/en_US/aam/c_dil.html)). Maak vervolgens de conversie [!UICONTROL trait] op basis van de verzonden gegevens wanneer de conversieactiviteit op de site wordt uitgevoerd.

## Een look-alike maken [!UICONTROL Model] van [!UICONTROL Second Party] of [!UICONTROL Third Party] gegevens {#create-a-look-alike-model-from-2nd-or-3rd-party-data}

Nadat u de bovenstaande stappen hebt uitgevoerd, zijn we nu klaar om een algoritme (look-alike) te maken [!UICONTROL Model]. Terwijl we de database opzetten, gebruiken we de conversie [!UICONTROL model]als onze basis [!UICONTROL trait] (belangrijke bezoekers die we willen dupliceren) en gebruiken we de ingeschakelde [!UICONTROL trait] [!UICONTROL third party] gegevensstroom als onze groep mensen waaruit we willen trekken.

>[!VIDEO](https://video.tv.adobe.com/v/25190/?quality-12)

## Belangrijke beste praktijken {#an-important-best-practice}

Bij het maken van de algoritme [!UICONTROL model] in de Audience Manager willen we natuurlijk dat de algoritme zo effectief mogelijk [!UICONTROL model] is. Aangezien de [!UICONTROL model] gebruiker alle elementen in overweging neemt [!UICONTROL traits] waarvan de leden in uw basis [!UICONTROL trait]/[!UICONTROL segment] deel uitmaken, is het voor de gebruiker niet nuttig [!UICONTROL model] als ALLE personen zich in een [!UICONTROL trait]/[!UICONTROL segment]bevinden. Daarom als u om het even welke supergenerische [!UICONTROL traits] (zoals iedereen die naar uw plaats ging, of iedereen die om het even welke advertentie van u, enz. heeft ontvangen) hebt, zorg ervoor dat niet [!UICONTROL data source] dat zij tot in [!UICONTROL data sources] in uw [!UICONTROL model]. behoren. In het gebruiksgeval van dit artikel is het onwaarschijnlijk dat u dit doet, omdat we ons richten op het bekijken van [!UICONTROL third party] gegevens voor onze nieuwe look-alies, maar het is de moeite waard om het toch te vermelden en geldt voor ALLE algoritmische elementen [!UICONTROL models].

## Algorithmic maken [!UICONTROL Trait] {#creating-an-algorithmic-trait}

Daarna, zullen wij een Algorithmic moeten creëren [!UICONTROL Trait], zodat de resultaten van [!UICONTROL model] kunnen worden gebruikt. Als u geen model maakt, [!UICONTROL trait]is het nutteloos. Dus, na de [!UICONTROL model] looppas, ben zeker om in de [!UICONTROL trait] dialoog te gaan en een Algorithmic tot stand te brengen [!UICONTROL Trait]. De volgende video doorloopt het en toont een paar uiteinden.

>[!VIDEO](https://video.tv.adobe.com/v/25191/?quality=12)

## Een [!UICONTROL Segment] formulier maken op basis van [!UICONTROL Model] Gegevens en verzenden naar DSP {#creating-a-segment-from-the-model-data-and-sending-it-to-dsps}

Nadat u een algoritme hebt gemaakt, kunt u een nieuw algoritme maken [!UICONTROL Trait]om het in te zetten, zodat u de gegevens kunt activeren (u kunt een algoritme niet activeren [!UICONTROL segment] , maar een nieuw één- [!UICONTROL trait][!UICONTROL trait] met het Algorithmic [!UICONTROL segment] erin maken, zodat u het [!UICONTROL Trait] [!UICONTROL segment]) kunt activeren (gebruiken).

Als u eenmaal een [!UICONTROL segment] formulier hebt gemaakt van dit algoritme [!UICONTROL trait], hebt u een publiek van potentiële klanten die eruitzien als mensen die al op uw site zijn geconverteerd. Nu kun je dit [!UICONTROL segment] aan elk van je DSP [!UICONTROL destinations] in Audience Manager toewijzen. U kunt uw marketing richten aan die blik-alikes, die eerder op uw plaats dan enkel het normale publiek zullen omzetten, die uw Terugkeer op Advertentie verhogen. Veel succes!
