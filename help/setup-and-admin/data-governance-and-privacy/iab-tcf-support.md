---
title: IAB TCF 2.0 Steun in Audience Manager
description: Adobe voorziet u van de middelen om de privacykeuzen van uw gebruikers te beheren en mee te delen door de Opt-in functionaliteit en door de Plug-in van de Audience Manager aan de Transparantie van IAB en de Steun van het Kader 2.0 van de Goedkeuring (TCF 2.0). Dit artikel werkt samen met de documentatie om u te helpen de Plug-in van de Audience Manager aan IAB TCF begrijpen en hoe het samen met het Opt-in voorwerp van Adobe en uw Bevelhebber van het Beheer van de Toestemming (CMP) werkt.
feature: data governance & privacy
topics: null
audience: implementer, architect
activity: implement
doc-type: technical video
team: Technical Marketing
thumbnail: 26434.jpg
kt: 5027
translation-type: tm+mt
source-git-commit: df8afb50ed3971dc47e6506d31a8222a7f488b25
workflow-type: tm+mt
source-wordcount: '1123'
ht-degree: 0%

---


# IAB TCF 2.0 Steun in Audience Manager {#iab-tcf-support-in-audience-manager}

Adobe voorziet u van de middelen om de privacykeuzen van uw gebruikers te beheren en mee te delen door de Opt-in functionaliteit en door de Plug-in van de Audience Manager aan de Transparantie van IAB en de Steun van het Kader 2.0 van de Goedkeuring (TCF 2.0). Dit artikel werkt samen met de documentatie om u te helpen de Plug-in van de Audience Manager aan IAB TCF begrijpen en hoe het samen met het Opt-in voorwerp van Adobe en uw Bevelhebber van het Beheer van de Toestemming (CMP) werkt. Voor meer informatie over IAB, te zien gelieve hun Website in [https://www.iabeurope.eu/](https://www.iabeurope.eu/).

## Eerste stap: Inschakelen van ECID begrijpen {#first-step-understand-ecid-s-opt-in}

Om te begrijpen hoe te met IAB TCF te werken, moet u [!DNL Opt-in] functionaliteit eerst begrijpen, die deel van de bibliotheek van de Dienst van Experience Cloud ID (ECID) uitmaakt. Als u niet bekend bent met de werking van Opt-in, raadpleeg dan eerst [dit handige artikel](https://docs.adobe.com/content/help/en/core-services-learn/tutorials/id-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html) . U moet ook de [documentatie](https://docs.adobe.com/content/help/nl-NL/id-service/using/implementation/opt-in-service/optin-overview.html)van Inschakelen controleren. Als u deze bronnen hebt doorlopen, gaat u terug naar deze pagina en gaat u verder.

## The Audience Manager Plug-In for IAB TCF {#the-audience-manager-plug-in-for-iab-tcf}

Nu u minstens een basisinzicht in hebt hoe de Opt-in dienst werkt, kan de Audience Manager op het [!DNL IAB Transparency and Consent Framework (TCF)] steun in lagen, die via een stop-binnen in het Opt-in voorwerp wordt gedaan.

De insteekmodule van de Audience Manager voor IAB TCF breidt de functionaliteit van toe Opt-binnen uit, en laat AAM klanten toe om, keuzes van de gebruikersprivacy aan stroomafwaartse partners in overeenstemming met IAB TCF te evalueren, te respecteren en door:sturen. Het verstrekt een norm die gegevenscontrolemechanismen (dat u als klant van Adobe bent) en verkopers (DMPs, DSP, SSPs, Advertentieservers, enz.) kan worden gebruikt om instemming in het hele toestemmingslandschap te begrijpen.

## IAB TCF inschakelen {#enabling-iab-tcf}

Het inschakelen van de plug-in Audience Manager voor IAB TCF is eenvoudig als u Adobe Experience Platform Launch gebruikt, omdat dit een eenvoudig selectievakje is, zoals in de korte video hieronder wordt getoond:

>[!VIDEO](https://video.tv.adobe.com/v/26433/?quality=12)

Als u echter niet de functie Starten gebruikt, kunt u deze ook inschakelen wanneer u de Experience Cloud-bezoeker instantieert. `isIabContext=true` Dit stelt de stroom IAB TCF in werking, d.w.z. voegt een andere stap aan toestemmingsinzameling toe, gebruikend IAB TCF om voor het koord te vragen IAB TC en het terug te verstrekken aan Opt-binnen, die dan dan met de oplossingen van Experience Cloud communiceert.

## IAB TC-tekenreeks {#iab-tcf-consent-string}

Een van de standaarden die IAB biedt, is een &quot;toestemmingstekenreeks&quot; (ook wel een &quot;DaisyBit&quot; genoemd), die eigenlijk twee lijsten zijn die worden samengesteld:

1. Doel: **Wat** is de instemming?
1. Leveranciers: **Aan wie** wordt toestemming gegeven?

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

**Voor Audience Manager om een UI voor klanten te verstrekken om IAB TCF te gebruiken om deze doeleinden en verkopers te kiezen, of al activiteit goed te keuren/af te keuren, moet u een partner gebruiken CMP die met IAB TCF wordt geregistreerd of bouwt die IAB TCF steunt en met IAB TCF wordt geregistreerd.**

## Inschakelen: Omzetten tussen IAB- en Adobe-oplossingen {#opt-in-translating-between-iab-and-adobe-solutions}

Een van de voordelen van het gebruik van IAB TCF is dat de hierboven vermelde standaarddoeleinden de eindgebruiker waarschijnlijk meer van een idee van geven wat zij dan een lijst van Adobe oplossingen goedkeuren. Eindgebruikers weten wellicht niet wat het betekent om Audience Manager goed te keuren of [!DNL Target], maar &quot;Opslaan en/of toegang krijgen tot informatie over een apparaat&quot; of &quot;Producten ontwikkelen en verbeteren&quot; is voor hen waarschijnlijk eenvoudiger om te begrijpen en ermee in te stemmen.

Om de Audience Manager te kunnen goedkeuren (d.w.z. om ervoor te zorgen dat de IAB-doeleinden voor Opt-in AAM &quot;ja&quot;-stem uitbrengen), moeten de doelstellingen 1 en 10, zoals hierboven vermeld, door de eindgebruiker worden goedgekeurd. Als een van deze twee opties niet is goedgekeurd of als een finder niet is goedgekeurd, worden AAM geen pixelbranden uitgevoerd of cookies ingesteld. Het is ook goed om te weten dat veel klanten er gewoon voor kiezen om de eindgebruiker een interface &quot;alles of niets&quot; te bieden, die het gebruik van Audience Manager (en de andere Experience Cloud-oplossingen) natuurlijk wel of niet toestaat.

Er is wat grote informatie in de [documentatie](https://marketing.adobe.com/resources/help/en_US/aam/aam-iab-plugin.html) over hoe de Audience Manager Plug-In voor IAB TCF stroom op zowel Uitgever als Advertiser gebruiksgevallen van toepassing is.

## IAB: Goedkeuring Downstream verzenden {#iab-sending-consent-downstream}

Wanneer de insteekmodule van de Audience Manager voor IAB TCF wordt gebruikt, zullen de de toestemmingskeuzen van de gebruiker ook naar platform-niveau (derde partij) de syncs van identiteitskaart voor partners worden verzonden die op de Globale Lijst van de Leverancier aanwezig zijn, zodat de partner de informatie van de gebruikerstoestemming heeft en op het kan ook handelen. Deze informatie wordt in twee variabelen verzonden:

* gdpr = 1
* gdpr_agreement = [gecodeerde toestemmingstekenreeks]

Het voorbehoud is dat als de gebruiker in IAB-context is en geen toestemming verleent (of negatieve toestemming verleent), dan de Audience Manager helemaal niet de koord IAB TC verzamelt, en als dusdanig de vraag laat vallen. Dus in dat geval... geen toestemming voorbij.

## Demo {#demo}

In de onderstaande video ziet u hoe cookies en bakens van ECID en oplossingen worden beïnvloed door de keuzeselecties van de IAB-gebruiker.

>[!VIDEO](https://video.tv.adobe.com/v/26434/?quality=12)

Voor meer gedetailleerde informatie over de stop-binnen van de Audience Manager voor IAB TCF 2.0, met inbegrip van hoe te om uit te voeren en te testen, gebruiksgevallen, en werkschema, te zien gelieve de [documentatie](https://docs.adobe.com/content/help/en/audience-manager/user-guide/overview/data-privacy/consent-management/aam-iab-plugin.html).