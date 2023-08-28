---
title: Erste Schritte mit Headless Adaptive Forms
description: Erste Schritte mit Headless Adaptive Forms
keywords: Headless, adaptives Formular, Tutorial
hide: true
source-git-commit: 0127f8ddede38083f0932b0e8d7efdd0dd77c3a6
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 3%

---


# Erste Schritte mit Headless Adaptive Forms

Dieses Tutorial bietet Ihnen ein durchgängiges Framework zum Erstellen eines Headless-adaptiven Formulars. Das Tutorial ist in einen Anwendungsfall und mehrere Handbücher unterteilt. Jedes Handbuch hilft Ihnen dabei, neue Funktionen zu lernen und zum adaptiven Formular ohne Kopfzeilen hinzuzufügen, das in diesem Tutorial erstellt wird. Sie verfügen nach jedem Handbuch über ein funktionierendes adaptives Headless-Formular. Am Ende dieses Tutorials können Sie Folgendes:

* Erstellen eines Headless-adaptiven Formulars
* Hinzufügen von Geschäftsregeln zum Formular
* Verwenden der Google-Materialbenutzeroberfläche zum Formatieren von Formularen
* Formular vorbefüllen 
* Formular in eine Webseite einbetten

Sie werden außerdem ein Verständnis der Architektur, der verfügbaren Artefakte und der JSON-Struktur von Headless-adaptiven Formularen erstellen.

**Die Journey beginnt mit dem Lernen des Anwendungsfalls**:

Raya Tan, ein Mitglied des Außenministeriums eines Landes, das für seine natürliche Schönheit und florierende Tourismuswirtschaft bekannt ist, überwacht die Verteilung der Visaformulare an Touristen. Diese Formulare stehen auf der Website der Abteilung, nativen mobilen Apps und im PDF-Format zur Verfügung, mit mehreren Sprachoptionen für Touristen zur Auswahl. Die Verwaltung und Skalierung dieser Formulare über verschiedene Plattformen und Technologien hinweg kann jedoch eine Herausforderung darstellen.

Um die Effizienz und Flexibilität ihres Visumantragsverfahrens zu verbessern, hat die Außendienststelle beschlossen, einen Ansatz für Headless-adaptive Formulare zu verfolgen. Diese entkoppelte Architektur trennt das Frontend vom Backend, was eine größere Anpassung und Skalierbarkeit ermöglicht. Die Abteilung plant die Verwendung der React-Komponenten der Google-Material-Benutzeroberfläche, um das Benutzererlebnis der Formulare zu verbessern und gleichzeitig Backend-Funktionen wie digitale Signaturen, Datenintegration, Business Process Management, Datensatzdokument und Nutzungsanalysen zu nutzen.

Die beliebteste Form unter den Touristen ist das Formular &quot;Kontaktaufnahme&quot;, das verwendet wird, um verschiedene Fragen und Anfragen zu stellen. Daher hat sich die ausländische Abteilung entschieden, mit der Implementierung des Konzepts für Headless-adaptive Formulare mit diesem Formular zu beginnen. Dieses Tutorial führt Sie durch den Prozess der Erstellung des Kontaktformulars mithilfe dieser neuen Architektur. Das Endergebnis sieht wie folgt aus:

![Kontaktaufnahme mit dem adaptiven US Headless-Formular](assets/contact-us-headless-adaptive-forms.png)