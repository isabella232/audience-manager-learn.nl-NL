---
title: Het gebruiken van look-Alike Modellen om Verkocht uit Inventaris van Uw Gegevens van de Eerste Partij uit te breiden
description: In deze zelfstudie doorlopen we de stappen die u moet uitvoeren om modellen op te zetten en te gebruiken die er uitzien als model, zodat u een nieuw soort publiek kunt maken dat er hetzelfde uitziet en deze als een uitbreiding op uw conversiesegment kunt verkopen.
feature: algoritmische modellen
topics: null
audience: all
activity: use
doc-type: feature video
team: Technical Marketing
thumbnail: 23523.jpg
kt: 1688
translation-type: tm+mt
source-git-commit: ba76f9437e5d8f0495e4f2dfafb90cbf2da6454f
workflow-type: tm+mt
source-wordcount: '827'
ht-degree: 0%

---


# Het gebruiken van kijkt-weg [!UICONTROL Models] om Verkocht uit Inventaris van Uw [!UICONTROL First Party] Gegevens {#using-look-alike-models-to-extend-sold-out-inventory-from-your-st-party-data} uit te breiden

In deze zelfstudie doorlopen we de stappen die u moet uitvoeren voor het instellen en gebruiken van look-Alike [!UICONTROL Models], zodat u nieuwe look-alike soorten publiek kunt maken en deze kunt verkopen als een uitbreiding op uw conversie [!UICONTROL segment].

## Hoofdletterdetails gebruiken {#use-case-details}

U bent een uitgever van inhoud. Als u al voorraad voor converters op uw site hebt verkocht, kunt u denken dat uw kans daar eindigt. Voer AAM look-Alike [!UICONTROL Models] in. Met deze functie kunt u de verkochte voorraad verder uitbreiden en ook het publiek verkopen van mensen die misschien nog niet zijn omgezet, maar die er net zo uitzien als mensen die zijn omgezet. Dit publiek [!UICONTROL segment] verkoopt doorgaans voor minder dan de werkelijke converters, maar u kunt desondanks toevoegen aan uw bedrijfsresultaat door een extra publieksoptie te bieden aan adverteerders die advertenties op uw site willen plaatsen. Het extra voordeel van dit gebruiksscenario is dat het uitvoeren van dit model op de gegevens van de eerste partij niets kost.

De stappen in deze zelfstudie zijn als volgt:

1. Een ideale gebruiker identificeren/maken (conversie) [!UICONTROL trait] of [!UICONTROL segment]
1. Een [!UICONTROL model] maken met deze conversie [!UICONTROL trait]/[!UICONTROL segment] als basisitem
1. Kies [!UICONTROL First party] gegevensbron(nen) in [!UICONTROL model] en voer [!UICONTROL model] uit
1. Maak een algoritme [!UICONTROL Trait] uit de [!UICONTROL model] resultaten en voeg [!UICONTROL trait] toe aan een [!UICONTROL segment]
1. [!UICONTROL segment] bieden belangstellende adverteerders aan om de omzet [!UICONTROL segment] uit te breiden

## Een ideale gebruiker identificeren/maken (conversie) [!UICONTROL trait] of [!UICONTROL segment] {#identify-create-an-ideal-user-conversion-trait-or-segment}

Wat probeert u mensen op uw site te laten doen? Wat is uw conversiegebeurtenis? Natuurlijk, zijn er vele verschillende antwoorden op deze vraag, afhankelijk van uw plaatstype/verticaal en uw organisatorische doelstellingen. Het is in ieder geval gebruikelijk in AAM een [!UICONTROL trait] te maken voor bezoekers die aan deze criteria voldoen.

In dit geval wordt dit al verondersteld, omdat u de voorraad hebt verkocht voor mensen die converters zijn. In het kader van deze zelfstudie is het echter een goede zaak om deze voor de rest van de gebruikszaak te bespreken.

Ook, wanneer het gebruiken van gebeurtenissen om [!UICONTROL traits] te creëren, is er een belangrijke gotcha die u in mening moet houden, zodat u niet meer gebruikers verzamelt dan u in [!UICONTROL trait] zou moeten. Bekijk de volgende video voor de grote openbaring. :)

>[!VIDEO](https://video.tv.adobe.com/v/23431/?quality=12)

**NOTA:** In de video hierboven, veronderstelt het voorbeeld dat ik toon dat u Adobe Analytics hebt. Dat is natuurlijk niet het geval. Als u Google Analytics (GA) hebt, hebben wij een module die u kunt gebruiken om gegevens naar AAM (zie [documentatie](https://marketing.adobe.com/resources/help/en_US/aam/dil-google-universal-analytics.html)) te verzenden, en als uw omzettingsactiviteit op uw plaats naar AAM door GA wordt verzonden, dan kunt u uw omzettingseigenschap van dat tot stand brengen. Als u een andere analytische oplossing hebt (of geen analytische oplossing), kunt u nog steeds gegevens naar AAM sturen via onze DIL-code en de functie `submit`, enz. (zie de [documentatie](https://marketing.adobe.com/resources/help/en_US/aam/c_dil.html)). Maak vervolgens opnieuw de conversietekenmerken op basis van de gegevens die worden verzonden wanneer de conversieactiviteit op de site wordt uitgevoerd.

## Een look-Alike [!UICONTROL Model] maken op basis van [!UICONTROL First Party] Data {#creating-a-look-alike-model-from-first-party-data}

In deze stap gaan we een [!UICONTROL First Party] look-Alike [!UICONTROL Model] maken. Dit betekent dat we niet alleen een [!UICONTROL first party] conversie [!UICONTROL trait]/[!UICONTROL segment] voor onze basis [!UICONTROL trait]/[!UICONTROL segment] (dit zou normaal voor de meeste [!UICONTROL models] hoe dan ook zijn) zullen gebruiken, maar ook slechts de pool van [!UICONTROL first party] gegevens voor meer mensen zullen onderzoeken die als de converters kijken. We zullen niet naar [!UICONTROL second party] of [!UICONTROL third party] gegevens kijken.

In dit geval, is dit belangrijk, omdat wij proberen om een [!UICONTROL segment] van gebruikers op onze plaats tot stand te brengen die als omzetters kijken maar enkel nog niet omgezet hebben, zodat wij deze blik-als [!UICONTROL segment] aan geïnteresseerde adverteerders kunnen verkopen.

>[!VIDEO](https://video.tv.adobe.com/v/23504/?quality-12)

## Een algoritme [!UICONTROL Trait] {#creating-an-algorithmic-trait} maken

Daarna zullen wij een Algorithmic [!UICONTROL Trait] moeten creëren, zodat de resultaten van [!UICONTROL model] kunnen worden gebruikt. Als u geen [!UICONTROL trait] maakt, is [!UICONTROL model] nutteloos. Dus nadat de [!UICONTROL model] looppas, zeker ben om in [!UICONTROL trait] dialoog te gaan en een Algorithmic [!UICONTROL Trait] te creëren. De volgende video doorloopt het en toont een paar uiteinden.

>[!VIDEO](https://video.tv.adobe.com/v/23523/?quality=12)

## Het Algorithmic [!UICONTROL Segment] aanbieden aan adverteerders {#offering-the-algorithmic-segment-to-advertisers}

Als u eenmaal een algoritme [!UICONTROL Trait] hebt gemaakt, kunt u een nieuwe [!UICONTROL segment] maken om deze in te zetten, zodat u de gegevens kunt activeren (u kunt geen [!UICONTROL trait] activeren, maar een nieuwe één-[!UICONTROL trait] [!UICONTROL segment] maken met het algoritme [!UICONTROL Trait] erin, zodat u [!UICONTROL segment] kunt activeren (gebruiken).

Nadat u een [!UICONTROL segment] van [!UICONTROL first party] bezoekers hebt gemaakt die hoog hebben gescord in de look-alike [!UICONTROL model] (d.w.z. die er als converters uitzien maar nog niet zijn omgezet), kunt u deze [!UICONTROL segment] aanbieden aan adverteerders op uw site, zelfs nadat u al uw voorraad van daadwerkelijke converters op uw site hebt verkocht. Dit is een goede manier om dit publiek uit te breiden en extra opbrengst te blijven zien door look-Alike [!UICONTROL Models] in Audience Manager te gebruiken.
