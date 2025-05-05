---
title: Guida completa alla transizione da Google Analytics ad Adobe Analytics
description: Scopri la posizione delle funzionalità equivalenti e come utilizzarle in modo efficiente durante la transizione da Google Analytics ad Adobe Analytics
feature: Third-party Integration
role: User
level: Beginner
kt: 9830
thumbnail: 34749.jpg
exl-id: b2be6081-a1c0-4435-affb-454ed5a74662
source-git-commit: d78c3351d2a98704396ceb8f84d123dd463befe5
workflow-type: tm+mt
source-wordcount: '3413'
ht-degree: 100%

---

# Guida completa alla transizione da Google Analytics ad Adobe Analytics{#comprehensive-guide-for-transitioning-to-Adobe-Analytics}

## 1. Introduzione

Una delle maggiori sfide nella transizione tra strumenti diversi consiste nell’imparare a trovare funzionalità equivalenti e usarle in modo efficiente. Questa discussione fa parte di una guida più ampia per facilitare gli utenti nel passaggio ad Adobe Analytics (sia come nuovo utente che come utente proveniente da Google Analytics). Confronto approfondito con GA; come strumento comparativo più probabile con cui la maggior parte degli utenti acquisirà familiarità; viene fornito per aiutare gli utenti a correlare le conoscenze esistenti al nuovo set di strumenti. Quando non è possibile sostituire la pratica, questo ti aiuta a iniziare e ridurre le frustrazioni che potresti incontrare durante questo periodo.

Dovremmo anche fare un rapido confronto terminologico:

| **Descrizione** | **Adobe Analytics** | **Google Analytics** |
|--------------------------------------------------------------------------------------------------------------------------------|---------------------|----------------------|
| È stata visualizzata una metrica evento che rappresenta una pagina (o una schermata di un’app) | Visualizzazioni di pagina | Pageview |
| Una metrica che rappresenta un gruppo di interazioni, nel sito web o nell’app, che si verificano nello stesso arco temporale | Visita | Sessione |
| Una metrica che definisce un dispositivo identificato (in base a più criteri, inclusi cookie e altri pattern di comportamento per unire le informazioni utente) | Visitatore univoco | Utente |

## 2. Interfacce

Quando le persone confrontano Adobe Analytics e Google Analytics, osservano che l’interfaccia di Adobe all’inizio è impegnativo. Questo è vero ma, credeteci o no, è anche un punto di forza, non una debolezza. Adobe offre un’ampia gamma di strumenti e grande flessibilità nella visualizzazione dei dati, consentendoti di creare in modo molto più libero ciò di cui hai bisogno.

Cominciamo guardando il reporting “in-site”.

### 2.1. Reporting in-site

#### 2.1.1. Schermata iniziale

Sia Adobe Analytics che Google Analytics consentono di personalizzare la prima visualizzazione offerta all’utente nel momento dell’accesso.

##### 2.1.1.1. Schermata Home area di lavoro/personalizzata (Adobe Analytics)

Adobe Analytics non presume di creare un rapporto predefinito visibile a tutti gli utenti all’accesso. La pagina Home predefinita porta l’utente alla schermata di destinazione dell’area di lavoro che mostra a ogni utente tutti i rapporti dell’area di lavoro creati o condivisi. Inoltre, ogni utente ha la possibilità di impostare uno qualsiasi di questi rapporti come schermata Home, se lo desidera.

![workspace-create-project](assets/ga-to-aa_1.png)

Di seguito in questa guida saranno riportati ulteriori dettagli sull’area di lavoro. Cfr. sezione 2.1.2.1

>[!TIP]
>
>Crea/condividi alcuni rapporti standard per la tua organizzazione in modo che abbiano un punto di partenza per visualizzare le informazioni senza doversi immergere nella creazione dei rapporti.



##### 2.1.1.2. Informazioni approfondite sulla schermata Home (Google Analytics)

* La schermata Home di Google Analytics offre alcune visualizzazioni predefinite per te. Tra queste troviamo:
* Utenti, Sessioni, Frequenza di rimbalzo e Durata della sessione negli ultimi sette giorni
* Utenti per ora del giorno negli ultimi 30 giorni
* Utenti attuali e pagine attive principali
* Canale di traffico, Origine/media e Riferimenti negli ultimi sette giorni
* Sessioni per Paese negli ultimi sette giorni
* Pagine principali per gli ultimi sette giorni
* Tendenza utenti attivi per gli ultimi 30 giorni
* e altro ancora

In GA4 gli utenti hanno più opzioni per personalizzare e aggiungere i propri rapporti alla schermata iniziale.

![google-analytics-interfaces](assets/ga-to-aa_2.png)

Questa è probabilmente l’unica cosa che ti manca di più in Adobe Analytics. Non c’è una schermata iniziale predefinita per te. Tuttavia, puoi facilmente impostare un’area di lavoro personalizzata per riprodurre ciò di cui hai bisogno dall’elenco precedente e impostarla come schermata di destinazione. Tratteremo ulteriormente questo argomento in seguito (oppure consulta la sezione 2.1.2.1 di Adobe Workspace).

#### 2.1.2. Report Builder nel sito

Oltre ai rapporti semplici forniti dagli strumenti di analisi, ogni strumento fornisce anche funzioni più potenti con cui creare rapporti personalizzati.

##### 2.1.2.1. Adobe Analytics Workspace

Questa è il punto forte di Adobe Analytics: dalla sua introduzione nel 2017 è diventata l’area ideale per l’analisi di Analytics e la ragione principale per cui la sezione Rapporti verrà presto ritirata.

Questo strumento consente di creare rapporti con una libertà pressoché completa.

Il rapporto può essere suddiviso in pannelli in cui è possibile inserire un numero qualsiasi di visualizzazioni. I pannelli possono essere impostati su informazioni comuni, ad esempio un intervallo di date e i filtri di segmenti più comuni.

I pannelli e le visualizzazioni al loro interno possono essere ridimensionati e trascinati per mostrare i vari elementi uno accanto all’altro o sovrapposti. Per confrontare due diverse suite di dati una accanto all’altra, puoi creare dei pannelli divisi a metà lungo il centro, in modo da mostrare, ad esempio, due siti affiancati per facilitarne il confronto.

Sono disponibili numerose visualizzazioni:

* Tabella a forma libera
* Tabella coorte
* Fallout (abbandono)
* Flusso
* Grafici
   * Ad aree (sovrapposte e non sovrapposte)
   * A linee
   * A dispersione
   * A barre (sovrapposte e non sovrapposte)
   * Bullet
   * Ad anello
   * Istogramma
   * A barre orizzontali (sovrapposte e non sovrapposte)
* Mappa
* Blocchi di riepilogo
   * Variazione di riepilogo
   * Testo di riepilogo
   * Testo (campo di testo libero per inserire ulteriori informazioni di contesto)
* Venn

A ogni pannello e visualizzazione è possibile assegnare un nome e una descrizione che fornisca contesto sulle informazioni visualizzate.
Nella soluzione Adobe, i segmenti (essenzialmente filtri per i dati) vengono applicati retroattivamente e possono essere inseriti nelle colonne delle tabelle a forma libera per confrontare i dati uno accanto all’altro. Ad esempio, per confrontare il traffico per due diverse categorie sul sito, si può creare un segmento per “Categoria A” e un altro per “Categoria B”.

![analytics-page-views-report](assets/ga-to-aa_3.png)

Le tabelle a forma libera permettono di usare più colonne e segmentazioni in base alle esigenze, per visualizzare i dati nel modo desiderato.

Se non desideri visualizzare un raggruppamento per data, trascina un’altra dimensione o un altro segmento per visualizzare i dati in modo diverso. Ad esempio, utilizza i segmenti per Tipo di dispositivo, quindi aggiungi un raggruppamento per sistema operativo per gli utenti di Cellulare/Tablet:

![analytics-compare-page-views-report](assets/ga-to-aa_4.png)

Workspace libera tua creatività, senza i vincoli dei raggruppamenti “standard”. Puoi creare le visualizzazioni necessarie per affrontare tutti i confronti che ti servono.

>[!TIP]
>
>Non avere paura di giocare ed esplorare. Ci sono così tanti modi per pensare fuori dagli schemi. Inoltre, la convalida di ciò che hai creato mostra ciò che pensi. L&#39;esperienza aiuta.

Puoi creare metriche calcolate al volo o segmenti che vivono solo all’interno del rapporto per evitare di ingolfare l’archivio dei segmenti e dei calcoli. Ciò ti consente di creare elementi mirati necessari per rapporti specifici senza confondere l’organizzazione con elementi che non sono utilizzabili in altri contesti.

Questa discussione è solo un’introduzione a questo strumento, ci sono altre guide complete per iniziare. Dopo aver esaminato queste guide, puoi creare rapporti completi come i seguenti:

![workspace-dashboard](assets/ga-to-aa_5.png)

Le aree di lavoro non vengono salvate automaticamente, pertanto è più semplice creare un rapporto per un caso specifico senza riempire inutilmente l’archivio dei rapporti.

Un’altra potente funzione delle aree di lavoro è la possibilità di applicare ai tuoi rapporti dei modificatori interattivi sotto forma di menu a discesa. Questi menu a discesa non funzionano sui file in formato CSV o PDF esportati dai rapporti. Tuttavia, all’interno del rapporto live, ti consentono di aggiornare tutte le visualizzazioni in un solo pannello per mostrare lo stesso rapporto in condizioni differenti. È possibile utilizzare più menu a discesa e finché le opzioni non si escludono a vicenda, gli elementi selezionati si sovrappongono per consentire di presentare le informazioni in modo ordinato.

>[!IMPORTANT]
>
>Per ulteriori informazioni sull’utilizzo dei menu a discesa e delle suddivisioni a forma libera, consulta <https://experienceleaguecommunities.adobe.com/t5/adobe-analytics-discussions/the-power-of-dropdown-filters-and-dimension-breakdowns-in-adobe/td-p/434680>

##### 2.1.2.2. Google Analytics: dashboard, report personalizzati e report salvati

Google dispone di alcuni strumenti per la creazione di rapporti all’interno dell’interfaccia. Tuttavia, questi strumenti mantengono ancora la stessa visualizzazione e le stesse limitazioni della sezione rapporti.

A questo punto, chi conosce bene Google Analytics dopo aver letto queste righe potrebbe dire “un momento, esiste anche Google Data Studio, non è un miglior equivalente di Adobe Workspace?” Sì, ma Data Studio tecnicamente non fa parte dello strumento Analytics e consente connessioni a diverse origini di dati. Questo strumento è trattato più avanti nella sezione “Accesso al rapporto esteso” in particolare nella sezione 2.2.3.

Le dashboard e i rapporti personalizzati di Google consentono di richiamare più visualizzazioni in un unico rapporto, ma a differenza di Workspace, si è ancora vincolati a correlazioni semplici e al concetto di quali dati si possono inserire in quali colonne.

Nei rapporti personalizzati, una delle principali sfide è la creazione di un filtro che si applica a tutte le schede del rapporto. Non esiste un modo per confrontare due filtri diversi all’interno dello stesso rapporto.

Per confronti superficiali è più che sufficiente. Sono simili alle dashboard, ai rapporti personalizzati e ai segnalibri legacy di Adobe. Sono strumenti di base forniti per supportare le tue esigenze, che risiedono nella suite di rapporti.

#### 2.1.3. Rapporti

Sia Google che Adobe dispongono di alcuni rapporti navigabili costituiti da tabelle predefinite e semplici grafici della timeline basati su una dimensione.

##### 2.1.3.1. Rapporti di Adobe Analytics

Adobe Analytics dispone anche di una sezione Rapporti, anche se questa viene gradualmente eliminata a favore di Analysis Workspace. In effetti, per questa interfaccia è stata annunciata la fine del ciclo di vita, poiché Workspace è uno strumento più potente. La maggior parte di queste tabelle può essere creata e modificata con maggiore facilità. Le sezioni di Adobe hanno una suddivisione molto più dettagliata, il che può intimidire qualche utente:

![analytics-site-metrics](assets/ga-to-aa_6.png)

Poiché la maggior parte del contenuto di questo elenco è accessibile tramite Workspaces, offrirò una breve panoramica di queste sezioni spiegando come si relazionano con Google Analytics, evidenziando i rapporti che sono ancora rilevanti.

Site Metrics (Metriche del sito) si riferisce alle metriche più comuni (visualizzazioni di pagina, visitatori univoci, visite ed eventi personalizzati che potresti aver configurato). È simile al rapporto Comportamento di Google Analytics, ma include anche alcuni elementi che si possono trovare in Pubblico, in quanto Adobe non separa i tipi di metrica.

Qui troverai anche i rapporti relativi ai “bot”. Il traffico generato dai bot è escluso da tutti i rapporti standard, tuttavia, sono presenti due rapporti per ottenere informazioni approfondite su ciò che accade in tempo reale e sui bot che raggiungono il tuo sito. È un aspetto particolarmente utile se imposti regole bot personalizzate per escludere i bot di spamming conosciuti e che visitano frequentemente il tuo sito. In questo modo puoi raccogliere alcune informazioni sul comportamento dei bot senza sovraccaricare i rapporti principali con quel tipo di traffico. I rapporti sui bot non sono attualmente disponibili in Workspace, ma le nuove funzionalità di reportistica disponibili a breve consentiranno agli utenti di ottenere queste informazioni anche qui.

“Site Content“ (contenuto del sito) è un raggruppamento di dimensioni standard di Adobe: nome della pagina, sezioni del sito, gerarchie, server e altro ancora. Tutti queste dimensioni sono disponibili in Workspace.

“Mobile“ è un raggruppamento di dati specifici per dispositivi mobili, inclusi dispositivi, tipi di dispositivi e altro ancora. Questi disponibili in Workspace.

I percorsi non sono disponibili in Workspace. Workspace dispone di un diagramma di flusso in cui è possibile visualizzare i flussi in entrata e in uscita per singola pagina/valore. Al contrario, “Paths“ (percorsi) ti consentono di visualizzare i percorsi più comuni utilizzati nel sito web. Per impostazione predefinita, “Pages“ (pagine) è il primo rapporto sul percorso configurato. Tuttavia, puoi attivarlo per le proprietà personalizzate, ad esempio un valore “Page type” (tipo di pagina). È possibile esaminare i percorsi all’interno dei tipi di pagina. Un altro aspetto apprezzabile di Paths (Percorsi) è la semplicità con cui vengono presentate le informazioni. Il diagramma di flusso nell’area di lavoro (a seconda della quantità di dati che vuoi vedere) può assumere dimensioni importanti. Consiglio di provare entrambi. Ognuno ha il suo uso e la sua importanza, a seconda di quello che si sta cercando di ottenere. È opportuno notare che qualsiasi dimensione può essere utilizzata nei flussi, mentre i percorsi devono essere impostati su una proprietà nel pannello di amministrazione.

I rapporti relativi a origini del traffico, campagne e canali di marketing sono simili al rapporto Acquisizione di Google. Origini del traffico è incentrato sui Referrer effettivi, le Campagne sui Codici campagna, così come Canali di marketing, ma in questo caso viene applicata una logica extra, determinata dall’utente, sulla modalità di elaborazione delle informazioni. Adobe offre maggiore libertà nella configurazione delle regole. Al contrario, Google esegue tantissime cose e questo rappresenta un cambiamento nel modo di pensare. Per impostazione predefinita, l’attribuzione di Google per i codici campagna è di sei mesi. Per impostazione predefinita, l’attribuzione di Adobe è impostata su una settimana. Puoi modificare l’attribuzione nelle impostazioni dell’amministratore, ma in Workspace puoi applicare l’attribuzione personalizzata a partire da qualsiasi dimensione per offrire una flessibilità molto più rapida.

I rapporti Mantenimento visitatori e Profilo visitatore sono simili ai rapporti Pubblico in Google Analytics. Il mantenimento è più incentrato sulla frequenza di ritorno, mentre il profilo del visitatore si concentra maggiormente sulla geografia e sulla tecnologia degli utenti.

I rapporti Conversione personalizzata e Traffico personalizzato sono entrambi rapporti di dimensione personalizzati. Le conversioni sono eVar (variabili di conversione). Puoi impostare una scadenza personalizzata in base al valore come hit, visita, mese e anno. Questo valore permane per un utente per l’arco temporale configurato, a meno che non venga sovrascritto. Le variabili di traffico sono proprietà. È anche possibile impostarle per i rapporti sui percorsi o come voci di elenco, che suddivideranno più valori in base a un delimitatore scelto.

I supporti sono per Video o File audio in cui hai impostato un tracciamento speciale dei contenuti multimediali.

Rapporti personalizzati è una sezione in cui un utente può personalizzare le colonne e i raggruppamenti creati all’interno dell’interfaccia dei rapporti e salvarli come rapporto personalizzato. Tuttavia, come accennato in precedenza, poiché Workspace consente raggruppamenti e correlazioni molto più potenti, qualsiasi elemento personalizzato dovrebbe essere creato lì. Questa era una buona soluzione prima dell’esistenza di Workspace.

La sezione Segnalibri è simile ai Rapporti personalizzati, dove i rapporti utilizzati di frequente possono essere contrassegnati con segnalibri all’interno dell’interfaccia dei rapporti, per facilitarne l’individuazione.

Dashboard era un prodotto precedente che consentiva alle persone di combinare mini-rapporti di dati in un’unica visualizzazione. Tuttavia, la funzionalità di Workspace (sezione 2.1.2.1) è molto più semplice da utilizzare, in quanto esiste solo come punto di accesso ai rapporti precedenti che devono essere ricostruiti prima che questa funzione venga disattivata.

I target consentono alle persone di creare un rapporto basato su un target entro un determinato arco temporale. I team monitorano le campagne per vedere se possono raggiungere i loro target di traffico.

Tutti i rapporti in quest’area consentono più colonne di metrica e raggruppamenti di dimensioni. Tuttavia la semplicità delle visualizzazioni e una parte della logica che sta dietro agli elementi che potrebbero essere correlati a volte possono essere frustranti.

##### 2.1.3.2. Rapporti di Google Analytics

Google Analytics suddivide questi rapporti nelle sezioni seguenti: In tempo reale, Pubblico, Acquisizione, Comportamento e Conversazioni (in GA3) e in Ciclo di vita (con le sottosezioni: Acquisizione, Coinvolgimento, Monetizzazione, Mantenimento) e Utente (con le sottosezioni: Demografia e Tecnologia).

![google-analytics-interface-compare](assets/ga-to-aa_7.png)

Puoi apportare alcune modifiche minori a queste visualizzazioni, aggiungere una suddivisione secondaria delle dimensioni, modificare la visualizzazione, creare un filtro per i dati, ecc. Puoi salvare le personalizzazioni come Rapporto salvato.

In questo modo puoi ottenere informazioni semplici e veloci sui tuoi dati. Tuttavia, non è possibile confrontare elementi come Utenti con visualizzazioni di pagina per una pagina nella stessa tabella e non è possibile aggiungere più di una dimensione aggiuntiva per visualizzare ulteriori dati.

Questi vanno bene per i dati analitici rapidi ma hanno dei limiti se hai bisogno di essere più specifico.

### 2.2. Accesso ai rapporti estesi

Oltre a “Generazione rapporti in-site”, la maggior parte degli strumenti offre funzionalità estese che consentono di portare l’analisi al di fuori degli strumenti e creare qualcosa di un po’ più personalizzato.

#### 2.2.1. Report Builder di Adobe Analytics (estensione per Microsoft® Excel)

Workspace è un ottimo strumento, ma a volte è necessario inserire i dati in un foglio di calcolo personalizzato, in modo da poter unire più origini di dati. E qui entra in gioco Report Builder.

Report Builder è un plug-in per Microsoft® Excel che consente di creare connessioni ai dati Adobe Analytics per estrarre dati tabulari su cui lavorare in Excel. In genere, per utilizzarlo in modo efficiente, puoi inserire i dati in alcune schede di dati non elaborati, utilizzare poi i riferimenti alle celle excel per richiamare i dati da queste schede in un unico rapporto consolidato, e quindi creare grafici e visualizzazioni.

>[!NOTE]
>
>Per accedere al plug-in Report Builder è necessario assegnare un’autorizzazione speciale agli utenti. L’autorizzazione dovrà probabilmente essere concessa solo agli utenti che hanno imparato a utilizzare correttamente lo strumento.

#### 2.2.2. Connessione API di Adobe Analytics

Se desideri comunque i vantaggi dei dati elaborati, comprese le esclusioni di regole bot, ma preferisci che Adobe Analytics passi attraverso qualcosa di diverso da Excel, puoi utilizzare l’API di Adobe per estrarre i dati direttamente. Quindi elaborarli tramite script o aggiungerli a un database da utilizzare con un altro sistema.

È opportuno notare che l’API estrae i dati di correlazione applicando i raggruppamenti e i segmenti come specificato nella richiesta pull.

Workspace di Adobe (sezione 2.1.2.1) utilizza di fatto l’API per generare tutti i rapporti. Se abiliti la modalità di debug in Workspace, potrai vedere le chiamate API utilizzate. Questa modalità ti permette di creare rapidamente le tue chiamate API. Infatti puoi utilizzare Workspace per generare e convalidare i dati che desideri richiamare e quindi le relative chiamate API per inserire i dati dalla tua elaborazione.


#### 2.2.3. Google Analytics Data Studio

Se hai letto fino a qui, saprai già che ho citato Data Studio come equivalente di Adobe Workspace. Data Studio consente di richiamare i dati di Google Analytics, ma anche da altre origini. Questa funzione è utile per consolidare i dati di analisi con gli altri dati raccolti. Tuttavia, con Google Analytics sono presenti gli stessi tipi di limitazioni di visualizzazione. Il modo in cui vengono formate le righe e le colonne è ancora limitato.

È ancora uno strumento potente e non dissuaderei le persone da utilizzarlo in alcun modo. Secondo la mia esperienza, il comportamento rigido è piuttosto limitante.


#### 2.2.4. Estensione Fogli Google

Per le mie necessità, quando ho bisogno di richiamare i dati in modo esteso da Google Analytics, lo strumento che scelgo è l’estensione Fogli Google. Anche se ho bisogno di creare più connessioni alle mie tabelle GA, posso fare riferimento alle celle dai dati non elaborati e creare i report di cui ho bisogno. Poi li visualizzo utilizzando le funzionalità relative ai grafici del foglio di calcolo di Google.


## 3. Esportazioni di dati non elaborati

Per le situazioni in cui servono solo dati non elaborati, è possibile utilizzare sia Adobe che Google.

### 3.1. Feed di dati di Adobe

Nella sezione 2.2.2, ho menzionato che l’API Adobe Analytics richiama “dati elaborati”. Il feed di dati non elaborati richiama i dati elaborati dalle “Regole di elaborazione” configurate nel pannello di amministrazione, ma questi dati non elaborati includono tutti i dati esclusi in qualsiasi altro luogo.

Questo significa che nei feed di dati non elaborati verranno inclusi i dati filtrati di IP interni, tutte le esclusioni di bot e altri dati esclusi. Specifici flag consentono di identificare tali dati in modo che, se si sta creando un data lake, il team tecnico possa creare una specifica logica di elaborazione.

I feed di dati non elaborati possono essere personalizzati per inviare tutte le colonne di dati oppure, per un feed più mirato, solo colonne specifiche.

I feed possono essere inviati direttamente a FTP, SFTP o S3.


### 3.2. Google Big Query

Sfortunatamente, questo è uno strumento Google sul quale non ho alcuna esperienza di utilizzo, ma in teoria dovrebbe essere simile al feed dati di Adobe e consentire al tuo team tecnico di accedere ai dati non elaborati dall’account Google Analytics.

Tuttavia, invece di fornire un dump completo dei dati non elaborati, permette ai tecnici di accedere ai dati tramite query SQL per estrarre dati non elaborati di destinazione o tutte le colonne di dati non elaborati.

## 4. Conclusione

Come qualsiasi sistema, per acquisire dimestichezza con lo strumento è necessaria la pratica. Questa guida ti aiuta a iniziare a utilizzare Adobe Analytics e fornisce suggerimenti per migliorarne l’utilizzo.

Ti consigliamo comunque di utilizzare sia Adobe Analytics sia Google Analytics nella strategia di implementazione (anche se Google Analytics è solo nella versione gratuita). Potrai così disporre di un sistema di backup per garantire la disponibilità di dati, perché nessun sistema è infallibile.

Oltre a questa guida sono disponibili numerose risorse che possono contribuire a migliorare la tua strategia:

* [Adobe Experience League](https://experienceleague.adobe.com/it?lang=it#home) - Contiene tutorial, video, documentazione e i forum della community
* [Gruppi di utenti Adobe](https://analytics-augs.adobe.com/): un hub di eventi gestiti dalla community per consentire agli utenti di connettersi tra loro e migliorare le implementazioni.
* [Canale YouTube del gruppo utenti di Adobe Analytics](https://www.youtube.com/channel/UCQOHnCs7KZgsuFHVzwboQuA) - Non puoi partecipare a una sessione del gruppo utenti di Adobe Analytics? Guarda le sessioni precedenti da tutto il mondo e scopri come altri professionisti come te utilizzano questo strumento.
* [Canale Slack di Measure Chat](https://www.measure.chat/) - Entra in contatto con gli utenti di Adobe Analytics in tutto il mondo e condividi esperienze nel settore, fai domande ad altri professionisti come te e partecipa a gruppi di interesse incentrati sulla misurazione.
* E altro ancora!

## Autore

Questo documento è stato scritto da:

![Jennifer Dungan](assets/Jennifer_Dungan_Headshot150.png)

Jennifer Dugan, Optimization Manager Analytics presso Torstar

Adobe Analytics Champion

