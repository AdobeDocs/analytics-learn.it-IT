---
title: Tracciamento personalizzato dei collegamenti senza Gestione tag
description: Per molte azioni sulla pagina, il tracciamento non deve essere trattato come una visualizzazione di pagina. Questo video illustra come codificare un beacon per il tracciamento dei collegamenti in Analytics, se non si utilizza un gestore di tag (come nell’Experience Platform Launch). Vedi il codice e scopri un suggerimento importante.
feature: appmeasurement implementation
topics: null
audience: implementer
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1845
translation-type: tm+mt
source-git-commit: 8276828e9e759a1964ca5ea89bb1395e5e78b500
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Tracciamento personalizzato dei collegamenti senza Gestione tag {#custom-link-tracking-without-a-tag-manager}

Per molte azioni sulla pagina, il tracciamento non deve essere trattato come una visualizzazione di pagina. Questo video illustra come codificare un beacon per il tracciamento dei collegamenti in Analytics, se non si utilizza un gestore di tag (come  Adobe [!DNL Experience Platform Launch]). Vedi il codice e scopri un suggerimento importante.

## Invio di un beacon s.tl() {#sending-an-s-tl-beacon}

Esistono due funzioni che inviano dati  Adobe Analytics:

1. s.t() - Un beacon &quot;track&quot;, che è un hit di visualizzazione pagina, che incrementa le visualizzazioni di pagina per il nome di pagina specificato, nonché imposta altre variabili
1. s.tl() - un beacon &quot;track link&quot;, che viene spesso definito come hit/beacon &quot;collegamento personalizzato&quot;, che non incrementa le visualizzazioni di pagina, e ignora la variabile pageName. Questa funzione è comunemente utilizzata per tenere traccia delle azioni più piccole sulla pagina che non caricano una nuova pagina/schermo, o di altre azioni che non generano un nuovo caricamento di pagina.

>[!NOTE]
>
>In questo video viene illustrato come codificare un hit di collegamento personalizzato quando NON si utilizza un gestore di tag come  Adobe [!DNL Experience Platform Launch]. Vi consigliamo di utilizzare [!DNL Experience Platform Launch], la nostra raccomandazione sulle best practice per l&#39;implementazione. Tuttavia, se è necessario codificare un `s.tl()`file, è possibile seguire questa procedura.

>[!VIDEO](https://video.tv.adobe.com/v/25832/?quality=12)

## Codice campione {#sample-code}

Di seguito è riportato il codice di esempio utilizzato per il collegamento personalizzato nel video:

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