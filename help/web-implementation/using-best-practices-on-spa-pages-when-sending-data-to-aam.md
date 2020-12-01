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


# Best practices gebruiken op SPA pagina&#39;s bij het verzenden van gegevens naar AAM {#using-best-practices-on-spa-pages-when-sending-data-to-aam}

In dit document worden verschillende aanbevolen procedures beschreven die u moet volgen en waarvan u zich bewust bent wanneer u gegevens verzendt van [!UICONTROL Single Page Applications] (SPA) naar Adobe Audience Manager (AAM). Dit document richt zich op het gebruiken van [!UICONTROL Experience Platform Launch], die de geadviseerde implementatiemethode is.

## Aanvankelijke notities

* Bij de onderstaande items wordt ervan uitgegaan dat u [!DNL Platform Launch] gebruikt om te implementeren op uw site. De overwegingen zouden nog bestaan als u [!DNL Platform Launch] niet gebruikt, maar u zou hen aan uw implementatiemethode moeten aanpassen.
* Alle SPA zijn verschillend, zodat kunt u sommige volgende punten moeten aanpassen om aan uw behoefte te voldoen, maar wij wilden sommige beste praktijken met u delen; dingen waar u over moet denken aangezien u gegevens van SPA pagina&#39;s naar Audience Manager verzendt.

## Eenvoudig diagram van het werken met SPA en AAM in Experience Platform Launch {#simple-diagram-of-working-with-spas-and-aam-in-experience-platform-launch}

![spa voor am in  [!DNL launch]](assets/spa_for_aam_in_launch.png)

>[!NOTE]
>Zoals vermeld, is dit een vereenvoudigd diagram van hoe SPA pagina&#39;s in een implementatie van Adobe Audience Manager (zonder Adobe Analytics) gebruikend [!DNL Platform Launch] worden behandeld. Zoals u kunt zien, is het vrij recht-voorwaarts, met het grote besluit zijn hoe u een meningsverandering (of een actie) aan [!DNL Platform Launch] gaat meedelen.

## [!DNL Launch] triggeren van de SPA pagina {#triggering-launch-from-the-spa-page}

Twee van de gemeenschappelijkere methodes om een regel in [!DNL Platform Launch] (en daarom het verzenden van gegevens naar Audience Manager) teweeg te brengen, zijn:

* Aangepaste JavaScript-gebeurtenissen instellen (zie voorbeeld [HERE](https://helpx.adobe.com/analytics/kt/using/spa-analytics-best-practices-feature-video-use.html) met Adobe Analytics)
* Een [!UICONTROL Direct Call Rule] gebruiken

In dit voorbeeld van Audience Manager, gaan wij [!UICONTROL Direct Call rule] in [!DNL Launch] gebruiken om de slag te teweegbrengen die in Audience Manager gaat. Zoals u in de volgende secties zult zien, wordt dit echt nuttig door [!UICONTROL Data Layer] aan een nieuwe waarde te plaatsen, zodat het door [!UICONTROL Data Element] in [!DNL Platform Launch] kan worden opgenomen.

## Demopagina {#demo-page}

Wij hebben een kleine demopagina gecreeerd die aantoont veranderend een waarde in [!DNL data layer] en verzendend het in AAM, zoals u op een SPA pagina kunt doen. Deze functionaliteit kan worden gemodelleerd voor uitgebreidere wijzigingen die nodig zijn. U kunt deze demopagina [HERE](https://aam.enablementadobe.com/SPA-Launch.html) vinden.

## De [!DNL data layer] {#setting-the-data-layer} instellen

Zoals vermeld, wanneer nieuwe inhoud op de pagina wordt geladen of wanneer iemand een actie op de plaats uitvoert, moet [!DNL data layer] dynamisch in de koptekst van de pagina worden geplaatst VOORDAT [!DNL Launch] wordt geroepen en [!UICONTROL rules] in werking stelt, zodat [!DNL Platform Launch] de nieuwe waarden van [!DNL data layer] kan opnemen en hen in Audience Manager duwen.

Als u naar de hierboven vermelde demosite gaat en naar de paginabron kijkt, ziet u:

* De [!DNL data layer] bevindt zich in de kop van de pagina, vóór de aanroep van [!DNL Platform Launch]
* Het JavaScript in de gesimuleerde SPA koppeling wijzigt de [!UICONTROL Data Layer] en roept vervolgens [!DNL Platform Launch] (de aanroep _satellite.track()) aan. Als u aangepaste JavaScript-gebeurtenissen gebruikte in plaats van [!UICONTROL Direct Call Rule], is de les hetzelfde. Wijzig eerst [!DNL data layer] en roep vervolgens [!DNL Launch].

>[!VIDEO](https://video.tv.adobe.com/v/23322/?quality=12)

## Aanvullende bronnen {#additional-resources}

* [SPA discussie over de forums van de Adobe](https://forums.adobe.com/thread/2451022)
* [Referentie Architectuur plaatsen om te tonen hoe te om SPA in Launch by Adobe uit te voeren](https://helpx.adobe.com/experience-manager/kt/integration/using/launch-reference-architecture-SPA-tutorial-implement.html)
* [Best practices gebruiken bij het bijhouden van SPA in Adobe Analytics](https://helpx.adobe.com/analytics/kt/using/spa-analytics-best-practices-feature-video-use.html)
* [Demopsite gebruikt voor dit artikel](https://aam.enablementadobe.com/SPA-Launch.html)
