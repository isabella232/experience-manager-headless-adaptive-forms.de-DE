---
title: Verwenden Sie Google Material UI-React-Komponenten zum Rendern eines Headless-Formulars
description: Erfahren Sie, wie Sie mit Google Material-UI-React-Komponenten ein Headless-Formular rendern können. Diese umfassende Anleitung führt Sie durch den schrittweisen Prozess zum Erstellen benutzerdefinierter Headless-Adaptive Forms-Komponenten, um Google Material-UI-React-Komponenten zuzuordnen und zu verwenden, um ein Headless-adaptives Formular zu gestalten.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
hide: false
exl-id: 476509d5-f4c1-4d1c-b124-4c278f67b1ef
source-git-commit: 47ac7d03c8c4fa18ac3bdcef04352fdd1cad1b16
workflow-type: tm+mt
source-wordcount: '934'
ht-degree: 1%

---


# Verwenden einer benutzerdefinierten React-Bibliothek zum Rendern eines Headless-Formulars

Sie können benutzerdefinierte Komponenten erstellen und implementieren, um das Erscheinungsbild und die Funktionalität (Verhalten) Ihrer Headless-adaptiven Formulare gemäß Anforderungen und Richtlinien Ihres Unternehmens anzupassen.

Diese Komponenten dienen hauptsächlich dazu, das Erscheinungsbild oder den Stil von Formularfeldern zu steuern und die über diese Felder erfassten Daten in der Formularmodellinstanz zu speichern. Wenn das verwirrend klingt, machen Sie sich keine Sorgen - wir werden diese Ziele in Kürze genauer untersuchen. Zunächst konzentrieren wir uns auf die ersten Schritte zum Erstellen benutzerdefinierter Komponenten, zum Rendern des Formulars mit diesen Komponenten und zum Verwenden von Ereignissen zum Speichern und Senden von Daten an einen REST-Endpunkt.

In diesem Tutorial werden Google-Material-UI-Komponenten verwendet, um zu demonstrieren, wie ein Headless-adaptives Formular mit benutzerdefinierten React-Komponenten wiedergegeben wird. Sie sind jedoch nicht auf diese Bibliothek beschränkt und können jede React-Komponentenbibliothek nutzen oder eigene benutzerdefinierte Komponenten entwickeln.

Mit Abschluss dieses Artikels wird die _Kontakt_ Formular erstellt in [Erstellen und Veröffentlichen eines Headless-Formulars mit dem Starter Kit](create-and-publish-a-headless-form.md) Der Artikel wandelt sich in Folgendes um:

![](assets/headless-adaptive-form-with-google-material-ui-components.png)


Die wichtigsten Schritte bei der Verwendung der Komponenten der Benutzeroberfläche der Google-Materialien zum Rendern eines Formulars sind:

![](assets/headless-forms-graphics-source-main.svg)

## 1. Installieren der Google-Material-Benutzeroberfläche

Standardmäßig verwendet das Starterkit [Adobe](https://spectrum.adobe.com/) Komponenten. Setzen wir es auf [Google-Materialbenutzeroberfläche](https://mui.com/):

1. Stellen Sie sicher, dass das Starterkit nicht ausgeführt wird. Um das Starterkit zu stoppen, öffnen Sie das Terminal und navigieren Sie zum **react-starter-kit-aem-headless-forms** und drücken Sie Strg-C (unter Windows, Mac und Linux ist es dasselbe).

   Versuchen Sie nicht, das Terminal zu schließen. Das Schließen des Terminals hält das Starterkit nicht an.

1. Führen Sie den folgenden Befehl aus:

```shell
    
    npm install @mui/material @emotion/react @emotion/styled --force
    
```

Es installiert die NPM-Bibliotheken der Google-Materialbenutzeroberfläche und fügt die Bibliotheken zu den Abhängigkeiten von Startkits hinzu. Sie können jetzt Komponenten der Materialbenutzeroberfläche zum Rendern von Formularkomponenten verwenden.


## 2. Benutzerdefinierte React-Komponenten erstellen

Erstellen wir eine benutzerdefinierte Komponente, die den Standard ersetzt [Texteingabe](https://spectrum.adobe.com/page/text-field/) Komponente mit [Textfeld der Google-Materialbenutzeroberfläche](https://mui.com/material-ui/react-text-field/) -Komponente.

Für jeden Komponententyp ist eine separate Komponente erforderlich ([fieldType](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-json-properties-fieldtype--text-input) oder :type), die in einer Definition für Headless Form verwendet wird. Beispielsweise können Sie im Kontaktformular, das Sie im vorherigen Abschnitt erstellt haben, die Felder Name, E-Mail und Telefon vom Typ `text-input` ([fieldType: &quot;text-input&quot;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/docs/adaptive-form-components-text-input-field--def)) und das Meldungsfeld vom Typ `multiline-input` ([&quot;fieldType&quot;: &quot;multiline-input&quot;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/docs/reference-json-properties-fieldtype--multiline-input)).


Erstellen wir eine benutzerdefinierte Komponente, um alle Formularfelder zu überlagern, die die [fieldType: &quot;text-input&quot;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/docs/adaptive-form-components-text-input-field--def) Eigenschaft mit [Textfeld der materiellen Benutzeroberfläche](https://mui.com/material-ui/react-text-field/) -Komponente.


Erstellen der benutzerdefinierten Komponente und Zuordnen der benutzerdefinierten Komponente zum [fieldType](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/docs/adaptive-form-components-text-input-field--def) property :

1. Öffnen Sie die **react-starter-kit-aem-headless-forms** Verzeichnis in einem Code-Editor und navigieren Sie zu `\react-starter-kit-aem-headless-forms\src\components`.


1. Erstellen Sie eine Kopie der **Regler** oder **richtext** und benennen Sie den kopierten Ordner in um **materialtextfield**. Slider und RichText sind zwei benutzerdefinierte Beispielkomponenten, die in der Starter-App verfügbar sind. Sie können diese verwenden, um eigene benutzerdefinierte Komponenten zu erstellen.

   ![Die benutzerdefinierte Komponente &quot;materialtextfield&quot;in VSCode](/help/assets/richtext-custom-component-in-vscode.png)

1. Öffnen Sie die `\react-starter-kit-aem-headless-forms\src\components\materialtextfield\index.tsx` und ersetzen Sie den vorhandenen Code durch den unten stehenden Code. Dieser Code gibt eine [Textfeld der Google-Materialbenutzeroberfläche](https://mui.com/material-ui/react-text-field/) -Komponente.

```JavaScript
 
     import React from 'react';
     import {useRuleEngine} from '@aemforms/af-react-renderer';
     import {FieldJson, State} from '@aemforms/af-core';
     import { TextField } from '@mui/material';
     import Box from '@mui/material/Box';
     import { richTextString } from '@aemforms/af-react-components';
     import Typography from '@mui/material/Typography';


     const MaterialtextField = function (props: State<FieldJson>) {

         const [state, handlers] = useRuleEngine(props);

         return(

         <Box>
             <Typography component="legend">{state.visible ? richTextString(state?.label?.value): ""} </Typography>
             <TextField variant="filled"/>
         </Box>

         )
     }

     export default MaterialtextField;
```


Die `state.visible` -Teil überprüft, ob die Komponente als sichtbar festgelegt ist. Ist dies der Fall, wird der Feldtitel abgerufen und mit `richTextString(state?.label?.value)`.

![](/help/assets/material-text-field.png)


Ihre benutzerdefinierte Komponente `materialtextfield` ist bereit. Legen wir diese benutzerdefinierte Komponente fest, um alle Instanzen von zu ersetzen.  [fieldType: &quot;text-input&quot;](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/docs/adaptive-form-components-text-input-field--def) mit dem Textfeld der Google-Materialbenutzeroberfläche.

## 3. Zuordnen benutzerdefinierter Komponenten zu Headless-Formularfeldern

Der Prozess der Verwendung von Bibliothekskomponenten eines Drittanbieters zum Rendern von Formularfeldern wird als Zuordnung bezeichnet. Jeder wird zugeordnet ([fieldType](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-json-properties-fieldtype--text-input)) der entsprechenden Komponente der Drittanbieterbibliothek.

Alle zuordnungsbezogenen Informationen werden zum `mappings.ts` -Datei. Die `...mappings` -Anweisung im `mappings.ts` -Datei bezieht sich auf die Standardzuordnungen, die die ([fieldType](https://opensource.adobe.com/aem-forms-af-runtime/storybook/?path=/story/reference-json-properties-fieldtype--text-input) oder :type) mit [Adobe Spectrum](https://spectrum.adobe.com/page/text-field/) Komponenten.

So fügen Sie die Zuordnung für  `materialtextfield` Komponente, erstellt im letzten Schritt:

1. Öffnen Sie die Datei `mappings.ts`.

1. Fügen Sie die folgende Importanweisung hinzu, um die `materialtextfield` -Komponente `mappings.ts` Datei:


   ```JavaScript
       import MaterialtextField from "../components/materialtextfield";
   ```

1. Fügen Sie die folgende Anweisung hinzu, um die `text-input` mit der materialtextfield -Komponente.


   ```JavaScript
       "text-input": MaterialtextField
   ```

   Der endgültige Code der Datei sieht wie folgt aus:

   ```JavaScript
         import { mappings } from "@aemforms/af-react-components";
         import MaterialtextField from "../components/materialtextfield";
   
   
         const customMappings: any = {
           ...mappings,
           "text-input": MaterialtextField
        };
        export default customMappings;
   ```

1. Speichern Sie die App und führen Sie sie aus. Die ersten drei Felder des Formulars werden mithilfe von [Textfeld der Google-Materialbenutzeroberfläche](https://mui.com/material-ui/react-text-field/):

   ![](assets/material-text-field-form-rendetion.png)


   Auf ähnliche Weise können Sie benutzerdefinierte Komponenten für die Felder &quot;message&quot;(&quot;fieldType&quot;: &quot;multiline-input&quot;) erstellen und den Dienst (&quot;fieldType&quot;:&quot;number-input&quot;) bewerten. Sie können das folgende Git-Repository für benutzerdefinierte Komponenten der Nachricht klonen und die Dienstfelder bewerten:

   [https://github.com/singhkh/react-starter-kit-aem-headless-forms](https://github.com/singhkh/react-starter-kit-aem-headless-forms)

## Nächster Schritt

Sie haben das Formular erfolgreich mit benutzerdefinierten Komponenten wiedergegeben, die die Benutzeroberfläche von Google Material verwenden. Haben Sie versucht, das Formular zu senden, indem Sie auf die Senden-Schaltfläche klicken (der entsprechenden Google Material UI-Komponente zugeordnet)? Wenn nicht, versuchen Sie es.

Sendet das Formular die Daten an eine Datenquelle? Nein? Mach dir keine Sorgen. Dies liegt daran, dass Ihr Formular nicht für die Kommunikation mit der Laufzeitbibliothek konfiguriert ist.

Wie können Sie Ihr Formular so konfigurieren, dass es kommuniziert? Wir haben bald einen Artikel, der alles im Detail erklärt. Bleiben Sie dran!
