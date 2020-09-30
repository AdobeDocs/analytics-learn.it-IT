---
title: Informazioni e utilizzo di IQ viaggio - Analisi cross-device
description: Quando gli utenti interagiscono con il tuo marchio, lo fanno in molti modi e su più dispositivi. Analytics tra dispositivi si integra con Adobe Experience Platform Identity Service per identificare la mappatura dei dispositivi alle persone. Quindi sfrutta questa intelligenza per creare una visualizzazione cross-device del comportamento degli utenti. Questo consente di eseguire analisi sulle persone, non sui dispositivi.
feature: cda
topics: null
audience: all
activity: use
doc-type: article
team: Technical Marketing
kt: 4138
translation-type: tm+mt
source-git-commit: 24ad92b0ccdf1112e3ed4a0968cd47db757598c3
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# Informazioni e utilizzo [!DNL Journey IQ] - Analisi cross-device

Quando gli utenti interagiscono con il tuo marchio, lo fanno in molti modi e su più dispositivi. Analytics tra dispositivi si integra con [!DNL Adobe Experience Platform Identity Service] per identificare la mappatura dei dispositivi alle persone. Quindi sfrutta questa intelligenza per creare una visualizzazione cross-device del comportamento degli utenti. Questo consente di eseguire analisi sulle persone, non sui dispositivi.

## Panoramica dell&#39;analisi multi-dispositivo

### Non sono dispositivi

Quando gli utenti interagiscono con il tuo marchio, lo fanno in molti modi e su più &quot;superfici&quot; o &quot;dispositivi&quot;. Possono utilizzare un browser Web su un PC o un dispositivo mobile, oppure possono utilizzare un&#39;app mobile. Nell&#39;analisi digitale tradizionale, cresciuta nella raccolta di dati basata sui cookie, ciascuna di queste superfici è rappresentata come un &quot;visitatore&quot; univoco. Questo significa che ogni utente è rappresentato come un multiplo di visitatori unici.

Ecco un esempio. Supponiamo che Isabelle interagisca con il tuo marchio nel modo seguente:

*Isabelle è tre visitatori*![Tradizionale viaggio di Analytics](assets/cda-isabelle-journey-traditional-analytics.png)

Utilizzando l&#39;analisi tradizionale, il viaggio di Isabelle è diviso in tre parti. È rappresentata da tre visitatori unici, ciascuno dei quali ha utilizzato un dispositivo diverso per eseguire attività isolate. Ciò che serve è una visione unificata e su più dispositivi delle interazioni di Isabelle. [!DNL Journey IQ: Cross-Device Analytics] fornisce questa visualizzazione.

*Isabelle è una persona* che viaggia nell&#39;analisi![multi-dispositivo](assets/cda-isabelle-journey-cross-device-analytics.png)

### Una Visualizzazione Su Più Dispositivi Fornisce Analisi Migliori

La visualizzazione del comportamento di Isabelle basata sulla persona e su più dispositivi può fare una differenza significativa per la vostra analisi. Ad esempio, l’approccio tradizionale basato sui visitatori non offre un quadro completo dell’efficacia dei canali di marketing. Vediamo di nuovo il percorso di Isabelle, concentrandoci su quale canale riceve credito per la sua visione del prodotto e per il suo acquisto. Useremo [!UICONTROL last-touch] l&#39;attribuzione per la semplicità, ma lo stesso problema si verifica utilizzando qualsiasi modello di attribuzione quando dividi il comportamento di Isabelle in visitatori separati. L’utilizzo della tradizionale visione del mondo basata sui visitatori offre risultati molto diversi, anche fuorvianti:

*Attribuzione*![canale Analytics tradizionale e analisi multi-dispositivo](assets/channel-attribution.png)

Con la visualizzazione su più dispositivi, il canale e-mail riceve credito sia per la visualizzazione del prodotto che per l&#39;acquisto, che rappresenta in modo più accurato l&#39;esperienza reale di Isabelle.

Continua a leggere per saperne di più:

* How [!DNL Cross-Device Analytics] Works
* Prerequisiti Per [!DNL Cross-Device Analytics]
* Interpretazione dei dati tra dispositivi
* Analisi dei dati multi-dispositivo in  Analysis Workspace

## How [!DNL Cross-Device Analytics] Works

[!DNL Journey IQ: Cross-Device Analytics (CDA)] si integra con il [!DNL Adobe Experience Platform Identity Service], utilizzando [[!DNL Co-op Graph]](https://docs.adobe.com/content/help/it-IT/device-co-op/using/home.html) o [!DNL Private Graph] per identificare la mappatura dei dispositivi alle persone. Quindi sfrutta questa intelligenza per creare una visualizzazione cross-device del comportamento degli utenti. CDA include funzionalità e strumenti ineguagliabili per aiutare l&#39;azienda a comprendere l&#39;utilizzo di più dispositivi e l&#39;esperienza dei clienti su tali dispositivi nelle loro interazioni con il tuo marchio. Si trova come un livello sotto  Analysis Workspace per fornire informazioni approfondite sull&#39;analisi dell&#39;audience basata sulle persone e l&#39;attribuzione, la segmentazione e l&#39;analisi del percorso tra dispositivi utilizzando potenti strumenti come [!UICONTROL Fallout], [!DNL Flow], [!DNL Cohort]e [!DNL Segment IQ] [!DNL Attribution IQ].

### Le selezioni del menu [!DNL Cross-Device Virtual Report Suite]

Il CDA viene presentato attraverso uno speciale tipo di cross-device [[!UICONTROL Virtual Report Suite]](https://docs.adobe.com/content/help/it-IT/analytics/components/virtual-report-suites/vrs-about.html). Questo consente di continuare a utilizzare la suite di rapporti basata sui dispositivi originale al momento dell&#39;introduzione dell&#39;analisi cross-device nell&#39;organizzazione. La configurazione di una VRS CDA è semplice.

Nel passaggio uno del generatore VRS, scegliete [!UICONTROL report suite] quello configurato dal Adobe  come abilitato per CDA:

*Scegliere una base abilitata per CDA (origine)[!UICONTROL report suite]*![[!UICONTROL Virtual Report Suite] Passo 1](assets/cda-vrs-step-one.png)

Quindi attivate [!UICONTROL Report Time Processing] e attivate [!UICONTROL cross-device stitching]:

*Abilita[!UICONTROL report-time processing]e[!UICONTROL cross-device stitching]* Passaggio 2![[!UICONTROL Virtual Report Suite]](assets/cda-vrs-step-two.png)

Completare la configurazione della VRS e salvarla. La VRS CDA verrà visualizzata in  Analysis Workspace con un&#39;icona speciale accanto ad essa, come mostrato di seguito:

*Selezionate CDA VRS in  Analysis Workspace*![[!UICONTROL Virtual Report Suite] Step Three](assets/cda-vrs-step-three.png)

>[!TIP]
>
>Potete creare tutti i CDA [!UICONTROL virtual report suites] che desiderate sulla base abilitata per CDA [!UICONTROL report suite].

### Ripristino della cronologia

A volte è necessario un po&#39; di tempo per consentire agli utenti di effettuare l&#39;accesso e per [!DNL Co-op Graph] o [!DNL Private Graph] per identificarli e mapparne insieme i dispositivi. CDA utilizza una finestra di look-back di 30 giorni, che consente di ripristinare un visitatore precedentemente non identificato come persona fino a 30 giorni nel passato.

Come aiuta questo? Ricordate il percorso utente di Isabelle dalla discussione precedente:

![[!DNL Cross-Device Analytics] Viaggio](assets/cda-isabelle-journey-cross-device-analytics.png)

È possibile che Isabelle non abbia effettuato l&#39;accesso fino a poco prima dell&#39;acquisto, e che il [!DNL Co-op Graph] o [!DNL Private Graph] non abbia mappato insieme i dispositivi di Isabelle fino a poco tempo dopo il suo acquisto. Ma lo sguardo di 30 giorni della CDA permette alla CDA di riaffermare il comportamento passato di Isabelle a livello personale, fornendo la visione cross-device del suo viaggio che vi serve.

>[!NOTE]
>
>Poiché la cronologia può essere ripristinata, ciò significa che i dati possono cambiare nel tempo in un CDA abilitato [!UICONTROL virtual report suite]. Tenete presente questo aspetto durante la comunicazione di informazioni da un’analisi basata su CDA.

## Prerequisiti Per [!UICONTROL Cross-Device Analytics]

CDA è incluso con [[!DNL Analytics Ultimate]](https://helpx.adobe.com/legal/product-descriptions/adobe-analytics.html). A partire da settembre 2019, [!DNL Analytics Ultimate] i clienti che soddisfano i prerequisiti elencati di seguito possono utilizzare CDA. I prerequisiti per CDA sono i seguenti:

* La società deve essere membro del [!DNL Adobe Experience Platform Identity Service] [!DNL Co-op Graph] [o utilizzare un](https://docs.adobe.com/content/help/it-IT/device-co-op/using/home.html)[!DNL Adobe Experience Platform Identity Service Private Graph].
* Devi implementare tutto ciò che è necessario per [!DNL Co-op Graph] o [!DNL Private Graph] includere [ID Experience Cloud (ECID)](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html) e la sincronizzazione ID con il grafico. Si noti che, oltre ai requisiti tecnici, l&#39;accordo [!DNL Co-op Graph] ha altri requisiti legali e contrattuali.
* Attualmente non è possibile utilizzare due organizzazioni IMS con un solo [!DNL Private Graph], pertanto è necessario standardizzare un&#39;unica organizzazione IMS. In alcuni casi, è possibile per un cliente con più organizzazioni IMS utilizzare il programma [!DNL Co-op Graph] insieme a CDA.
* I componenti [!DNL Co-op graph] e [!DNL Private Graph], nonché alcuni componenti di CDA, sono ospitati in [!DNL Microsoft Azure]. Ciò significa che [!DNL Analytics] i dati vengono copiati avanti e indietro tra  centro  elaborazione dati e  presenza  Adobe in [!DNL Microsoft Azure]. Alcuni [!DNL Analytics] dati verranno memorizzati in [!DNL Azure]. La vostra azienda deve accettare questo accordo.
* CDA richiede un &quot;cross-device&quot; [!UICONTROL report suite]. In altre parole, l’ [!UICONTROL report suite] utilizzo per CDA deve includere dati provenienti da più tipi di dispositivi o &quot;superfici&quot; diversi, ad esempio Web per desktop, Web per dispositivi mobili e app mobili. A partire da settembre 2019, il volume delle chiamate server per questo [!UICONTROL report suite] deve essere di 100 MM al giorno o meno. (I limiti di volume delle chiamate al server aumenteranno nei prossimi mesi).
* A partire da settembre 2019, [!DNL Co-op Graph] e [!DNL Private Graph] sono disponibili solo in Nord America. Il programma per la presenza dei grafici nell&#39;area EMEA e nell&#39;APAC verrà annunciato in futuro. Se vi trovate in queste regioni, vi invitiamo a iniziare a considerare questi prerequisiti ora in modo da essere pronti ad andare quando il grafico diventerà disponibile.

## Interpretazione dei dati tra dispositivi

### Persone non visitatori

All&#39;interno del CDA [!UICONTROL Virtual Report Suite], vedrete alcune modifiche. Ad esempio, la [!UICONTROL Unique Visitors] metrica viene sostituita da due nuove metriche: [!UICONTROL People] e [!UICONTROL Unique Devices]. Queste nuove metriche ti consentono di conoscere meglio le dimensioni dell&#39;audience.

*Persone e dispositivi* univoci![CDA [!UICONTROL People Metric]](assets/cda-people-metric.png)

Nel contenitore [[!UICONTROL Segment Builder]](https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/segmentation-workflow/seg-build.html), il [!UICONTROL Visitor] segmento è stato sostituito da un contenitore di [!UICONTROL Person] segmento. Utilizzando una VRS CDA, puoi creare segmenti tra dispositivi quali:

* Utenti che utilizzano più dispositivi
* Persone che iniziano il loro percorso su un dispositivo mobile e successivamente acquistano su un dispositivo desktop
* Visite in cui le persone utilizzano più dispositivi per eseguire un&#39;attività

*Contenitore segmenti*![[!DNL Segment Builder] a livello di persona [!UICONTROL Person]](assets/cda-segment-builder-person-container.png)

### Persistenza Dimension

All&#39;interno di una VRS CDA, dimensioni come [!DNL eVars] ora persistono automaticamente tra i dispositivi. Ad esempio, un oggetto [!DNL eVar] configurato come:

* Allocazione: Più recente (ultimo)
* Scadenza dopo: Purchase

persisterà automaticamente da un dispositivo all&#39;altro fino all&#39;attivazione dell&#39;evento Purchase.

## Analisi dei dati multi-dispositivo in  Analysis Workspace

### Analisi dell&#39;audience basata su persona

Vi siete mai chiesti quante persone interagiscono con il vostro marchio? Desideri capire quanti e che tipo di dispositivi utilizzano? Come si sovrappone l&#39;utilizzo? Utilizzando una VRS CDA, potete creare diagrammi [](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/venn.html) Venn cross-device e [istogrammi](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/histogram.html)per persona.

*Analisi*![Venn e Istogramma basate su persona](assets/cda-venn-and-histogram.png)

### Cross-Device [!DNL Flow]

Con CDA e  Analysis Workspace, puoi visualizzare il modo in cui le persone si spostano da un dispositivo all&#39;altro nel tempo nella visualizzazione [[!DNL Flow]](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/visualizations/flow/flow.html). Potete vedere dove abbandonano il loro viaggio e dove proseguono.

*[!DNL Flow]con CDA*
![[!DNL Flow Visualization]](assets/cda-flow-viz.png)

### Cross-Device [!DNL Fallout]

È probabile che si utilizzino diverse visualizzazioni [[!DNL Fallout]](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html) per analizzare in che modo gli utenti ottengono risultati positivi attraverso una serie di passaggi prima di raggiungere il successo. Sapevate che la vostra visione di questi elementi [!DNL Fallout visualizations] è limitata quando utilizzate l&#39;analisi tradizionale basata sui dispositivi? Per ottenere un risultato positivo, il passaggio successivo deve verificarsi nello stesso browser o nella stessa app del passaggio precedente. Nell&#39;analisi basata sui dispositivi, non si è veduti gli utenti che hanno completato con successo il passaggio successivo su un altro dispositivo.

Non preoccuparti, CDA ti ha coperto. CDA crea la vista cross-device che rende [!DNL Fallout visualizations] molto, molto più utile. Dopo tutto, ciò che conta davvero è se la persona alla fine è riuscita nel suo compito da qualche parte.

*[!DNL Fallout]con CDA*
![[!DNL Fallout Visualization]](assets/cda-fallout-viz.png)

### [!DNL Cross-Device Attribution IQ]

Poiché CDA crea un livello di dati cross-device sotto  Analysis Workspace, tutte le analisi saranno aromatizzate con una prospettiva cross-device. Un esempio potente è attraverso [[!DNL  Attribution IQ]](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/panels/attribution/attribution.html). [!DNL Attribution IQ] in  Analysis Workspace consente di confrontare più modelli di attribuzione affiancati. Utilizzando questa funzionalità con CDA, ora puoi confrontare come diversi dispositivi contribuiscono al successo.

Ad esempio, supponete di voler capire la frequenza con cui un cellulare è il primo dispositivo utilizzato in un&#39;interazione che alla fine porta al successo. Rappresenta il &quot;tasso di acquisizione&quot; del telefono cellulare. CDA + [!DNL Attribution IQ] consente di eseguire questa analisi:

*[!DNL Attribution IQ]con CDA*
![[!DNL Attribution IQ]](assets/cda-attribution-iq.png)

For more information, see the [[!DNL Cross-Device Analytics] help documentation](https://docs.adobe.com/content/help/it-IT/analytics/components/cda/cda-home.html).
