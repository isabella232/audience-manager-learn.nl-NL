---
title: IAB TCF 2.0 Steun in Audience Manager
description: Adobe voorziet u van de middelen om de privacykeuzen van uw gebruikers te beheren en mee te delen door de Opt-in functionaliteit en door de Plug-in van de Audience Manager aan de Transparantie van IAB en de Steun van het Kader 2.0 van de Goedkeuring (TCF 2.0). Dit artikel werkt samen met de documentatie om u te helpen de Plug-in van de Audience Manager aan IAB TCF begrijpen en hoe het samen met het Opt-in voorwerp van Adobe en uw Bevelhebber van het Beheer van de Toestemming (CMP) werkt.
feature: Data Governance & Privacy
activity: implement
doc-type: technical video
team: Technical Marketing
thumbnail: 26434.jpg
kt: 5027
role: Developer, Data Engineer, Architect
level: Experienced
exl-id: 04b4e786-0457-4dcc-bcf9-a79eda67bb2e
source-git-commit: 086071ab04551c512c5415f091a8054123bc6445
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# IAB TCF 2.0 Steun in Audience Manager {#iab-tcf-support-in-audience-manager}

Adobe voorziet u van de middelen om de privacykeuzen van uw gebruikers te beheren en mee te delen door de Opt-in functionaliteit en door de Plug-in van de Audience Manager aan de Transparantie van IAB en de Steun van het Kader 2.0 van de Goedkeuring (TCF 2.0). Dit artikel werkt samen met de documentatie om u te helpen de Plug-in van de Audience Manager aan IAB TCF begrijpen en hoe het samen met het Opt-in voorwerp van Adobe en uw Bevelhebber van het Beheer van de Toestemming (CMP) werkt. Voor meer informatie over IAB, gelieve hun Website op [https://www.iabeurope.eu/](https://www.iabeurope.eu/) te zien.

## Eerste stap: Inschakelen van ECID begrijpen {#first-step-understand-ecid-s-opt-in}

Om te begrijpen hoe te met IAB TCF te werken, moet u [!DNL Opt-in] functionaliteit eerst begrijpen, die deel van de Experience Cloud ID van de Dienst (ECID) bibliotheek uitmaakt. Als u niet bekend bent met de werking van Opt-in, zie [dit nuttige artikel](https://experienceleague.adobe.com/docs/core-services-learn/tutorials/id-service/use-opt-in-to-control-experience-cloud-activities-based-on-user-consent.html) eerst. U moet ook de documentatie [Opt-in](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html) controleren. Als u deze bronnen hebt doorlopen, gaat u terug naar deze pagina en gaat u verder.

## De plug-in Audience Manager voor IAB TCF {#the-audience-manager-plug-in-for-iab-tcf}

Nu u minstens een basisinzicht in hebt hoe de Opt-in dienst werkt, kan de Audience Manager op het [!DNL IAB Transparency and Consent Framework (TCF)] steun in lagen, die via een stop-binnen in het Opt-in voorwerp wordt gedaan.

De insteekmodule van de Audience Manager voor IAB TCF breidt de functionaliteit van toe Opt-binnen uit, en laat AAM klanten toe om, keuzes van de gebruikersprivacy aan stroomafwaartse partners in overeenstemming met IAB TCF te evalueren, te respecteren en door:sturen. Het verstrekt een norm die gegevenscontrolemechanismen (dat u als klant van Adobe bent) en verkopers (DMPs, DSP, SSPs, Advertentieservers, enz.) kan worden gebruikt om instemming in het hele toestemmingslandschap te begrijpen.

## IAB TCF inschakelen {#enabling-iab-tcf}

Het inschakelen van de plug-in Audience Manager voor IAB TCF is eenvoudig als u Adobe Experience Platform Launch gebruikt, omdat dit een eenvoudig selectievakje is, zoals in de korte video hieronder wordt getoond:

>[!VIDEO](https://video.tv.adobe.com/v/26433/?quality=12)

U kunt `isIabContext=true` ook gebruiken om Launch in te schakelen wanneer u de Experience Cloud Bezoeker instantieert. Dit stelt de stroom IAB TCF in werking, d.w.z. voegt een andere stap aan toestemmingsinzameling toe, gebruikend IAB TCF om voor het koord te vragen IAB TC en het terug te verstrekken aan Opt-binnen, die dan dan met de oplossingen van Experience Cloud communiceert.

## IAB TC-tekenreeks {#iab-tcf-consent-string}

Een van de standaarden die IAB biedt, is een &quot;toestemmingstekenreeks&quot; (ook wel een &quot;DaisyBit&quot; genoemd), die eigenlijk twee lijsten zijn die worden samengesteld:

1. Doel: **Waarvoor wordt toestemming gegeven?**
1. Leveranciers: **Aan wie wordt toestemming gegeven?**

### Doelstellingen {#purposes}

Met IAB TCF 2.0, zijn er tien &quot;doeleinden&quot;waarvoor om toestemming te verzamelen (wat de verkopers met de gegevens van de bezoeker kunnen doen). Adobe Audience Manager vereist niet alle tien, maar alleen toestemming voor de volgende doeleinden, naast toestemming van de leverancier:

* **Doelstelling 1:Informatie** opslaan en/of openen op een apparaat;
* **Doelstelling 10:** Producten ontwikkelen en verbeteren;
* **Speciaal doel 1:** Zorgen voor beveiliging, fraude voorkomen en fouten opsporen.

Dit is het eerste deel van de IAB TC-tekenreeks en wordt alleen opgenomen als een getal van 1 en 0, waarbij wordt voorgeschreven of dat doel of die activiteit wordt goedgekeurd of niet.

>[!NOTE]
>
>Conform IAB-regels is Speciale doelstelling 1 (Beveiliging, Fraude voorkomen en fouten opsporen) altijd goedgekeurd en kunnen gebruikers er geen bezwaar tegen maken.

### Leveranciers {#vendors}

Een ander deel van de IAB TC-reeks bestaat uit een lange lijst met honderden leveranciers, zodat bezoekers een lijst kunnen krijgen met relevante leveranciers die tags op de site hebben en kunnen kiezen welke leveranciers u wilt gebruiken. Leveranciers behouden hun plaats in de lijst. Het Adobe Audience Manager-leveranciernummer in deze lijst is bijvoorbeeld 565. Als dat nummer in de lijst een &#39;1&#39; heeft, kan de Audience Manager de goedgekeurde doeleinden uitvoeren vanaf de voorkant van de lijst. Als de vlek van AAM &quot;0&quot;heeft, kan het niets met de gegevens doen.

**Voor Audience Manager om een UI voor klanten te verstrekken om IAB TCF te gebruiken om deze doeleinden en verkopers te kiezen, of om al activiteit goed te keuren/af te keuren, moet u een partner gebruiken CMP die met IAB TCF wordt geregistreerd of bouwt die IAB TCF steunt en met IAB TCF wordt geregistreerd.**

## Inschakelen: Omzetten tussen IAB- en Adobe-oplossingen {#opt-in-translating-between-iab-and-adobe-solutions}

Een van de voordelen van het gebruik van IAB TCF is dat de hierboven vermelde standaarddoeleinden de eindgebruiker waarschijnlijk meer van een idee van geven wat zij dan een lijst van Adobe oplossingen goedkeuren. Eindgebruikers weten wellicht niet wat het betekent om Audience Manager of [!DNL Target] goed te keuren, maar &quot;Opslaan en/of toegang krijgen tot informatie over een apparaat&quot; of &quot;Producten ontwikkelen en verbeteren&quot; is voor hen waarschijnlijk eenvoudiger om te begrijpen en ermee in te stemmen.

Om de Audience Manager te kunnen goedkeuren (d.w.z. om ervoor te zorgen dat de IAB-doeleinden voor Opt-in AAM &quot;ja&quot;-stem uitbrengen), moeten de doelstellingen 1 en 10, zoals hierboven vermeld, door de eindgebruiker worden goedgekeurd. Als een van deze twee opties niet is goedgekeurd of als een finder niet is goedgekeurd, worden AAM geen pixelbranden uitgevoerd of cookies ingesteld. Het is ook goed om te weten dat veel klanten er gewoon voor kiezen om de eindgebruiker een interface &quot;alles of niets&quot; te bieden, die het gebruik van Audience Manager (en de andere Experience Cloud-oplossingen) natuurlijk wel of niet toestaat.

Er is één of andere grote informatie in [documentatie](https://marketing.adobe.com/resources/help/en_US/aam/aam-iab-plugin.html) over hoe de stroom van de Plug-in van de Audience Manager voor IAB TCF op zowel Uitgever als Advertiser van toepassing is.

## IAB: Goedkeuring Downstream verzenden {#iab-sending-consent-downstream}

Wanneer de insteekmodule van de Audience Manager voor IAB TCF wordt gebruikt, zullen de de toestemmingskeuzen van de gebruiker ook naar platform-niveau (derde partij) de syncs van identiteitskaart voor partners worden verzonden die op de Globale Lijst van de Leverancier aanwezig zijn, zodat de partner de informatie van de gebruikerstoestemming heeft en op het kan ook handelen. Deze informatie wordt in twee variabelen verzonden:

* gdpr = 1
* gdpr_agreement = [gecodeerde toestemmstring]

Het voorbehoud is dat als de gebruiker in IAB-context is en geen toestemming verleent (of negatieve toestemming verleent), dan de Audience Manager helemaal niet de koord IAB TC verzamelt, en als dusdanig de vraag laat vallen. Dus in dat geval... geen toestemming voorbij.

## Demo {#demo}

In de onderstaande video ziet u hoe cookies en bakens van ECID en oplossingen worden beïnvloed door de keuzeselecties van de IAB-gebruiker.

>[!VIDEO](https://video.tv.adobe.com/v/26434/?quality=12)

Raadpleeg de [documentatie](https://experienceleague.adobe.com/docs/audience-manager/user-guide/overview/data-privacy/consent-management/aam-iab-plugin.html) voor meer informatie over de plug-in Audience Manager voor IAB TCF 2.0, zoals het implementeren en testen, gebruiken en het werken.
