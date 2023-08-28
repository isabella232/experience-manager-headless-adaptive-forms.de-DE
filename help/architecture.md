---
title: Headless-Architektur für adaptive Formulare
description: Erfahren Sie mehr über die Architektur von AEM Forms Headless Adaptive Forms und wie Sie damit schnell Formulare für verschiedene Plattformen erstellen können. Dieser Artikel bietet Einblicke in die Funktionsweise von Headless Adaptive Forms und deren Integration in verschiedene Anwendungen, um den Formularerstellungsprozess zu vereinfachen.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
keywords: Headless, adaptives Formular, Architektur
hide: false
exl-id: ee7096d8-89e2-41e0-85e7-b26457df96fb
source-git-commit: 47ac7d03c8c4fa18ac3bdcef04352fdd1cad1b16
workflow-type: tm+mt
source-wordcount: '916'
ht-degree: 0%

---


# Wie funktioniert das adaptive Formular &quot;Headless&quot;?

Ein Headless-adaptives Formular ist im Wesentlichen eine JSON-Struktur (Schema), die aus Formularfeldern (Textfeld, Auswahl und viele weitere Felder) und entsprechenden Regeln (Bedingungslogik) besteht, um dem Formular interaktives Verhalten hinzuzufügen. Sie können REST-APIs in Ihrer Anwendung oder Website verwenden, um die gehostete JSON-Struktur anzufordern und die JSON-Struktur nativ als Formular in Ihrer App oder Website zu rendern. Ein einzelnes Headless-adaptives Formular kann mehrere Webseiten und Anwendungen bedienen, ohne App- oder Website-spezifische Änderungen daran vorzunehmen.

![Funktionsweise des adaptiven Formulars ohne Kopfzeilen](/help/assets/how-headless-adaprive-forms-work.png)

## Architektur {#architecture}

Eine typische Headless-Architektur für adaptive Formulare bildet einen Adobe Experience Manager Forms-Server, auf Adobe Experience Manager Forms-Server gehostete Headless-adaptive Formulare sowie Ihre Frontend-Apps (Website, mobile Anwendung, JavaScript-Apps, Chat-Anwendungen und mehr) für kanalspezifische Formularwiedergaben.

Die typische Architektur einer Bereitstellung von Headless-adaptiven Formularen sieht wie folgt aus:

![Architektur](/help/assets/headless-af-architecture.png)

<!-- 

You can use the React renderer component shipped with Headless adaptive forms to render an Adaptive Form or build your own custom component to natively render a Headless Form in a website or an application or use any UI framework or programming language to build your own components to render your forms.

A typical Headless adaptive forms architecture constitutes an Adobe Experience Manager Server, JSON structure of forms, various frontend apps for channel-specific form renditions.

![Architecture](/help/assets/headless-af-architecture.png) -->

### Komponente einer Implementierung von Headless-adaptiven Formularen

**Adobe Experience Manager Server**: Neben der Bereitstellung als Host für Headless-adaptive Formulare bietet Adobe Experience Manager die folgenden Backend-Funktionen:

* RESTful-APIs zum Auflisten, Abrufen, Vorausfüllen, Validieren, Senden und Verfolgen des Sendestatus von Headless-Formularen.
* Visual Editor, um einfach ein Headless-adaptives Formular zu entwickeln.
* Forms-Datenmodell zum Empfangen oder Senden von Daten an verschiedene Datenquellen.
* Workflow-Engine zur Automatisierung komplexer Aufgaben.

**Headless-adaptive Formulare**: Ein Headless-adaptives Formular wird als JSON-Datei dargestellt. Die JSON-Struktur definiert Komponenten, Begrenzungen und die Struktur eines Formulars.

**Frontend-Apps**: Frontend-Apps wie SPA (Einzelseiten-Apps), mobile Apps, JavaScript-Apps, verwenden Headless-adaptive Formulare (die JSON-Formulardarstellung) und rendern das Formular auf einem Client. Sie können die React-Renderer-Komponente, die mit Headless-adaptiven Formularen geliefert wird, verwenden, um ein adaptives Formular zu rendern oder Ihre eigene benutzerdefinierte Komponente zu erstellen, um native adaptive Formulare ohne Kopfzeilenfunktion wiederzugeben.

<!-- ### Understanding Headless adaptive forms definition -->



### Entwicklertools

In einem typischen Entwicklungszyklus beginnen Sie mit dem Erstellen und Hosten von Headless-adaptiven Formularen auf Adobe Experience Manager Forms Server. Im zweiten Schritt ordnen Sie die Komponenten der Benutzeroberfläche zu oder verwenden Sie eine Bibliothek mit Komponenten der öffentlichen Benutzeroberfläche, z. B. die Google-Material-Benutzeroberfläche oder die Chakra-Benutzeroberfläche, um Formulare zu gestalten. Im letzten Schritt rufen Sie Headless-adaptive Formulare in Ihrer Anwendung ab und zeigen sie an (Website, mobile Anwendung, JavaScript-Apps, Chat-Anwendungen oder viele andere Oberflächen).

Mit den folgenden Tools können Sie adaptive Headless-Formulare erstellen und in Ihre Anwendungen integrieren:

**Forms Web SDK (Client-seitige Laufzeit)**: Das Forms Web SDK ist eine clientseitige JavaScript-Bibliothek. Dadurch können Sie clientseitige Validierungen auf Formularfelder anwenden, den Status des Formulars beibehalten und das Formular mit einer UI-Ebene oder einer gerenderten Komponente für adaptive Formulare verbinden. Dadurch können Kunden Einschränkungen überprüfen, die auf verschiedene Felder eines Formulars angewendet werden, und Hoks zum Verbinden der JSON-Struktur des Formulars mit dem UI-Framework nutzen. Das Forms Web SDK umfasst die folgenden Komponenten:

* **Business Rule Prozessor**: Der Geschäftsregelprozessor akzeptiert die JSON-Struktur der Formulare als Eingabe, verwaltet den Status der Formularfelder, führt Regeln und Ereignishandler aus, die in der JSON vorhanden sind.
* **React-Bindemittel**: Stellt Hooks über den Controller bereit, um den Status zu Formularkomponenten hinzuzufügen. Dies ist auch beim Vorausfüllen eines Formulars hilfreich.
* **Komponentenbibliothek**: Es stellt React-Spectrum-Komponenten bereit und verwendet Hooks im React-Binder-Modul, um diesen Komponenten Status hinzuzufügen.

Das Forms Web SDK stellt die APIs zur Validierung von Einschränkungen bereit, die auf verschiedene Formularfelder angewendet werden. Außerdem stellt es auch Haken bereit, um Headless-adaptive Formulare mit dem UI-Framework zu verbinden. Es bietet außerdem React Renderer-&#x200B; für Headless-adaptive Formulare, um ein Headless-adaptives Formular in Ihre Anwendung zu integrieren. Die folgenden Komponenten des Web SDK sind verfügbar:

* **[@aemforms/af-response-components](https://www.npmjs.com/package/@aemforms/af-react-components)**
* **[@aemforms/af-response-renderer](https://www.npmjs.com/package/@aemforms/af-react-renderer)**
* **[@aemforms/af-core](https://www.npmjs.com/package/@aemforms/af-core)**

Alle diese Komponenten sind in AEM Archetyp enthalten. Wenn Sie ein AEM Archetyp 37 oder ein späteres Projekt für Headless adaptive Formulare erstellen, ist die neueste Version der oben aufgeführten Bibliotheken im Projekt enthalten.

**Started Application**: Adobe hat auch eine erste Anwendung veröffentlicht, die Ihnen dabei hilft, schnell mit Headless adaptiven Formularen zu beginnen.

<!-- **View Library (UI Layer)**: A custom form application built in a front-end language. You can use react, Angular, Flutter, NPM, Vue.js, Ionic, BootStrap, or any other language to built front end. You can also use the Headless adaptive forms Super Component, provided out-of-the-box, inside a react application to render a Headless adaptive form. Headless adaptive forms super component makes use of OOTB react spectrum -based form components to render the Headless adaptive form. 

Core-Components: It enables use to render an Adaptive Form using JSON structure. It uses rule grammar to help create dynamic field interactions. The rule grammar is based on [JSON formula](http://github.com/adobe/json-formula/). You can develop your own renderer or embed the React based Adaptive Forms renderer, provided OOTB, in your front-end app to render the form. -->

**Storybook**: [Storybook](https://opensource.adobe.com/aem-forms-af-runtime/storybook/) bietet einen Überblick über die verschiedenen Komponenten von Headless adaptiven Formularen. Sie enthält außerdem eine Liste aller unterstützten Komponenten, deren zugehörige Eigenschaften und Einschränkungen.

**Visual Studio Code-Erweiterung**: [Visual Studio Code-Erweiterung](visual-studio-code-extension-for-headless-adaptive-forms.md) um eine gültige JSON-Struktur zu erstellen. Es bietet IntelliSense-Unterstützung und -Validierung für die JSON-Struktur von Formularen sowie allgemeine Funktionen wie das Hinzufügen, Löschen oder Umbenennen von Komponenten einer JSON-Struktur.

**Adaptive Forms Version 2.0 - Spezifikationen**: Die Spezifikation der adaptiven Forms-Version 2.0 enthält detaillierte Informationen zu allen Komponenten, Einschränkungen und Methoden, die zur Definition von Headless-adaptiven Formularen verfügbar sind. Die Spezifikation ist verfügbar unter [PDF](/help/assets/Headless-Adaptive-Form-Specification.pdf) Format.

**HTTP- und JavaScript-APIs**: [HTTP-APIs](https://opensource.adobe.com/aem-forms-af-runtime/api/) ermöglichen es Ihnen, den Sendestatus von Headless-Formularen aufzulisten, abzurufen, zu validieren, zu senden und zu verfolgen. [JS-APIs](https://opensource.adobe.com/aem-forms-af-runtime/jsdocs/) hilft Ihnen bei der Verwendung von Headless-adaptiven Formularen mit einem beliebigen JavaScript-basierten UI-Framework.

**JSON-Formel**: Es handelt sich um eine Implementierung der Grammatik von Formularausdrücken, die Sie beim Abfragen der JSON-Struktur und beim Erstellen von Regeln für adaptive Formulare ohne Kopfzeilen unterstützt. Die Grammatik ist ein Mashup von tabellenähnlichen Funktionen und Operatoren und [JMESPath](https://jmespath.org/) eine JSON-Abfragesprache. Sie können die [Abspielplatz](https://opensource.adobe.com/json-formula/dist/index.html) , um die Syntax und Funktionen der JSON-Formel zu untersuchen.