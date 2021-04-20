---
title: Tracciamento dei collegamenti personalizzati senza tag Manager
description: Per molte azioni sulla pagina, il tracciamento non deve essere trattato come una visualizzazione di pagina. In questo video, imparerai a codificare un beacon di tracciamento dei collegamenti in Analytics, se non utilizzi un gestore di tag (come Experience Platform Launch). Vedi il codice e scopri un suggerimento importante.
feature: Appmeasurement Implementation
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1845
role: "Developer, Data Engineer"
level: Intermediate
translation-type: tm+mt
source-git-commit: f3b3fa7d91b0cb21005b57768ca23ed6700fcc03
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 4%

---


# Tracciamento dei collegamenti personalizzati senza tag Manager {#custom-link-tracking-without-a-tag-manager}

Per molte azioni sulla pagina, il tracciamento non deve essere trattato come una visualizzazione di pagina. In questo video, imparerai a codificare un beacon di tracciamento dei collegamenti in Analytics, se non utilizzi un gestore di tag (come Adobe [!DNL Experience Platform Launch]). Vedi il codice e scopri un suggerimento importante.

## Invio di un beacon s.tl() {#sending-an-s-tl-beacon}

Esistono due funzioni che inviano dati ad Adobe Analytics:

1. s.t() - Un beacon &quot;track&quot;, che è un hit di visualizzazione della pagina, che incrementa le visualizzazioni di pagina per il nome della pagina specificato, nonché imposta altre variabili
1. s.tl() - un beacon &quot;track link&quot;, che viene spesso chiamato come hit/beacon &quot;custom link&quot;, che non incrementa le visualizzazioni di pagina, e ignora la variabile pageName. Viene comunemente utilizzato per monitorare le azioni più piccole sulla pagina che non caricano una nuova pagina/schermo o altre azioni che non generano un nuovo caricamento di pagina.

>[!NOTE]
>
>In questo video ti mostriamo come codificare un hit di collegamento personalizzato quando NON utilizzi un gestore di tag come Adobe [!DNL Experience Platform Launch]. È consigliabile utilizzare [!DNL Experience Platform Launch], la raccomandazione sulle best practice per l’implementazione. Tuttavia, se devi eseguire il codice in un `s.tl()`, ecco come farlo.

>[!VIDEO](https://video.tv.adobe.com/v/25832/?quality=12)

## Codice campione {#sample-code}

Ecco il codice di esempio utilizzato sul collegamento personalizzato nel video:

```JavaScript
<a href="#" onclick="
    s.linkTrackVars='events,eVar2,prop2';
    s.linkTrackEvents=s.events='event2';
    s.eVar2='facebook share';
    s.prop2='facebook share';
    s.tl(this,'o','Social Share');
    s.manageVars('clearVars',s.linkTrackVars,1);">
    Click here to share on FaceBook
</a>
```

Per ulteriori informazioni sui collegamenti personalizzati, consulta la [documentazione](https://marketing.adobe.com/resources/help/it_IT/sc/implement/function_tl.html).