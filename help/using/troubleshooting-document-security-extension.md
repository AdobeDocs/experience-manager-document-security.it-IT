---
title: Risoluzione dei problemi di AEM Document Security Extension for Microsoft Office
description: In caso di problemi durante l’installazione, la configurazione o l’utilizzo di AEM Document Security Extension for Microsoft Office, segui le istruzioni riportate in questo documento.
uuid: 61001ca8-a25a-4879-98ac-563a6eb126e7
contentOwner: khsingh
content-type: reference
topic-tags: using
discoiquuid: bdc3f174-e417-4d3e-b3af-972cdcc10133
exl-id: 98f24032-0774-47f8-bcc5-1ee37b417833
TQID: https://experienceleague.adobe.com/3YVMcSeYDXCWkVeG8HmlJOgja9OwLqs1gpPWP8rhhs0
product_v2:
  - id: e8f6de9b-cf88-4405-8d10-15efa08c230e
  - id: fd1f54a9-f50c-467d-8956-cebbaf4f3eb8
feature_v2:
  - id: fd5d26fd-7180-407d-bbd8-5f8a17f9c0b8
role_v2:
  - id: b69b2659-1057-424e-8fc5-ed9e016dc554
topic_v2:
  - id: c1579802-ddd4-4214-8a91-97b2066abe11
  - id: d095671a-1355-40aa-8b5f-06c33c68080b
source-git-commit: b2df949228acdc23ca7f2c55b72e62c1dba130b8
workflow-type: tm+mt
source-wordcount: 316
ht-degree: 100%

---

# Risoluzione dei problemi di AEM Document Security Extension for Microsoft Office{#troubleshooting-aem-document-security-extension-for-microsoft-office}

## Risoluzione dei problemi di installazione e configurazione {#troubleshootinginstallationandconfiguration}

In caso di problemi durante l’installazione e la configurazione di AEM Document Security Extension for Microsoft Office, accertati di aver seguito attentamente le istruzioni elencate nella sezione “Prima dell’installazione” dell’articolo [Installazione](installing-configuring-aemdsext.md).

Se hai eseguito l’installazione e la configurazione seguendo la documentazione, consulta le sezioni seguenti per verificare se sono presenti problemi simili a quelli da te riscontrati.

### Impossibile caricare Document Security Extension per le applicazioni di Microsoft Office {#document-security-extension-fails-to-load-for-microsoft-office-applications}

La proprietà LoadBehavior nel Registro di sistema di Windows specifica il funzionamento in fase di esecuzione del plug-in di protezione dei documenti. Se la proprietà LoadBehavior è impostata su 3, tutti i plug-in vengono caricati automaticamente. Prima di installare Document Security Extension for Microsoft Office, verifica che il valore della proprietà LoadBehavior sia impostato su 3.

1. Esegui il backup del Registro di sistema di Windows prima di modificarlo. Per istruzioni dettagliate, consulta [Come modificare il Registro di sistema di Windows](https://learn.microsoft.com/it-it/troubleshoot/windows-server/performance/windows-registry-advanced-users).
1. Nell’editor del Registro di sistema, passa a HKEY_CURRENT_USER\Software\Microsoft\Office\Word\Addins\Adobe.DRMIntegration.WordAddin oppure HKEY_LOCAL_MACHINE\Software\Microsoft\Office\Word\Addins\Adobe.DRM.
1. Imposta il valore della proprietà **LoadBehavior** su 3.

1. Chiudi l’editor del Registro di sistema.

Per informazioni dettagliate su LoadBehavior, consulta l’articolo sulle [voci del registro di sistema per i componenti aggiuntivi VSTO](https://learn.microsoft.com/it-it/visualstudio/vsto/registry-entries-for-vsto-add-ins?view=vs-2022&redirectedfrom=MSDN#LoadBehavior).

## Risoluzione dei problemi relativi ad attività amministrative {#admintasks}

In questa sezione vengono descritti i possibili problemi con la versione di AEM Document Security Extension installata.

### Con l’installazione di Document Security Extension, le applicazioni di Microsoft Office presentano problemi di avvio {#microsoft-office-applications-dont-start-smoothly-on-installing-document-security-extension}

Per garantire un avvio ottimale delle applicazioni Office sui computer in cui sono installati Document Security Extension e McAfee VirusScan con scansione all’accesso abilitata, disabilita la protezione da overflow del buffer nella console di McAfee VirusScan.
