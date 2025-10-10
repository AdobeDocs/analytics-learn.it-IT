---
title: Tracciamento dei collegamenti personalizzati senza un gestore di tag
description: Per molte azioni eseguite sulla pagina, il tracciamento non deve essere trattato come una visualizzazione di pagina. Questo video spiega come scrivere il codice per un beacon di tracciamento dei collegamenti per Analytics, se non utilizzi un gestore di tag (come Experience Platform Launch). Trovi anche un esempio di codice e un suggerimento importante.
feature: Appmeasurement Implementation
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1845
role: Developer, Data Engineer
level: Intermediate
exl-id: e4567b1c-414e-44ad-982f-52b0150e7eda
source-git-commit: 8fc641743bc9e07b838a22ca64ccc15344d52764
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Tracciamento dei collegamenti personalizzati senza un gestore di tag {#custom-link-tracking-without-a-tag-manager}

Per molte azioni eseguite sulla pagina, il tracciamento non deve essere trattato come una visualizzazione di pagina. Questo video spiega come scrivere il codice per un beacon di tracciamento dei collegamenti per Analytics, se non utilizzi un gestore di tag (come Adobe [!DNL Experience Platform Launch]). Trovi anche un esempio di codice e un suggerimento importante.

## Invio di un beacon s.tl() {#sending-an-s-tl-beacon}

Esistono due funzioni che inviano dati ad Adobe Analytics:

1. s.t() - Un beacon “track”, ossia un hit di visualizzazione della pagina che incrementa le visualizzazioni di pagina per il nome di pagina specificato e imposta altre variabili
1. s.tl() - Un beacon “track link”, spesso chiamato hit/beacon “custom link”, che non incrementa le visualizzazioni di pagina e ignora la variabile pageName. Viene comunemente utilizzato per tracciare le azioni più piccole sulla pagina che non caricano una nuova pagina o schermata oppure altre azioni che non generano un nuovo caricamento di pagina.

>[!NOTE]
>
>Questo video spiega come scrivere il codice per un hit di collegamento personalizzato quando NON utilizzi un gestore di tag come Adobe [!DNL Experience Platform Launch]. Come best practice per l’implementazione, consigliamo di utilizzare [!DNL Experience Platform Launch]. Tuttavia, se nel codice vuoi usare `s.tl()`, ecco come farlo.

>[!VIDEO](https://video.tv.adobe.com/v/328135/?quality=12&learn=on&captions=ita)

## Codice di esempio {#sample-code}

Ecco il codice di esempio utilizzato per il collegamento personalizzato nel video:

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
