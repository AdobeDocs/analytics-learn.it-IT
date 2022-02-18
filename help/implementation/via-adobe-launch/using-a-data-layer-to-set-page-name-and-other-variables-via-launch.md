---
title: Utilizzo di un livello dati per impostare il nome della pagina e altre variabili in Adobe Analytics tramite Launch
description: L’utilizzo di un livello di dati per Analytics e altre soluzioni di Experience Cloud è considerata una best practice. In questo video vedrai come estrarre i valori dal livello dati e utilizzarli in Launch per popolare le variabili in Adobe Analytics.
feature: Launch Implementation
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1852
role: Developer, Data Engineer
level: Beginner
exl-id: 408ceb47-df05-4456-85bb-0ef2798a05a5
source-git-commit: fe861dfd541c1b9cb3b233fa3f56d55054305fd9
workflow-type: ht
source-wordcount: '356'
ht-degree: 100%

---

# Utilizzo di un livello dati per impostare il nome della pagina e altre variabili tramite [!DNL Experience Platform Launch] {#using-a-data-layer-to-set-page-name-and-other-variables-in-adobe-analytics-via-launch}

Utilizzo di un livello di dati per [!DNL Analytics] e altre soluzioni di Experience Cloud sono considerate una best practice. In questo video vedrai come estrarre i valori dal livello dati e utilizzarli in [!DNL Experience Platform Launch] per popolare le variabili in Adobe Analytics.

## Livelli dati {#data-layers}

Come best practice, è consigliabile utilizzare un livello dati quando si lavora con i dati sul sito e le soluzioni Adobe Experience Cloud, in particolare con Adobe Analytics. Un _livello dati_ è un framework di oggetti JavaScript che gli sviluppatori inseriscono nelle pagine. I livelli dati possono essere utilizzati da strumenti di tracciamento (inclusi sistemi di gestione dei tag come [!DNL Experience Platform Launch]) per compilare i rapporti. Per ulteriori informazioni sui livelli dati, consulta la [documentazione di Experience Cloud](https://experienceleague.adobe.com/docs/analytics/implementation/prepare/data-layer.html?lang=it) o il [sito W3C](https://www.w3.org/).

Inoltre, leggi il blog [Livelli dati: da Buzzword a Best Practice](https://theblog.adobe.com/data-layers-buzzword-best-practice/), che fornisce informazioni preziose sui livelli dati e un paio di esempi.

## Livelli dati, [!DNL Experience Platform Launch], e Adobe Analytics {#data-layers-launch-and-adobe-analytics-oh-my}

1. Crea uno standard del livello dati da utilizzare sul tuo sito, a cui puoi fare riferimento tramite [!DNL Experience Platform Launch].

   1. Posiziona questo livello di dati il più in alto possibile nella parte superiore della pagina, prima della chiamata a [!DNL Experience Platform Launch], in modo che i valori possano essere utilizzati immediatamente sia da [!DNL Launch], sia dalle soluzioni Adobe che devono essere nella parte superiore della pagina, come Adobe Target.

1. Popola i dati nel livello dati.
1. In [!DNL Experience Platform Launch], crea “[!UICONTROL data elements]” che fanno riferimento ai punti dati nel livello dati e che possono essere utilizzati in [!DNL Experience Platform Launch] in [!UICONTROL rules], [!UICONTROL extensions], e così via.
1. Utilizza [!UICONTROL data elements] nelle variabili globali dell’estensione [!DNL Analytics] o in una regola, assegnando i valori in [!UICONTROL props], [!UICONTROL eVars], [!UICONTROL pageName] o altre variabili di [!DNL Analytics].
1. Attiva un beacon che invia i dati ad [!DNL Analytics].

Il seguente video illustra la procedura da seguire.

>[!VIDEO](https://video.tv.adobe.com/v/25899/?quality=12)
