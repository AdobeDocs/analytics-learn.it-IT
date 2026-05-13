---
title: Tracciamento dei collegamenti personalizzati senza un gestore di tag
description: Per molte azioni eseguite sulla pagina, il tracciamento non deve essere trattato come una visualizzazione di pagina. Questo video spiega come scrivere il codice per un beacon di tracciamento dei collegamenti per Analytics, se non utilizzi un gestore di tag (come Experience Platform Launch). Trovi anche un esempio di codice e un suggerimento importante.
feature: Appmeasurement Implementation
topics: null
activity: implement
doc-type: technical video
team: Technical Marketing
kt: 1845
role: Developer
level: Intermediate
exl-id: e4567b1c-414e-44ad-982f-52b0150e7eda
TQID: https://experienceleague.adobe.com/BU98KM1JAq3v6Gd7SRU0FNT3qW-4a9UvP0M-ffFqJIA
product_v2:
  - id: e55547f1-a1ff-40c6-8978-026e40ab7fa4
role_v2:
  - id: ff6a42d2-313e-452e-93a6-792e4fad9ff8
level_v2:
  - id: b5a62a22-46f7-4f0d-b151-3fc640bef588
topic_v2:
  - id: b5ce8718-c3af-4fdb-a1a9-fca32f83a87c
  - id: c2be0313-b3ae-45e0-b454-d20bf54b23f2
source-git-commit: 677e5a22dab92be7ff021c8410525b9091975aef
workflow-type: tm+mt
source-wordcount: 272
ht-degree: 100%

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

>[!VIDEO](https://video.tv.adobe.com/v/25832/?quality=12&learn=on)

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
