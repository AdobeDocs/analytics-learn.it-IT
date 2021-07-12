---
title: Informazioni e utilizzo del Percorso IQ - Analisi multidispositivo
description: Quando gli utenti interagiscono con il tuo marchio, lo fanno in molti modi e su più dispositivi. Analisi multidispositivo si integra con il servizio Adobe Experience Platform Identity per identificare in che modo i dispositivi si associano alle persone. Quindi sfrutta questa intelligenza per creare una visione cross-device del comportamento degli utenti. Questo si traduce nella possibilità di eseguire analisi sulle persone, non sui dispositivi.
feature: CDA
topics: null
activity: use
doc-type: article
team: Technical Marketing
kt: 4138
role: User
level: Intermediate
exl-id: 3748d5d7-d250-4057-8131-afdc66c80200
source-git-commit: 32424f3f2b05952fe4df9ea91dcbe51684cee905
workflow-type: tm+mt
source-wordcount: '1606'
ht-degree: 5%

---

# Informazioni e utilizzo di [!DNL Journey IQ] - Analisi multidispositivo

Quando gli utenti interagiscono con il tuo marchio, lo fanno in molti modi e su più dispositivi. Cross-Device Analytics si integra con [!DNL Adobe Experience Platform Identity Service] per identificare in che modo i dispositivi vengono mappati alle persone. Quindi sfrutta questa intelligenza per creare una visione cross-device del comportamento degli utenti. Questo si traduce nella possibilità di eseguire analisi sulle persone, non sui dispositivi.

## Panoramica di Analytics tra dispositivi

### Non Sono I Miei Dispositivi

Quando gli utenti interagiscono con il tuo marchio lo fanno in molti modi e su più &quot;superfici&quot; o &quot;dispositivi&quot;. Possono utilizzare un browser web su un PC o su un dispositivo mobile, oppure un&#39;app mobile. Nell’analisi digitale tradizionale, cresciuta nella raccolta di dati basata sui cookie, ciascuna di queste superfici è rappresentata come un &quot;visitatore&quot; univoco. Questo significa che ogni utente umano è rappresentato da un multiplo di visitatori unici.

Ecco un esempio. Supponiamo che Isabelle interagisca con il tuo marchio nel modo seguente:

*Isabelle è composta da tre*
![visitatoriPercorso di analisi tradizionale](assets/cda-isabelle-journey-traditional-analytics.png)

Utilizzando l&#39;analisi tradizionale, il percorso di Isabelle è diviso in tre parti. È rappresentata da tre visitatori unici, ciascuno dei quali ha utilizzato un dispositivo diverso per eseguire attività isolate. Ciò che serve è una visione unificata e interattiva delle interazioni di Isabelle. [!DNL Journey IQ: Cross-Device Analytics] fornisce questa visualizzazione.

*Isabelle è una sola*
![persona nel Percorso Cross-Device Analytics](assets/cda-isabelle-journey-cross-device-analytics.png)

### Una Visualizzazione multidispositivo Offre Una Migliore Analisi

Avere una visione del comportamento di Isabelle incentrata sulla persona e su più dispositivi può fare una differenza significativa nella tua analisi. Ad esempio, l’approccio tradizionale basato sui visitatori non offre un quadro completo dell’efficacia dei canali di marketing. Vediamo ancora una volta il percorso di Isabelle, concentrandoci su quale canale riceve credito per la sua visualizzazione del prodotto e per il suo acquisto. Useremo l’attribuzione [!UICONTROL last-touch] per la semplicità, ma lo stesso problema si verifica quando si suddivide il comportamento di Isabelle in visitatori separati. L&#39;utilizzo della visione tradizionale del mondo basata sui visitatori dà risultati molto diversi, anche fuorvianti:

*Attribuzione canali tradizionali di Analytics e*
![Analytics tra dispositivi](assets/channel-attribution.png)

Tieni presente che con la visualizzazione su più dispositivi, il canale e-mail riceve credito sia per la visualizzazione del prodotto che per l’acquisto, che rappresenta più accuratamente l’esperienza reale di Isabelle.

Continua a leggere per saperne di più:

* Come funziona [!DNL Cross-Device Analytics]
* Prerequisiti Per [!DNL Cross-Device Analytics]
* Interpretazione dei dati tra dispositivi
* Analisi dei dati tra dispositivi in Analysis Workspace

## Come funziona [!DNL Cross-Device Analytics]

[!DNL Journey IQ: Cross-Device Analytics (CDA)] si integra con  [!DNL Adobe Experience Platform Identity Service], utilizzando  [[!DNL Co-op Graph]](https://docs.adobe.com/content/help/it-IT/device-co-op/using/home.html) o  [!DNL Private Graph] per identificare in che modo i dispositivi si associano alle persone. Quindi sfrutta questa intelligenza per creare una visione cross-device del comportamento degli utenti. CDA include funzionalità e strumenti ineguagliabili per aiutare la tua azienda a comprendere l’utilizzo multi-dispositivo e l’esperienza del cliente tra questi dispositivi nelle loro interazioni con il tuo marchio. Si trova come livello sotto Analysis Workspace per fornire informazioni approfondite sull’analisi del pubblico basata su persone e sull’attribuzione, la segmentazione e l’analisi del percorso tra dispositivi utilizzando potenti strumenti come [!UICONTROL Fallout], [!DNL Flow], [!DNL Cohort], [!DNL Segment IQ] e [!DNL Attribution IQ].

### Le selezioni del menu [!DNL Cross-Device Virtual Report Suite]

Il CDA viene presentato attraverso un tipo speciale di cross-device [[!UICONTROL Virtual Report Suite]](https://docs.adobe.com/content/help/it-IT/analytics/components/virtual-report-suites/vrs-about.html). Questo consente di continuare a utilizzare la suite di rapporti originale basata su dispositivi durante l’introduzione dell’analisi tra più dispositivi nell’organizzazione. Configurare una VRS CDA è facile.

Nel passaggio uno del generatore VRS, scegli il [!UICONTROL report suite] configurato da Adobe come abilitato da CDA:

*Scegli una base abilitata per CDA (origine)[!UICONTROL report suite]*
![[!UICONTROL Virtual Report Suite] Passaggio 1](assets/cda-vrs-step-one.png)

Quindi attiva [!UICONTROL Report Time Processing] e abilita [!UICONTROL cross-device stitching]:

*Abilita  [!UICONTROL report-time processing] e[!UICONTROL cross-device stitching]*
![[!UICONTROL Virtual Report Suite] passaggio 2](assets/cda-vrs-step-two.png)

Completare la configurazione VRS e salvarla. La VRS CDA verrà visualizzata in Analysis Workspace con un’icona speciale accanto ad essa, come illustrato di seguito:

*Seleziona la VRS CDA in Analysis*
![[!UICONTROL Virtual Report Suite] WorkspacePassaggio 3](assets/cda-vrs-step-three.png)

>[!TIP]
>
>Puoi creare tutti i CDA [!UICONTROL virtual report suites] che desideri sulla base abilitata per CDA [!UICONTROL report suite].

### Ripristino della cronologia

A volte ci vuole un po&#39; di tempo prima che gli utenti effettuino l&#39;accesso e che i [!DNL Co-op Graph] o [!DNL Private Graph] identifichino e mappino i loro dispositivi. CDA utilizza un intervallo di look-back di 30 giorni, che consente di ripristinare un visitatore non identificato in precedenza come persona fino a 30 giorni nel passato.

Come aiuta questo? Ricorda il percorso utente di Isabelle dalla discussione precedente:

![[!DNL Cross-Device Analytics] Percorso](assets/cda-isabelle-journey-cross-device-analytics.png)

È possibile che Isabelle non abbia effettuato l&#39;accesso fino al momento in cui ha effettuato l&#39;acquisto e che i dispositivi di Isabelle non siano stati mappati fino a qualche momento dopo il suo acquisto. [!DNL Co-op Graph][!DNL Private Graph] Ma il look-back di 30 giorni di CDA permette a CDA di riaffermare il comportamento passato di Isabelle a livello di persona, fornendo la visione cross-device del suo percorso di cui hai bisogno.

>[!NOTE]
>
>Poiché la cronologia può essere ripristinata, i dati potrebbero cambiare nel tempo in un [!UICONTROL virtual report suite] abilitato per CDA. Tieni presente questo aspetto durante la comunicazione delle informazioni da un’analisi basata su CDA.

## Prerequisiti Per [!UICONTROL Cross-Device Analytics]

CDA è incluso in [[!DNL Analytics Ultimate]](https://helpx.adobe.com/legal/product-descriptions/adobe-analytics.html). A partire da settembre 2019, i clienti [!DNL Analytics Ultimate] che soddisfano i prerequisiti elencati di seguito possono utilizzare CDA. I prerequisiti per CDA sono i seguenti:

* La tua azienda deve essere membro di [!DNL Adobe Experience Platform Identity Service] [[!DNL Co-op Graph]](https://docs.adobe.com/content/help/en/device-co-op/using/home.html) oppure utilizzare un [!DNL Adobe Experience Platform Identity Service Private Graph].
* Devi implementare tutto ciò che è necessario per [!DNL Co-op Graph] o [!DNL Private Graph], compresi [Experience Cloud ID (ECID)](https://docs.adobe.com/content/help/it-IT/id-service/using/home.html) e la sincronizzazione ID con il grafico. Si noti che oltre ai requisiti tecnici, il [!DNL Co-op Graph] ha altri requisiti legali e contrattuali.
* Attualmente non è possibile utilizzare due organizzazioni IMS con un singolo [!DNL Private Graph], pertanto devi standardizzare un’unica organizzazione IMS. In alcuni casi è possibile per un cliente con più organizzazioni IMS utilizzare [!DNL Co-op Graph] insieme a CDA.
* I [!DNL Co-op graph] e [!DNL Private Graph], così come alcuni componenti di CDA, sono ospitati in [!DNL Microsoft Azure]. Ciò significa che i dati [!DNL Analytics] vengono copiati avanti e indietro tra il centro di elaborazione dati di Adobe e la presenza di Adobe in [!DNL Microsoft Azure]. Alcuni dati [!DNL Analytics] verranno memorizzati in [!DNL Azure]. La tua azienda deve accettare questo accordo.
* CDA richiede un &quot;cross-device&quot; [!UICONTROL report suite]. In altre parole, la [!UICONTROL report suite] utilizzata per CDA deve includere dati provenienti da più tipi di dispositivi o &quot;superfici&quot; diversi, come web per desktop, web per dispositivi mobili e app mobili. A partire da settembre 2019, il volume delle chiamate al server per questo [!UICONTROL report suite] deve essere di 100 MM al giorno o meno. (I limiti di volume delle chiamate al server aumenteranno nei prossimi mesi.)
* A partire da settembre 2019, i formati [!DNL Co-op Graph] e [!DNL Private Graph] sono disponibili solo in Nord America. Il programma per la presenza di grafici in EMEA e APAC verrà annunciato in un momento futuro. Se ti trovi in queste aree, ti invitiamo a iniziare a esaminare questi prerequisiti in modo da essere pronti per iniziare quando il grafico sarà disponibile.

## Interpretazione dei dati tra dispositivi

### Persone non visitatori

All&#39;interno di CDA [!UICONTROL Virtual Report Suite], vedrai alcune modifiche. Ad esempio, la metrica [!UICONTROL Unique Visitors] viene sostituita da due nuove metriche: [!UICONTROL People] e [!UICONTROL Unique Devices]. Queste nuove metriche consentono di ottenere informazioni molto migliori sulle dimensioni del pubblico.

*Persone e*
![dispositivi uniciCDA  [!UICONTROL People Metric]](assets/cda-people-metric.png)

Nel [[!UICONTROL Segment Builder]](https://docs.adobe.com/content/help/it-IT/analytics/components/segmentation/segmentation-workflow/seg-build.html) il contenitore di segmenti [!UICONTROL Visitor] è stato sostituito da un contenitore di segmenti [!UICONTROL Person]. Utilizzando una VRS CDA, puoi creare segmenti tra dispositivi quali:

* Utenti che utilizzano più dispositivi
* Chi inizia il percorso su un dispositivo mobile e successivamente acquista su un dispositivo desktop
* Visite in cui le persone utilizzano più dispositivi per eseguire un’attività

*Contenitore*
![[!DNL Segment Builder] [!UICONTROL Person] segmenti a livello di persona](assets/cda-segment-builder-person-container.png)

### Persistenza Dimension

All’interno di una VRS CDA, dimensioni come [!DNL eVars] persistono automaticamente tra i dispositivi. Ad esempio, un [!DNL eVar] configurato come:

* Allocazione: Più recente (ultimo)
* Scadenza dopo: Acquisto

persisterà automaticamente da un dispositivo all&#39;altro fino all&#39;attivazione dell&#39;evento di acquisto.

## Analisi dei dati tra dispositivi in Analysis Workspace

### Analisi del pubblico basata su persona

Vi siete mai chiesti quante persone interagiscono con il vostro marchio? Avete voluto capire quanti e che tipo di dispositivi utilizzano? Come si sovrappone il loro utilizzo? Utilizzando una VRS CDA, è possibile creare diagrammi di Venn [e diagrammi di Venn](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/venn.html) e dispositivi per persona [istogrammi](https://docs.adobe.com/content/help/en/analytics/analyze/analysis-workspace/visualizations/histogram.html).

*Analisi del pubblico basata su personaVenn e*
![Istogramma](assets/cda-venn-and-histogram.png)

### Cross-Device [!DNL Flow]

Con CDA e Analysis Workspace, puoi visualizzare il modo in cui le persone si spostano da un dispositivo all’altro nel tempo in [[!DNL Flow visualization]](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/visualizations/flow/flow.html). Potete vedere dove abbandonano nel loro percorso e dove continuano.

*[!DNL Flow]con CDA*
![[!DNL Flow Visualization]](assets/cda-flow-viz.png)

### Cross-Device [!DNL Fallout]

È probabile che si utilizzino diversi [[!DNL Fallout visualizations]](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/visualizations/fallout/fallout-flow.html) per analizzare in che modo gli utenti lo fanno attraverso una determinata serie di passaggi prima di raggiungere il successo. Sapevi che la tua visione di questi [!DNL Fallout visualizations] è limitata quando usi le analisi tradizionali basate su dispositivi? Per eseguire con successo il passaggio &quot;fall-through&quot;, il passaggio successivo deve verificarsi nello stesso browser o app del passaggio precedente. Nelle analisi basate su dispositivi, non sei cieco nei confronti delle persone che hanno completato con successo il passaggio successivo su un altro dispositivo.

Non ti preoccupare, CDA ti ha coperto. CDA crea la visualizzazione cross-device che rende [!DNL Fallout visualizations] molto, molto più utile. Dopo tutto, ciò che conta veramente è se la persona alla fine è riuscita nel loro compito da qualche parte.

*[!DNL Fallout]con CDA*
![[!DNL Fallout Visualization]](assets/cda-fallout-viz.png)

### [!DNL Cross-Device Attribution IQ]

Poiché CDA crea un livello di dati multi-dispositivo sotto Analysis Workspace, tutte le tue analisi saranno aromatizzate con una prospettiva multi-dispositivo. Un esempio potente è attraverso [[!DNL Attribution IQ]](https://docs.adobe.com/content/help/it-IT/analytics/analyze/analysis-workspace/panels/attribution/attribution.html). [!DNL Attribution IQ] in Analysis Workspace puoi confrontare più modelli di attribuzione uno accanto all’altro. Utilizzando questa funzionalità con CDA, ora puoi confrontare come diversi dispositivi contribuiscono al successo.

Ad esempio, supponi di voler capire quanto spesso un telefono cellulare è il primo dispositivo utilizzato in un&#39;interazione che alla fine porta al successo. Ciò rappresenta il &quot;tasso di acquisizione&quot; del telefono cellulare. CDA + [!DNL Attribution IQ] consente di eseguire questa analisi:

*[!DNL Attribution IQ]con CDA*
![[!DNL Attribution IQ]](assets/cda-attribution-iq.png)

Per ulteriori informazioni, consulta la [[!DNL Cross-Device Analytics] documentazione della guida](https://docs.adobe.com/content/help/it-IT/analytics/components/cda/cda-home.html).
