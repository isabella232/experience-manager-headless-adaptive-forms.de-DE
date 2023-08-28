---
title: Übersicht über AEM Headless-adaptive Formulare
description: Übersicht über AEM adaptiven Formulare ohne Kopfzeilenfunktion.
hide: true
exl-id: cd7c7972-376c-489f-a684-f479d92c37e7
source-git-commit: 0127f8ddede38083f0932b0e8d7efdd0dd77c3a6
workflow-type: tm+mt
source-wordcount: '510'
ht-degree: 3%

---


# Versionshinweise

Willkommen bei der frühzeitigen Version von adaptiven Formularen ohne Experience Manager Headless. Lesen Sie weiter, um Ressourcen und Anweisungen zu erhalten, um zu beginnen und die Version optimal zu nutzen.

Sie können adaptive Adobe Experience Manager Headless-Formulare verwenden, um Formularanwendungen mithilfe von Frontend-UI-Frameworks wie React, Angular und mehr zu erstellen und das Adaptive Forms Web SDK für Funktionen wie Statusverwaltung, Validierung und Integrationen mit verschiedenen anderen Touchpoints zu verwenden.

Die frühe Adopter-Version bietet Ihnen Zugriff auf die Verwendung von Headless-adaptiven Formularen in einer [lokale Entwicklungsumgebung](setup-development-environment.md). Sie können die lokale Entwicklungsumgebung verwenden, um Headless-adaptive Formulare zu erstellen und zu testen.

Adaptive Headless-Formulare werden laufend verbessert. Besuchen Sie diese Seite regelmäßig, um über die neuesten Entwicklungen auf dem Laufenden zu bleiben. Auf dieser Seite finden Sie Informationen zu frühzeitigem Zugriff, aktuellen Versionen, neuen Funktionen, Verbesserungen, Fehlerbehebungen, veralteten Funktionen, speziellen Anweisungen und künftigen Plänen für Änderungen.

<!-- 

## July 2022 (v0.22.1)

### New features

* Introduced the `validateFormData` API. It validates all the components against the rules and constraints an returns the list of errors. The validation takes place on the server.
* Introduced the `FormLoad` event.
* Introduced the `importData` and `exportData`.
* You can now dynamically add or remove items, that expect unqiue values, from a repeatable panel. You can use the `minItems` and `maxitems` constraint to set limit of item.
* You can now use constraint to set maximum file upload size, accepted file types, minimum files, and maximum files to upload.

### Improvements and bug fixes

* The service was executing some event handlers twice. The issue is fixed.
* Fixing Data Generation with different values of dataRef, name and type.

<!-- ### React Renderer component -->

## In der frühen Adoptionsversion verfügbare Artefakte

In der Journey, um Ihnen adaptive Adobe Experience Manager Headless-Formulare bereitzustellen, sind die folgenden Artefakte in der frühen Advertising-Version verfügbar:

### AEM FORMS AS A CLOUD SERVICE SDK

AEM Forms as a Cloud Service SDK zum Erstellen, Speichern und Abrufen von Headless-adaptiven Formularen. Es hilft auch bei der Bereitstellung von Diensten zum Vorausfüllen, serverseitigen Validieren von Regeln und Senden für adaptive Headless-Formulare.

### Forms Web SDK

Das Forms Web SDK bietet die APIs zum Validieren von Einschränkungen, die auf verschiedene Formularfelder angewendet werden, und zum Verbinden der JSON-Formularstruktur mit dem UI-Framework. Es bietet außerdem React Renderer-&#x200B; für Headless-adaptive Formulare, um ein Headless-adaptives Formular in Ihre Anwendung zu integrieren. Die folgenden Komponenten des Web SDK sind verfügbar:

* **[@aemforms/af-response-components](https://www.npmjs.com/package/@aemforms/af-react-components)**
* **[@aemforms/af-response-renderer](https://www.npmjs.com/package/@aemforms/af-react-renderer)**
* **[@aemforms/af-core](https://www.npmjs.com/package/@aemforms/af-core)**

<!-- npm i --save @aemforms/af-react-components @aemforms/af-react-renderer @aemforms/af-core -->

#### Storybook

[Storybook](https://opensource.adobe.com/aem-forms-af-runtime/storybook/) bietet einen Überblick über die verschiedenen Komponenten von Headless adaptiven Formularen. Sie enthält außerdem eine Liste aller unterstützten Komponenten, deren zugehörige Eigenschaften und Einschränkungen.

### Forms-Kernkomponente

<!-- Forms components are the structural elements that constitute the content of the form being authored. These components provide various form fields and ability to customize those fields. -->

Kernkomponenten sind eine Reihe standardisierter WCM-Komponenten (Web Content Management), mit denen Sie die Entwicklungszeit verkürzen und die Wartungskosten Ihrer Formulare reduzieren können. Die Forms-Container-Komponente ist eine Kernkomponente. Dies hilft Ihnen beim Einbetten und Rendern einer JSON-Struktur des Headless-adaptiven Formulars im adaptiven Forms-Editor des as a Cloud Service Forms SDK.

### Adaptive Forms V2-Spezifikationen

Die Spezifikation für Headless-adaptive Formulare bietet detaillierte Informationen zu allen Komponenten, Begrenzungen und Methoden, die zum Definieren von Headless-adaptiven Formularen verfügbar sind. Die Spezifikation ist verfügbar unter [PDF](/help/assets/Headless-Adaptive-Form-Specification.pdf) Format.

### HTTP- und JS-API

[HTTP-APIs](https://opensource.adobe.com/aem-forms-af-runtime/api/) ermöglichen es Ihnen, den Sendestatus von Headless-Formularen aufzulisten, abzurufen, zu validieren, zu senden und zu verfolgen. [JS-APIs](https://opensource.adobe.com/aem-forms-af-runtime/jsdocs/) hilft Ihnen bei der Verwendung von Headless-adaptiven Formularen mit einem beliebigen JavaScript-basierten UI-Framework.

### Visual Studio Code-Erweiterung

[Visual Studio Code-Erweiterung](visual-studio-code-extension-for-headless-adaptive-forms.md) um eine gültige JSON-Struktur zu erstellen. Es bietet IntelliSense-Unterstützung und -Validierung für die JSON-Struktur von Formularen sowie allgemeine Funktionen wie das Hinzufügen, Löschen oder Umbenennen von Komponenten einer JSON-Struktur.

<!-- ## What's next

The following features would be available in upcoming releases:

* HTTP APIs to invoke a business logic.
* Server-side capabilities (Prefill, server-side validation, generating Document of Record (DoR), Submitting to a Form Data Model or using Form Data Models for creating rules, and more).
* Continuous improvements to specifications and Headless adaptive form runtime.
* Use  Adaptive Forms editor for easier management and authoring Headless adaptive forms.
-->