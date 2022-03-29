---
title: IAB TCF 2.0-ondersteuning
description: Meer informatie over de plug-in Audience Manager in IAB TCF en over de manier waarop deze werkt met het aanmeldingsobject van Adobe en de CMP (Consent Management Provider).
feature: Data Governance & Privacy
activity: implement
doc-type: technical video
team: Technical Marketing
thumbnail: 26434.jpg
kt: 5027
role: Developer, Data Engineer, Architect
level: Experienced
exl-id: 04b4e786-0457-4dcc-bcf9-a79eda67bb2e
source-git-commit: 62b43b5627dabf754cf821f974a56c60989ef7ef
workflow-type: tm+mt
source-wordcount: '1078'
ht-degree: 0%

---

# IAB TCF 2.0 steun in Audience Manager {#iab-tcf-support-in-audience-manager}

Adobe voorziet u van de middelen om de privacykeuzen van uw gebruikers te beheren en mee te delen door de Opt-in functionaliteit en door de Plug-in van de Audience Manager aan de Transparantie van IAB en de Steun van het Kader 2.0 van de Goedkeuring (TCF 2.0). Dit artikel werkt samen met de documentatie om u te helpen de Plug-in van de Audience Manager aan IAB TCF begrijpen en hoe het samen met het Opt-in voorwerp van Adobe en uw Bevelhebber van het Beheer van de Toestemming (CMP) werkt. Om meer over IAB te leren, gelieve hun Website te zien bij [https://www.iabeurope.eu/](https://www.iabeurope.eu/).

## Eerste stap: De Experience Cloud-id-aanmelding begrijpen {#first-step-understand-ecid-s-opt-in}

Om te begrijpen hoe te met IAB TCF te werken, moet u eerst begrijpen [!DNL Opt-in] -functionaliteit, die onderdeel is van de Experience Cloud ID Service-bibliotheek (ECID). Als u niet bekend bent met de werking van de aanmeldingsprocedure, raadpleegt u [dit nuttige artikel](https://experienceleague.adobe.com/docs/core-services-learn/tutorials/id-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html) eerst. U moet ook de optie Inschakelen bekijken [documentatie](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html). Als u deze bronnen hebt doorlopen, gaat u terug naar deze pagina en gaat u verder.

## De plug-in Audience Manager voor IAB TCF {#the-audience-manager-plug-in-for-iab-tcf}

Nu u minstens een basisbegrip van hebt hoe de Opt-in dienst werkt, kan de Audience Manager op het laag [!DNL IAB Transparency and Consent Framework (TCF)] ondersteuning, die via een insteekmodule in het object Opt-in wordt uitgevoerd.

De insteekmodule van de Audience Manager voor IAB TCF breidt de functionaliteit van toe Opt-binnen uit, en laat AAM klanten toe om, keuzes van de gebruikersprivacy aan stroomafwaartse partners in overeenstemming met IAB TCF te evalueren, te respecteren en door:sturen. Het verstrekt een norm die gegevenscontrolemechanismen (dat u als klant van Adobe bent) en verkopers (DMPs, DSP, SSPs, Advertentieservers, enz.) kan worden gebruikt om instemming in het hele toestemmingslandschap te begrijpen.

## IAB TCF inschakelen {#enabling-iab-tcf}

Het inschakelen van de plug-in Audience Manager voor IAB TCF is eenvoudig als u Adobe Experience Platform Launch gebruikt, omdat dit een eenvoudig selectievakje is, zoals in de korte video hieronder wordt getoond:

>[!VIDEO](https://video.tv.adobe.com/v/26433/?quality=12)

Als u echter geen Launch gebruikt, kunt u `isIabContext=true` om het toe te laten wanneer u de Bezoeker van de Experience Cloud concretiseert. Dit stelt de stroom IAB TCF in werking, d.w.z. voegt een andere stap aan toestemmingsinzameling toe, gebruikend IAB TCF om voor het koord te vragen IAB TC en het terug te verstrekken aan Opt-binnen, die dan dan met de oplossingen van Experience Cloud communiceert.

## IAB TC-tekenreeks {#iab-tcf-consent-string}

Een van de standaarden die IAB biedt, is een &quot;toestemmingstekenreeks&quot; (ook wel een &quot;DaisyBit&quot; genoemd), die eigenlijk twee lijsten zijn die worden samengesteld:

1. Doel: **Wat** wordt hiervoor toestemming gegeven ?
1. Leveranciers: **Wie** wordt er toestemming gegeven ?

### Doelstellingen {#purposes}

Met IAB TCF 2.0, zijn er tien &quot;doeleinden&quot;waarvoor om toestemming te verzamelen (wat de verkopers met de gegevens van de bezoeker kunnen doen). Adobe Audience Manager vereist niet alle tien, maar alleen toestemming voor de volgende doeleinden, naast toestemming van de leverancier:

* **Doel 1:** Informatie over een apparaat opslaan en/of openen;
* **Doelstelling 10:** Producten ontwikkelen en verbeteren;
* **Speciaal doel 1:** Zorgen voor beveiliging, fraude voorkomen en fouten opsporen.

Dit is het eerste deel van de IAB TC-tekenreeks en wordt alleen opgenomen als een getal van 1 en 0, waarbij wordt voorgeschreven of dat doel of die activiteit wordt goedgekeurd of niet.

>[!NOTE]
>
>Conform IAB-regels is Speciale doelstelling 1 (Beveiliging, Fraude voorkomen en fouten opsporen) altijd goedgekeurd en kunnen gebruikers er geen bezwaar tegen maken.

### Leveranciers {#vendors}

Een ander deel van de IAB TC-reeks bestaat uit een lange lijst met honderden leveranciers, zodat bezoekers een lijst kunnen krijgen met relevante leveranciers die tags op de site hebben en kunnen kiezen welke leveranciers u wilt gebruiken. Leveranciers behouden hun plaats in de lijst. Het Adobe Audience Manager-leveranciernummer in deze lijst is bijvoorbeeld 565. Als dat nummer in de lijst een &#39;1&#39; heeft, kan de Audience Manager de goedgekeurde doeleinden uitvoeren vanaf de voorkant van de lijst. Als de vlek van AAM &quot;0&quot;heeft, kan het niets met de gegevens doen.

**Voor Audience Manager om een UI voor klanten te verstrekken om IAB TCF te gebruiken om deze doeleinden en verkopers te kiezen, of om al activiteit goed te keuren/af te keuren, moet u een partner gebruiken CMP die met IAB TCF wordt geregistreerd of bouwt die IAB TCF steunt en met IAB TCF wordt geregistreerd.**

## Inschakelen: Vertalen tussen IAB- en Adobe-toepassingen {#opt-in-translating-between-iab-and-adobe-solutions}

Een van de voordelen van het gebruik van IAB TCF is dat de hierboven vermelde standaarddoeleinden de eindgebruiker waarschijnlijk meer van een idee van geven wat zij dan een lijst van Adobe oplossingen goedkeuren. Eindgebruikers weten wellicht niet wat het betekent &quot;goedkeuren&quot; Audience Manager of [!DNL Target], maar &quot;Opslaan en/of toegang krijgen tot informatie over een apparaat&quot; of &quot;Ontwikkelen en verbeteren van producten&quot; is voor hen waarschijnlijk eenvoudiger te begrijpen en te accepteren.

Om de Audience Manager te kunnen goedkeuren (d.w.z. om ervoor te zorgen dat de IAB-doeleinden voor Opt-in AAM &quot;ja&quot;-stem uitbrengen), moeten de doelstellingen 1 en 10, zoals hierboven vermeld, door de eindgebruiker worden goedgekeurd. Als een van deze twee opties niet is goedgekeurd of als een finder niet is goedgekeurd, worden AAM geen pixelbranden uitgevoerd of cookies ingesteld. Het is ook goed om te weten dat veel klanten er gewoon voor kiezen om de eindgebruiker een interface &quot;alles of niets&quot; te bieden, die het gebruik van Audience Manager (en de andere Experience Cloud-oplossingen) natuurlijk wel of niet toestaat.

Er staat veel informatie in de [documentatie](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/consent-management/aam-iab-plugin.html?lang=en) over hoe de Audience Manager Plug-In voor IAB TCF stroom op zowel Uitgever als Advertiser gebruiksgevallen van toepassing is.

## IAB: Goedkeuring achteraf verzenden {#iab-sending-consent-downstream}

Wanneer de insteekmodule van de Audience Manager voor IAB TCF wordt gebruikt, zullen de de toestemmingskeuzen van de gebruiker ook naar platform-niveau (derde partij) de syncs van identiteitskaart voor partners worden verzonden die op de Globale Lijst van de Leverancier aanwezig zijn, zodat de partner de informatie van de gebruikerstoestemming heeft en op het kan ook handelen. Deze informatie wordt in twee variabelen verzonden:

* gdpr = 1
* gdpr_permission = [gecodeerde tekenreeks voor toestemming]

Het voorbehoud is dat als de gebruiker in IAB-context is en geen toestemming verleent (of negatieve toestemming verleent), dan de Audience Manager helemaal niet de koord IAB TC verzamelt, en als dusdanig de vraag laat vallen. Dus in dat geval... geen toestemming voorbij.

## Demo {#demo}

In de onderstaande video ziet u hoe cookies en bakens van ECID en oplossingen worden beïnvloed door de keuzeselecties van de IAB-gebruiker.

>[!VIDEO](https://video.tv.adobe.com/v/26434/?quality=12)

Voor meer gedetailleerde informatie over de Audience Manager Plug-In voor IAB TCF 2.0, met inbegrip van hoe te om uit te voeren en te testen, te gebruiken gevallen, en werkschema, gelieve te zien [documentatie](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/consent-management/aam-iab-plugin.html).
