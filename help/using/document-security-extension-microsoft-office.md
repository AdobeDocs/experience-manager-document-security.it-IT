---
title: Introduzione a AEM Document Security Extension for Microsoft® Office
description: Document Security Extension for Microsoft&reg; Office consente di applicare impostazioni di riservatezza predefinite ai file di Microsoft&reg; Office.
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
exl-id: 3e07c031-3f88-4bde-bdb3-b136ef5f9527
source-git-commit: 3b6a686966fb8d006bed8cc4a4bf5eebe0dfb030
workflow-type: tm+mt
source-wordcount: '1248'
ht-degree: 68%

---

# Introduzione a AEM Document Security Extension for Microsoft® Office{#introduction-to-aem-document-security-extension-for-microsoft-office}

L’estensione Adobe® Experience Manager Document Security Extension for Microsoft® Office garantisce che solo le persone autorizzate possano utilizzare file Word, Excel e PowerPoint con contenuti protetti dai diritti di proprietà intellettuale dell’autore. L’utilizzo di Document Security Extension for Microsoft® Office consente di applicare impostazioni di riservatezza predefinite ai file di Microsoft® Office.

Document Security Extension for Microsoft® Office migliora il Rights Management del LiveCycle e la sicurezza dei documenti per Adobe Experience Manager Forms. Protegge i file di Office e consente agli utenti autorizzati di accedere ai file protetti tramite policy in base alle impostazioni di riservatezza stabilite.

## Come Document Security protegge la proprietà intellettuale {#how-document-security-protects-intellectual-property}

L’estensione Document Security garantisce che solo le persone autorizzate possano utilizzare i file protetti dai diritti di proprietà intellettuale dell’autore. Document Security consente infatti di proteggere i file tramite policy (o criteri) di riservatezza. Una *policy* è una raccolta di informazioni che comprendono impostazioni di riservatezza e un elenco di utenti autorizzati. Le impostazioni specificate in una policy determinano il modo in cui un destinatario può utilizzare i file a cui è associata la policy. Consentono di specificare, ad esempio, se i destinatari possono stampare o copiare il testo o salvare le modifiche.

Sia gli amministratori che gli utenti di Document Security possono creare policy. Gli amministratori creano policy organizzative disponibili per tutti gli utenti autorizzati. Gli amministratori e i coordinatori di set di policy possono anche creare gruppi o *set di policy* disponibili per un sottoinsieme di utenti. Gli utenti possono creare policy proprie, che possono essere utilizzate solo dall’utente che le ha create. Gli amministratori, i coordinatori di set di policy e gli utenti possono creare policy utilizzando le pagine web di Document Security.

Sebbene le policy siano memorizzate in Document Security, è possibile applicarle ai file tramite Word, Excel o PowerPoint. Quando si applica una policy a un file, le informazioni contenute nel file vengono protette dalle impostazioni di riservatezza specificate nella policy. Quando si distribuisce il file protetto tramite policy, solo i destinatari autorizzati possono accedere al relativo contenuto.

Se si protegge un file mediante una policy, si ha un controllo costante del file, anche dopo averlo distribuito. Puoi controllare gli eventi per tenere traccia di quando e come i destinatari utilizzano il file. È inoltre possibile apportare modifiche alla policy, impedire agli utenti di continuare ad accedere al file e modificare la policy associata al file.

## Funzionamento dei criteri {#how-policies-work}

Le policy contengono informazioni sugli utenti autorizzati e impostazioni di riservatezza da applicare alla proprietà intellettuale. Document Security riconosce gli utenti inclusi in un elenco LDAP o Active Directory collegato. Possono essere anche persone invitate a registrarsi in Document Security o per le quali l’amministratore ha creato un account.

Le impostazioni di riservatezza di una policy determinano il modo in cui i destinatari possono utilizzare i file protetti dalla policy. Le policy consentono ad esempio di specificare se i destinatari possono stampare i file, copiarne i contenuti in altri file o salvare le modifiche apportate ai file protetti. Con le policy è possibile anche specificare impostazioni di riservatezza diverse per i vari utenti.

Quando si applica una policy a un file, le informazioni contenute nel file vengono protette dalle impostazioni di riservatezza specificate nella policy. Quando si distribuisce il file, Document Security autentica i destinatari che tentano di aprirlo e ne autorizza l’accesso in base ai privilegi specificati nella policy.

Dopo aver applicato un criterio a un file, le impostazioni di riservatezza del criterio possono essere modificate in qualsiasi momento. È possibile aggiungere o rimuovere utenti autorizzati o modificare i privilegi per gli utenti dopo che hanno ricevuto il file. È possibile modificare la policy applicata al file. Inoltre, l&#39;accesso al file può essere revocato in modo che chiunque disponga di una copia del file non possa più aprirlo.

Se la policy consente l’accesso offline, i destinatari possono utilizzare i file protetti tramite policy anche in modalità offline (senza una connessione Internet o di rete attiva) per il periodo di tempo specificato nella policy.

## Funzionamento dei file protetti da un criterio {#how-policy-protected-files-work}

Affinché un utente possa aprire e utilizzare file Word, Excel e PowerPoint protetti tramite policy, la policy deve includere l’utente come destinatario. In alternativa, deve consentire l’accesso anonimo. Inoltre, l’utente deve aver installato Document Security Extension for Microsoft® Office. Per fornire un file protetto tramite policy a un utente che non dispone di Document Security Extension for Microsoft® Office, puoi fornire loro una copia del software. Oppure puoi chiedere loro come scaricarlo dal tuo sito web. Se necessario, il programma di installazione può essere scaricato dalla [pagina di download](https://experienceleague.adobe.com/en/docs/experience-manager-document-security/using/download-installer).

Quando un utente cerca di aprire un file protetto tramite policy, Document Security Extension for Microsoft® Office si connette a Document Security per autenticare l’utente. Se Document Security è configurato per controllare le modalità di utilizzo del file, l’utente riceve una notifica con cui viene informato che l’utilizzo del file è sotto controllo. Document Security determina le autorizzazioni sui file da concedere all’utente, che potrà quindi utilizzare il file in base alle impostazioni della policy, alle seguenti condizioni:

* Per il periodo di validità specificato nella policy.
* Fino a quando un amministratore o la persona che ha applicato la policy non revoca l’accesso al file o modifica la policy.

  Se la persona che ha applicato il criterio lo modifica o revoca l’accesso al file, le autorizzazioni di cui dispone l’utente per il file vengono modificate o rimosse, anche se il file è già in suo possesso. Se il file è stato revocato, è possibile fornire all’utente un URL da cui scaricare una copia aggiornata.

  Se la policy consente l’accesso offline, gli utenti possono aprire file protetti tramite policy senza una connessione Internet o di rete durante il periodo di lease offline specificato. Al termine di questo intervallo di tempo, l’utente deve tornare online ed effettuare la sincronizzazione con Document Security, che avvia un nuovo periodo di lease.

  Se la policy consente l’accesso offline, gli utenti possono aprire file protetti tramite policy senza una connessione Internet o di rete durante il periodo di lease offline specificato. Come per il file originale, vengono controllati e registrati anche gli eventi correlati, ad esempio i tentativi di aprire il nuovo file.

## Utilizzo di Document Security per proteggere i file {#using-document-security-to-protect-your-files}

È possibile utilizzare i criteri per proteggere i file in varie situazioni.

Ad esempio, se un produttore accetta le offerte di vari fornitori di componenti per un nuovo prodotto, il produttore deve necessariamente fornire agli offerenti le informazioni proprietarie necessarie per finalizzare le loro proposte. Utilizza quindi Document Security per proteggere i file con una policy che consenta ai candidati di aprire i file e visualizzarne le informazioni, senza tuttavia poter modificare, stampare o copiare i file. Chiunque non disponga delle necessarie autorizzazioni, inoltre, non potrà aprire i file.

Dopo aver accettato un&#39;offerta, il produttore aggiorna la policy per concedere al candidato vincitore le autorizzazioni per stampare, copiare e salvare le modifiche localmente. Il produttore rimuove anche gli offerenti non aggiudicatari, revocando l&#39;autorizzazione ad aprire i file.

Durante il lavoro con l’offerente selezionato, gli ingegneri del produttore modificano alcune delle specifiche di progettazione contenute nei file. Per pubblicare le nuove specifiche, il produttore revoca l’accesso ad alcuni file e pubblica le nuove versioni. Quando gli ingegneri del candidato vincitore tentano di aprire il file, viene visualizzato un messaggio con cui vengono informati che l’accesso al file è stato revocato. Il messaggio contiene inoltre un URL da cui possono scaricare la nuova versione del file.

## Informazioni aggiuntive {#additional-information}

Le risorse elencate in questa tabella consentono di acquisire maggiore familiarità con AEM Document Security:

<table >
 <tbody>
  <tr>
   <th><p>Per informazioni su</p> </th>
   <th><p>Consulta</p> </th>
  </tr>
  <tr>
   <td><p>Guida per gli amministratori di AEM Forms</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/forms/administrator-help/get-started/configure-general-aem-forms-settings">Guida per gli amministratori</a> o, nelle pagine di amministrazione di Document Security, fai clic sul collegamento Help, in alto a destra.</p> </td>
  </tr>
  <tr>
   <td><p>Aggiornamenti patch, note tecniche e informazioni aggiuntive su questa versione del prodotto</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/?support-solution=General&amp;support-tab=home&amp;lang=it#support">Supporto tecnico di Experience Cloud</a></p> </td>
  </tr>
 </tbody>
</table>
