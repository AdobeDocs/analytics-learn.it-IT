---
title: Utilizzo di un livello dati per impostare il nome della pagina e altre variabili in  Adobe Analytics tramite Launch
description: È consigliabile utilizzare un livello dati per Analytics e altre soluzioni  Experienci Cloud. Questo video illustra come estrarre i valori dal livello dati e usarli in Launch per compilare le variabili in  Adobe Analytics.
feature: launch implementation
topics: null
audience: implementer
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1852
translation-type: tm+mt
source-git-commit: ee6c03cff5b051d9293d75965e9fd98f151d7fce
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Utilizzo di un livello dati per impostare il nome della pagina e altre variabili tramite [!DNL Experience Platform Launch] {#using-a-data-layer-to-set-page-name-and-other-variables-in-adobe-analytics-via-launch}

È consigliabile utilizzare un livello dati per [!DNL Analytics] e altre soluzioni  Experienci Cloud. Questo video illustra come estrarre i valori dal livello dati e utilizzarli [!DNL Experience Platform Launch] per comporre le variabili in  Adobe Analytics.

## Livelli dati {#data-layers}

È consigliabile utilizzare un livello dati quando si utilizzano dati sul sito e soluzioni Adobe Experience Cloud, in particolare con  Adobe Analytics. Un livello __ dati è un framework di oggetti JavaScript che gli sviluppatori inseriscono nelle pagine. I livelli di dati possono essere utilizzati dagli strumenti di tracciamento (compresi i sistemi di gestione tag come [!DNL Experience Platform Launch]) per compilare i rapporti. Ulteriori informazioni sui livelli di dati sono disponibili nella documentazione [del Experience Cloud](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-data-layer.html) o sul sito [](https://www.w3.org/)W3C.

Inoltre, consultate il blog [Data Layers (Livelli dati del blog): Da Buzzword a Best Practice,](https://theblog.adobe.com/data-layers-buzzword-best-practice/)che offre informazioni sui livelli di dati, oltre a un paio di esempi.

## Livelli dati [!DNL Experience Platform Launch]e  Adobe Analytics (oh my?){#data-layers-launch-and-adobe-analytics-oh-my}

1. Crea uno standard per i livelli dati da utilizzare sul tuo sito, a cui può fare riferimento [!DNL Experience Platform Launch].

   1. Posiziona questo livello dati il più possibile in alto nella parte superiore della pagina, prima della chiamata a [!DNL Experience Platform Launch], in modo che i valori possano essere utilizzati immediatamente da [!DNL Launch]e da soluzioni di Adobe che devono essere alte sulla pagina, come  Adobe Target.

1. Compilare i dati nel livello dati.
1. In [!DNL Experience Platform Launch], create &quot;[!UICONTROL data elements]&quot; che faccia riferimento ai punti dati nel livello dati e che possa essere utilizzato in tutto [!DNL Experience Platform Launch] il [!UICONTROL rules], [!UICONTROL extensions]e così via.
1. Utilizzate le variabili globali [!UICONTROL data elements] dell&#39; [!DNL Analytics] estensione o in una regola, assegnando i valori a [!UICONTROL props], [!UICONTROL eVars], [!UICONTROL pageName]o altre [!DNL Analytics] variabili.
1. Attiva un beacon in cui vengono inviati i dati [!DNL Analytics].

Il seguente video illustra le procedure da seguire.

>[!VIDEO](https://video.tv.adobe.com/v/25899/?quality=12)
