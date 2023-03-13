---
title: Utilizzare un livello di dati per impostare le variabili di Analytics tramite tag
description: Scopri come utilizzare un livello di dati per impostare l’origine dei dati di Analytics e altre soluzioni Experience Cloud.
feature: Launch Implementation
role: Developer, Data Engineer
level: Beginner
kt: 1852
thumbnail: 25899.jpg
exl-id: 408ceb47-df05-4456-85bb-0ef2798a05a5
source-git-commit: d78c3351d2a98704396ceb8f84d123dd463befe5
workflow-type: tm+mt
source-wordcount: '315'
ht-degree: 100%

---

# Utilizzare un livello di dati per impostare le variabili di Analytics tramite [!DNL Tags] {#use-a-data-layer-to-set-analytics-variables-in-adobe-analytics-via-tags}

L’utilizzo di un livello di dati per [!DNL Analytics] e altre soluzioni Experience Cloud è considerato una best practice. Questo video spiega come estrarre i valori dal livello di dati e utilizzarli in [!DNL Experience Platform Tags] per popolare le variabili in Adobe Analytics.

## Livelli di dati {#data-layers}

Un _livello di dati_ è un framework di oggetti JavaScript che gli sviluppatori aggiungono alle pagine web digitali. Le soluzioni Analytics utilizzano il livello di dati per compilare i rapporti. I sistemi di gestione dei tag, tra cui [!DNL Experience Platform Tags], sono gli intermediari che leggono il livello di dati, associano i valori alle variabili e inviano i dati alle soluzioni di esperienze digitali.

Per ulteriori informazioni sui livelli di dati, consulta la [documentazione di Experience Cloud](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=it) e il blog [Livelli di dati: da termine trendy a best practice](https://blog.adobe.com/en/2014/03/13/data-layers-buzzword-best-practice).

## Livelli di dati, [!DNL Experience Platform Tags] e Adobe Analytics{#data-layers-launch-and-adobe-analytics}

1. Definisci o identifica uno standard per il livello di dati da utilizzare nel sito.

   1. inserisci il livello di dati il più in alto possibile nella sezione head della pagina e prima della chiamata a [!DNL Experience Platform Tags]. In questo modo i dati sono immediatamente accessibili a [!DNL Tags] e alle soluzioni Adobe che richiedono una posizione nella parte iniziale della pagina, come Adobe Target.

1. Popola i dati nel livello di dati.
1. In [!DNL Experience Platform Tags], crea “[!UICONTROL data elements]” con cui mappare i punti di dati nel livello di dati. Questi elementi di dati vengono utilizzati in [!DNL Experience Platform Tags], in [!UICONTROL rules] e [!UICONTROL extensions].
1. Nella sezione delle variabili globali dell’estensione [!DNL Analytics] o in una [!DNL Tags rule], assegna i valori in [!UICONTROL data elements] a [!UICONTROL props], [!UICONTROL eVars], [!UICONTROL pageName] e altre variabili di [!DNL Analytics].
1. Attiva un beacon che invia i dati ad [!DNL Analytics].

Il seguente video illustra la procedura da seguire.

>[!VIDEO](https://video.tv.adobe.com/v/25899/?quality=12)

>[!NOTE]
>
>Anche se lo specifico livello di dati di questo video potrebbe non essere considerato una “best practice” per la tua organizzazione, è comunque una best practice utilizzare un livello di dati per far emergere dati importanti nelle soluzioni di marketing digitale.