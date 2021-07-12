---
title: Utilizzo di un livello dati per impostare Nome pagina e Altre variabili in Adobe Analytics tramite Launch
description: L’utilizzo di un livello di dati per Analytics e altre soluzioni di Experience Cloud è considerata una best practice. In questo video vedrai come estrarre i valori dal livello dati e utilizzarli in Launch per popolare le variabili in Adobe Analytics.
feature: Implementazione di Launch
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1852
role: Developer, Data Engineer
level: Beginner
exl-id: 408ceb47-df05-4456-85bb-0ef2798a05a5
source-git-commit: 32424f3f2b05952fe4df9ea91dcbe51684cee905
workflow-type: tm+mt
source-wordcount: '358'
ht-degree: 4%

---

# Utilizzo di un livello dati per impostare il nome della pagina e altre variabili tramite [!DNL Experience Platform Launch] {#using-a-data-layer-to-set-page-name-and-other-variables-in-adobe-analytics-via-launch}

È consigliabile utilizzare un livello di dati per [!DNL Analytics] e altre soluzioni di Experience Cloud. Questo video illustra come estrarre i valori dal livello dati e utilizzarli in [!DNL Experience Platform Launch] per popolare le variabili in Adobe Analytics.

## Livelli dati {#data-layers}

È consigliabile utilizzare un livello dati quando si lavora con dati sul sito e soluzioni Adobe Experience Cloud, in particolare con Adobe Analytics. Un _livello dati_ è un framework di oggetti JavaScript che gli sviluppatori inseriscono nelle pagine. I livelli dati possono essere utilizzati da strumenti di tracciamento (inclusi sistemi di gestione tag come [!DNL Experience Platform Launch]) per popolare i rapporti. Per ulteriori informazioni sui livelli dati, consulta la [documentazione Experience Cloud](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-data-layer.html) o il [sito W3C](https://www.w3.org/).

Inoltre, consulta il blog [Livelli dati: Da Buzzword a Best Practice,](https://theblog.adobe.com/data-layers-buzzword-best-practice/), che fornisce alcune informazioni fantastiche sui livelli di dati, così come un paio di esempi.

## Livelli dati, [!DNL Experience Platform Launch] e Adobe Analytics (oh my?){#data-layers-launch-and-adobe-analytics-oh-my}

1. Crea uno standard del livello dati da utilizzare sul sito, a cui può fare riferimento [!DNL Experience Platform Launch].

   1. Posiziona questo livello di dati il più in alto possibile nella parte superiore della pagina, prima della chiamata a [!DNL Experience Platform Launch], in modo che i valori possano essere utilizzati immediatamente da [!DNL Launch] e dalle soluzioni di Adobe che devono essere elevate sulla pagina, come Adobe Target.

1. Popolare i dati nel livello dati.
1. In [!DNL Experience Platform Launch], crea &quot;[!UICONTROL data elements]&quot; che fa riferimento ai punti dati nel livello dati e che può essere utilizzato in [!DNL Experience Platform Launch] in [!UICONTROL rules], [!UICONTROL extensions] e così via.
1. Utilizza il [!UICONTROL data elements] nelle variabili globali dell&#39;estensione [!DNL Analytics] o in una regola, assegnando i valori in [!UICONTROL props], [!UICONTROL eVars], [!UICONTROL pageName] o in altre variabili [!DNL Analytics].
1. Attiva un beacon che invia i dati in [!DNL Analytics].

Il seguente video illustra la procedura da seguire.

>[!VIDEO](https://video.tv.adobe.com/v/25899/?quality=12)
