---
title: Utilizza un livello dati per impostare le variabili di Analytics tramite Tag
description: Scopri come utilizzare un livello di dati per la determinazione dell’origine dei dati di Analytics e di altre soluzioni di Experience Cloud.
feature: Launch Implementation
role: Developer, Data Engineer
level: Beginner
kt: 1852
thumbnail: 25899.jpg
exl-id: 408ceb47-df05-4456-85bb-0ef2798a05a5
source-git-commit: d78c3351d2a98704396ceb8f84d123dd463befe5
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 10%

---

# Utilizza un livello dati per impostare le variabili di Analytics tramite [!DNL Tags] {#use-a-data-layer-to-set-analytics-variables-in-adobe-analytics-via-tags}

Utilizzo di un livello di dati per [!DNL Analytics] e altre soluzioni di Experience Cloud sono una best practice. In questo video, scopri come estrarre i valori dal livello dati e utilizzarli in [!DNL Experience Platform Tags] per popolare le variabili in Adobe Analytics.

## Livelli dati {#data-layers}

A _livello dati_ è un framework di oggetti JavaScript che gli sviluppatori aggiungono alle pagine web digitali. Le soluzioni Analytics utilizzano infine il livello dati per compilare i rapporti. Sistemi di gestione dei tag, tra cui [!DNL Experience Platform Tags]) sono gli intermediari che leggono il livello dati, mappano i valori alle variabili e inviano tali dati alle soluzioni di esperienza digitale.

Rivedi informazioni aggiuntive sui livelli dati nella sezione [Documentazione di Experience Cloud](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=it) e il blog [Livelli dati: Da Buzzword alle best practice](https://blog.adobe.com/en/2014/03/13/data-layers-buzzword-best-practice).

## Livelli dati, [!DNL Experience Platform Tags]e Adobe Analytics{#data-layers-launch-and-adobe-analytics}

1. Definisci o identifica uno standard del livello dati da utilizzare sul sito.

   1. Posiziona il livello di dati il più in alto possibile nella sezione head della pagina e prima della chiamata a [!DNL Experience Platform Tags]. In questo modo i valori sono immediatamente accessibili da [!DNL Tags] e da soluzioni di Adobe che devono essere high sulla pagina, come Adobe Target.

1. Popola i dati nel livello dati.
1. In [!DNL Experience Platform Tags], crea &quot;[!UICONTROL data elements]&quot; che mappa i punti dati nel livello dati. Questi elementi dati vengono utilizzati in tutto il [!DNL Experience Platform Tags] in [!UICONTROL rules] e [!UICONTROL extensions].
1. In o [!DNL Analytics] sezione variabili globali dell&#39;estensione o in un [!DNL Tags rule], assegna i valori in [!UICONTROL data elements] a [!UICONTROL props], [!UICONTROL eVars], [!UICONTROL pageName]e altri [!DNL Analytics] variabili.
1. Attiva un beacon che invia i dati ad [!DNL Analytics].

Il seguente video illustra la procedura da seguire.

>[!VIDEO](https://video.tv.adobe.com/v/25899/?quality=12)

>[!NOTE]
>
>Il livello dati specifico utilizzato in questo video potrebbe non essere considerato una &quot;best practice&quot; per la tua organizzazione. È consigliabile utilizzare un livello di dati per la visualizzazione di dati importanti nelle soluzioni di marketing digitale.