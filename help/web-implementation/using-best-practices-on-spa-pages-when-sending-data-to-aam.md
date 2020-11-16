---
title: Best practices gebruiken op SPA pagina's wanneer gegevens naar AAM worden verzonden
description: In dit document worden verschillende aanbevolen procedures beschreven die u moet volgen en waarvan u op de hoogte bent wanneer u gegevens verzendt van Single Page Applications (SPA) naar Adobe Audience Manager (AAM). Dit document zal zich op het gebruiken van Launch by Adobe concentreren, die de geadviseerde implementatiemethode is.
feature: implementation basics
topics: spa
audience: implementer
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1390
translation-type: tm+mt
source-git-commit: a108c51fdad66f4e7974eb96609b6d8f058cb6ff
workflow-type: tm+mt
source-wordcount: '576'
ht-degree: 0%

---


# Best practices gebruiken op SPA pagina&#39;s wanneer gegevens naar AAM worden verzonden {#using-best-practices-on-spa-pages-when-sending-data-to-aam}

In dit document worden verschillende aanbevolen procedures beschreven die u moet volgen en waarvan u op de hoogte bent wanneer u gegevens verzendt van [!UICONTROL Single Page Applications] (SPA) naar Adobe Audience Manager (AAM). Dit document richt zich op het gebruiken [!UICONTROL Experience Platform Launch], die de geadviseerde implementatiemethode is.

## Aanvankelijke notities

* Bij de onderstaande items wordt ervan uitgegaan dat u gebruikt [!DNL Platform Launch] om deze te implementeren op uw site. De overwegingen zouden nog bestaan als u niet gebruikt, [!DNL Platform Launch]maar u zou hen aan uw implementatiemethode moeten aanpassen.
* Alle SPA zijn verschillend, zodat kunt u sommige volgende punten moeten aanpassen om aan uw behoefte te voldoen, maar wij wilden sommige beste praktijken met u delen; dingen waar u over moet denken aangezien u gegevens van SPA pagina&#39;s naar Audience Manager verzendt.

## Eenvoudig diagram van het werken met SPA en AAM in Experience Platform Launch {#simple-diagram-of-working-with-spas-and-aam-in-experience-platform-launch}

![spa voor am in [!DNL launch]](assets/spa_for_aam_in_launch.png)

>[!NOTE]
>Zoals vermeld, is dit een vereenvoudigd diagram van hoe SPA pagina&#39;s in een implementatie van Adobe Audience Manager (zonder Adobe Analytics) het gebruiken worden behandeld [!DNL Platform Launch]. Zoals u kunt zien, is het vrij recht-voorwaarts, met het grote besluit is hoe u een meningsverandering (of een actie) aan gaat meedelen [!DNL Platform Launch].

## Triggeren [!DNL Launch] vanaf de SPA pagina {#triggering-launch-from-the-spa-page}

Twee van de gemeenschappelijkere methodes om een regel in teweeg te brengen [!DNL Platform Launch] (en daarom het verzenden van gegevens in Audience Manager), zijn:

* Aangepaste JavaScript-gebeurtenissen instellen (zie voorbeeld [HIER](https://helpx.adobe.com/analytics/kt/using/spa-analytics-best-practices-feature-video-use.html) met Adobe Analytics)
* Een [!UICONTROL Direct Call Rule]

In dit voorbeeld gaan we een Audience Manager gebruiken [!UICONTROL Direct Call rule] [!DNL Launch] om de hit te laten Audience Managers. Zoals u in de volgende secties zult zien, wordt dit heel handig als u de waarde instelt [!UICONTROL Data Layer] op een nieuwe waarde, zodat de waarde door de [!UICONTROL Data Element] in kan worden opgepakt [!DNL Platform Launch].

## Demopagina {#demo-page}

Wij hebben een kleine demopagina gecreeerd die aantoont veranderend een waarde in het [!DNL data layer] en het verzenden van het in AAM, zoals u op een SPA pagina kunt doen. Deze functionaliteit kan worden gemodelleerd voor uitgebreidere wijzigingen die nodig zijn. U kunt deze demopagina [HIER](https://aam.enablementadobe.com/SPA-Launch.html)vinden.

## De instelling [!DNL data layer] {#setting-the-data-layer}

Zoals vermeld, wanneer de nieuwe inhoud op de pagina wordt geladen of wanneer iemand een actie op de plaats uitvoert, [!DNL data layer] moet dynamisch in het hoofd van de pagina worden geplaatst VOORDAT [!DNL Launch] wordt geroepen en [!UICONTROL rules]in werking stelt, zodat [!DNL Platform Launch] kan de nieuwe waarden van [!DNL data layer] en hen in Audience Manager duwen.

Als u naar de hierboven vermelde demosite gaat en naar de paginabron kijkt, ziet u:

* Het [!DNL data layer] bevindt zich in het hoofd van de pagina, vóór de oproep aan [!DNL Platform Launch]
* Het JavaScript in de gesimuleerde SPA-koppeling wijzigt de methode [!UICONTROL Data Layer]en roept vervolgens [!DNL Platform Launch] (de aanroep _satellite.track()) aan. Als u in plaats van deze aangepaste JavaScript-gebeurtenissen gebruikte, [!UICONTROL Direct Call Rule]is de les hetzelfde. Wijzig eerst de naam [!DNL data layer]en bel vervolgens [!DNL Launch].

>[!VIDEO](https://video.tv.adobe.com/v/23322/?quality=12)

## Additional Resources {#additional-resources}

* [SPA discussie over de forums van de Adobe](https://forums.adobe.com/thread/2451022)
* [Referentie Architectuur plaatsen om te tonen hoe te om SPA in Launch by Adobe uit te voeren](https://helpx.adobe.com/experience-manager/kt/integration/using/launch-reference-architecture-SPA-tutorial-implement.html)
* [Best practices gebruiken bij het bijhouden van SPA in Adobe Analytics](https://helpx.adobe.com/analytics/kt/using/spa-analytics-best-practices-feature-video-use.html)
* [Demopsite gebruikt voor dit artikel](https://aam.enablementadobe.com/SPA-Launch.html)
