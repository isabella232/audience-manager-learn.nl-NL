---
title: Het gebruiken van look-Alike Modellen om Verkocht uit Inventaris van Uw Gegevens van de Eerste Partij uit te breiden
description: In deze zelfstudie doorlopen we de stappen die u moet uitvoeren om modellen op te zetten en te gebruiken die er uitzien als model, zodat u een nieuw soort publiek kunt maken dat er hetzelfde uitziet en deze als een uitbreiding op uw conversiesegment kunt verkopen.
feature: algorithmic models
topics: null
audience: all
activity: use
doc-type: feature video
team: Technical Marketing
kt: 1688
translation-type: tm+mt
source-git-commit: dfd549508cc223714bdb07ac6fd2aa31e6ca5586
workflow-type: tm+mt
source-wordcount: '825'
ht-degree: 0%

---


# Het gebruiken van kijkt-Alike [!UICONTROL Models] om Verkocht uit Voorraad van Uw [!UICONTROL First Party] Gegevens uit te breiden {#using-look-alike-models-to-extend-sold-out-inventory-from-your-st-party-data}

In deze zelfstudie doorlopen we de stappen die u moet uitvoeren om weerkaatsing in te stellen en te gebruiken, [!UICONTROL Models]zodat u een nieuw soort publiek kunt maken dat er hetzelfde uitziet, en deze kunt verkopen als een uitbreiding van uw conversie [!UICONTROL segment].

## Details kwestie gebruiken {#use-case-details}

U bent een uitgever van inhoud. Als u al voorraad voor converters op uw site hebt verkocht, kunt u denken dat uw kans daar eindigt. Voer AAM look-Alike in [!UICONTROL Models]. Met deze functie kunt u de verkochte voorraad verder uitbreiden en ook het publiek verkopen van mensen die misschien nog niet zijn omgezet, maar die er net zo uitzien als mensen die zijn omgezet. Dit publiek [!UICONTROL segment] verkoopt doorgaans voor minder dan de werkelijke converters, maar u kunt desondanks toevoegen aan uw bedrijfsresultaat door een extra publieksoptie in te stellen voor adverteerders die advertenties op uw site willen plaatsen. Het extra voordeel van dit gebruiksscenario is dat het uitvoeren van dit model op de gegevens van de eerste partij niets kost.

De stappen in deze zelfstudie zijn als volgt:

1. Een ideale gebruiker (conversie) identificeren/maken [!UICONTROL trait] of [!UICONTROL segment]
1. Een object maken [!UICONTROL model] met deze conversie [!UICONTROL trait]/[!UICONTROL segment] als basisitem
1. Kies een of meer [!UICONTROL First party] gegevensbron(nen) in het [!UICONTROL model] dialoogvenster [!UICONTROL model]
1. Een algoritme maken [!UICONTROL Trait] op basis van de [!UICONTROL model] resultaten en het toevoegen [!UICONTROL trait] aan een [!UICONTROL segment]
1. De [!UICONTROL segment] adverteerders de mogelijkheid bieden om de [!UICONTROL segment] omzet uit te breiden

## Een ideale gebruiker (conversie) identificeren/maken [!UICONTROL trait] of [!UICONTROL segment] {#identify-create-an-ideal-user-conversion-trait-or-segment}

Wat probeert u mensen op uw site te laten doen? Wat is uw conversiegebeurtenis? Natuurlijk, zijn er vele verschillende antwoorden op deze vraag, afhankelijk van uw plaatstype/verticaal en uw organisatorische doelstellingen. Het is in ieder geval gebruikelijk om een AAM te creëren [!UICONTROL trait] voor bezoekers die aan deze criteria hebben voldaan.

In dit geval wordt dit al verondersteld, omdat u de voorraad hebt verkocht voor mensen die converters zijn. In het kader van deze zelfstudie is het echter een goede zaak om deze voor de rest van de gebruikszaak te bespreken.

Ook, wanneer het gebruiken van gebeurtenissen om tot stand te brengen [!UICONTROL traits], is er een belangrijke gotcha die u in mening moet houden, zodat u niet meer gebruikers verzamelt dan u in [!UICONTROL trait]zou moeten. Bekijk de volgende video voor de grote openbaring. :)

>[!VIDEO](https://video.tv.adobe.com/v/23431/?quality=12)

**OPMERKING:** In de video hierboven gaat het voorbeeld dat ik toon ervan uit dat je Adobe Analytics hebt. Dat is natuurlijk niet het geval. Als u Google Analytics (GA) hebt, hebben wij een module die u kunt gebruiken om gegevens naar AAM te verzenden (zie de [documentatie](https://marketing.adobe.com/resources/help/en_US/aam/dil-google-universal-analytics.html)), en als uw omzettingsactiviteit op uw plaats naar AAM door GA wordt verzonden, dan kunt u uw omzettingseigenschap van dat tot stand brengen. Als u een andere analytische oplossing hebt (of geen analytische oplossing), kunt u nog steeds gegevens naar AAM sturen via onze DIL-code en de `submit` functie, enz. (zie de [documentatie](https://marketing.adobe.com/resources/help/en_US/aam/c_dil.html)). Maak vervolgens opnieuw de conversietekenmerken op basis van de gegevens die worden verzonden wanneer de conversieactiviteit op de site wordt uitgevoerd.

## Een look-Alike maken [!UICONTROL Model] op basis van [!UICONTROL First Party] gegevens {#creating-a-look-alike-model-from-first-party-data}

In deze stap gaan we een [!UICONTROL First Party] look-Alike creëren [!UICONTROL Model]. Dit betekent dat we niet alleen een [!UICONTROL first party] conversie [!UICONTROL trait]/[!UICONTROL segment] voor onze basis [!UICONTROL trait]/[!UICONTROL segment] zullen gebruiken (dit zou [!UICONTROL models] hoe dan ook normaal zijn), maar dat we ook alleen de pool met [!UICONTROL first party] gegevens zullen bekijken voor meer mensen die er als de converters uitzien. We zullen niet naar [!UICONTROL second party] of [!UICONTROL third party] gegevens kijken.

In dit geval, is dit belangrijk, omdat wij proberen om een [!UICONTROL segment] van gebruikers op onze plaats tot stand te brengen die als omzetters kijken maar enkel nog niet hebben omgezet, zodat wij deze blik-gelijkaardig [!UICONTROL segment] aan geïnteresseerde adverteerders kunnen verkopen.

>[!VIDEO](https://video.tv.adobe.com/v/23504/?quality-12)

## Algorithmic maken [!UICONTROL Trait] {#creating-an-algorithmic-trait}

Daarna zullen wij een Algorithmic moeten creëren [!UICONTROL Trait], zodat de resultaten van [!UICONTROL model] kunnen worden gebruikt. Als u geen [!UICONTROL trait]sjabloon maakt, [!UICONTROL model] is dat nutteloos. Dus na de [!UICONTROL model] uitvoering moet u het [!UICONTROL trait] dialoogvenster openen en een algoritme maken [!UICONTROL Trait]. De volgende video doorloopt het en toont een paar uiteinden.

>[!VIDEO](https://video.tv.adobe.com/v/23523/?quality=12)

## Het Algorithmic [!UICONTROL Segment] aan Advertisers aanbieden {#offering-the-algorithmic-segment-to-advertisers}

Nadat u een algoritme hebt gemaakt, kunt u een nieuw algoritme maken [!UICONTROL Trait]om het in te zetten, zodat u de gegevens kunt activeren (u kunt een algoritme niet activeren [!UICONTROL segment] , maar een nieuw één- [!UICONTROL trait][!UICONTROL trait] met het Algorithmic [!UICONTROL segment] erin maken, zodat u het [!UICONTROL Trait] [!UICONTROL segment]kunt activeren (gebruiken).

Als u eenmaal een [!UICONTROL segment] groep [!UICONTROL first party] bezoekers hebt gemaakt die hoog hebben gescord in het uiterlijk [!UICONTROL model] (die er dus uitzien als converters maar nog niet hebben geconverteerd), kunt u dit aanbieden [!UICONTROL segment] aan adverteerders op uw site, zelfs nadat u al uw voorraad daadwerkelijke converters op uw site hebt verkocht. Dit is een goede manier om dit publiek uit te breiden en extra opbrengst te blijven zien door look-Alike [!UICONTROL Models] in Audience Manager te gebruiken.
