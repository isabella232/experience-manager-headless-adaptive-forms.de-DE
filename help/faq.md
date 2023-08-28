---
title: Häufig gestellte Fragen
description: Häufig gestellte Fragen
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
keywords: Headless, adaptives Formular, FAQ
hide: false
exl-id: 5bfc307d-96a3-4007-b65f-32176ecdb710
source-git-commit: 47ac7d03c8c4fa18ac3bdcef04352fdd1cad1b16
workflow-type: tm+mt
source-wordcount: '429'
ht-degree: 2%

---

# Häufig gestellte Fragen (FAQ) {#headless-adaptive-forms-faq}

## Sollte ich React.js kennen, um Headless-adaptive Formulare zu verwenden?

Sie können jedes Framework, jede Bibliothek oder jede Sprache verwenden, um Headless-adaptive Formulare wiederzugeben und unsere REST-APIs zum Überprüfen und Senden der Formulare zu verwenden. Die AF-Core-Bibliothek, die OOTB bereitgestellt wird, ist Framework-unabhängig. React-Render- und React-component-Bibliotheken, die OOTB zur Verfügung gestellt werden, sind für Sie bequem. Sie können eigene Komponenten entwickeln und sind nicht auf deren Verwendung beschränkt.

<!-- 
## Did Adobe release a new AEM Archetype for Headless adaptive forms?

You can use Archetype 37 with flag `includeFormsheadless` or later flag to create an AEM project with Headless adaptive forms functionality. 

-->

## Benötige ich eine as a Cloud Service Forms-Sandbox zur Verwendung von Headless-adaptiven Formularen?

Sie können die Starter-App verwenden, um Ihre Headless-adaptiven Formulare zu entwickeln und zu gestalten. Sie benötigen Forms, das as a Cloud Service ist, Headless-adaptive Formulare zusammen mit Backend-Formularfunktionen zu hosten und bereitzustellen.

<!-- ## Do I need an archetype project to develop Headless adaptive forms?

You can use the starter app to start developing and styling your Headless adaptive forms. Later on, you can use the 
archetype project to deploy the finished Headless adaptive forms and corresponding custom code, created using starter app, to Forms as a Cloud Service environment. The Forms as a Cloud Service environment helps you test and productionize the forms. -->

## Wo erhalte ich eine Vorschau für ein adaptives Headless-Formular? {#storybook-example}

Sie können die Starter-App verwenden, um ein benutzerdefiniertes Headless-adaptives Formular zu rendern und in der Vorschau anzuzeigen. Sie können auch eine [Storybook](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-examples--introduction) Beispiel für die Vorschau eines adaptiven Formulars ohne Kopfzeilenmodus.

![](/help/assets/storybook-example.png)

## Ist es möglich, Headless-adaptive Formulare mit benutzerdefinierten Frameworks zu verwenden?

Headless-adaptive Formulare basieren auf [Standardspezifikation](/help/assets/Headless-Adaptive-Form-Specification.pdf). Sie können die Spezifikation erweitern, um sie zum Erstellen benutzerdefinierter Komponenten zu verwenden. Beispielsweise Komponenten für die Chakra-Benutzeroberfläche, Vue.js und mehr.

## Unterstützen Headless adaptive Formulare kaskadierende Felder?

In kaskadierenden Feldern hängt der Inhalt des zweiten Felds vom im ersten Feld ausgewählten Inhalt ab. Die [Storybook](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/adaptive-form-dynamic-behavior—options&amp;args=formJson.items[0].fieldType:drop-down;formJson.items[0].minimum:!undefined;formJson.items[0].maximum:!undefined;formJson.items[0].label.value:Choose+number+of+options;formJson.items[0].enum[0]:1;formJSp son.items[0].enum[1]:2;formJson.items[0].enum[2]:3;formJson.items[1].fieldType:drop-down) bietet ein Beispiel für kaskadierende Felder.

## Lassen adaptive Formulare mit Headless das Vorausfüllen von Formularen mit personalisierten Daten zu?

Headless adaptive Formulare ermöglichen das Vorausfüllen von Formularen mit personalisierten Daten. Die [Storybook](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-examples--prefill-form-with-personalised-data) bietet ein Beispiel dafür, wie Sie ein adaptives Headless-Formular vorab ausfüllen können.

<!-- >
## Can I use existing Adaptive Forms editor to create a Headless adaptive form?

At this moment, you use the Adaptive Form Editor to specify the JSON structure and set submit action for the forms. Support for drag-and-drop components, applying rules using editor, and more editor-related options would be available later in the beta phase. Keep a watch on release notes.  -->

## Kann ich adaptive Formulare mit Headless-Angular-SPA verwenden?

Sie können das Web SDK verwenden, um Headless-adaptive Formulare in Angular-SPA zu integrieren. Sie ist unabhängig von jedem Rahmen. Sie können React SDK als Referenz verwenden.

<!-- ## Should the `-r prerelease` switch be used every time to start the AEM SDK instance or only for the first time?

During the limited release program, use the `-r prerelease` switch every time you start the AEM SDK instance. 

## What is AEM Forms add-on (.far file) and how to install it?

Adobe Experience Manager Forms as a Cloud Service feature archive provides tools to create Headless adaptive forms on the local development environment. To install the feature archive, see [Setup development environment](setup-development-environment.md).

<!-- 
## Where do one get the license.properties file from?

You do not require a license.properties file to run AEM Cloud Service SDK. 

-->

## Gibt es irgendein Plugin, um die Entwicklung für Headless AF zu erleichtern?

Ja, für Microsoft Visual Studio Code ist eine Erweiterung verfügbar. Es bietet eine praktische Möglichkeit, die JSON-Datei für Headless-adaptive Formulare manuell zu erstellen.

## Kann ein Headless-adaptives Formular eine Verbindung zu einem beliebigen CRM herstellen, um Daten zu lesen oder zu schreiben?

Sie können Microsoft Dynamics und Salesforce verwenden, um ein adaptives Headless-Formular zu senden oder vorzufüllen. Zusätzlich zu CRMs unterstützen adaptive Formulare ohne Kopfzeilen das Senden oder Vorbefüllen mit REST-Endpunkten, E-Mail und benutzerdefinierten Übermittlungsaktionen.
