---
title: Utilizzare un livello di dati per impostare le variabili di Analytics in Experienci Platform [!DNL tags]
description: Scopri come utilizzare un livello di dati per l’origine dei dati di Analytics e altre soluzioni di Experience Cloud.
feature: Tags
topics: Development
role: Developer, Data Engineer
level: Beginner
kt: 1852
thumbnail: 25899.jpg
exl-id: 408ceb47-df05-4456-85bb-0ef2798a05a5
source-git-commit: a45667a8d7ccb46b9e33bd11a78fac9714a61df5
workflow-type: tm+mt
source-wordcount: '312'
ht-degree: 50%

---

# Utilizzare un livello di dati per impostare le variabili di Analytics in Experienci Platform [!DNL tags]

L’utilizzo di un livello di dati per [!DNL Analytics] e altre soluzioni Experience Cloud è considerato una best practice. Questo video spiega come estrarre i valori dal livello dati e utilizzarli in Experienci Platform [!DNL tags] per popolare le variabili in Adobe Analytics.

## Livelli di dati

Un _livello di dati_ è un framework di oggetti JavaScript che gli sviluppatori aggiungono alle pagine web digitali. Le soluzioni Analytics utilizzano il livello di dati per compilare i rapporti. Sistemi di gestione dei tag, tra cui Experience Platform [!DNL tags]) sono gli intermediari che leggono il livello di dati, associano i valori alle variabili e inviano i dati alle soluzioni di esperienze digitali.

Rivedi informazioni aggiuntive sui livelli di dati in [Documentazione di Experience Cloud](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=it).

## Livelli dati, Experience Platform [!DNL tags], e ADOBE ANALYTICS

1. Definisci o identifica uno standard per il livello di dati da utilizzare nel sito.

   1. Posiziona il livello di dati il più in alto possibile nella sezione head della pagina e prima della chiamata ad Experienci Platform [!DNL tags]. In questo modo i dati sono immediatamente accessibili a [!DNL tags] e alle soluzioni Adobe che richiedono una posizione nella parte iniziale della pagina, come Adobe Target.

1. Popola i dati nel livello di dati.
1. Nell’Experience Platform [!DNL tags], creare &quot;[!UICONTROL data elements]&quot; che mappano i punti dati nel livello dati. Questi elementi di dati vengono utilizzati in tutto Experienci Platform [!DNL tags] in [!UICONTROL rules] e [!UICONTROL extensions].
1. Nella sezione delle variabili globali dell’estensione [!DNL Analytics] o in una [!DNL Tags rule], assegna i valori in [!UICONTROL data elements] a [!UICONTROL props], [!UICONTROL eVars], [!UICONTROL pageName] e altre variabili di [!DNL Analytics].
1. Attiva un beacon che invia i dati ad [!DNL Analytics].

Il seguente video illustra la procedura da seguire.

>[!NOTE]
>
> Il lancio è ora **[!DNL tags]**

>[!VIDEO](https://video.tv.adobe.com/v/25899/?quality=12&learn=on)

>[!NOTE]
>
>Anche se lo specifico livello di dati di questo video potrebbe non essere considerato una “best practice” per la tua organizzazione, è comunque una best practice utilizzare un livello di dati per far emergere dati importanti nelle soluzioni di marketing digitale.
