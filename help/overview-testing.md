---
title: Adaptive Headless-Formulare von AEM – Übersicht
description: Adaptive Headless-Formulare von AEM bieten eine schnelle und effiziente Möglichkeit zum Erstellen von Formularen für verschiedene Plattformen, einschließlich Headless- oder Headful-CMS, React-Anwendungen, Einzelseitenanwendungen (SPA), Web Apps, Mobile Apps, Amazon Alexa, Google Assistant, WhatsApp und mehr. Mit adaptiven Headless-Formularen können Sie den Prozess zum Erstellen von Formularen optimieren und so die Erfassung von Benutzerdaten auf verschiedenen Geräten und Plattformen zu vereinfachen.
solution: Experience Manager Forms
feature: Adaptive Forms
topic: Headless
role: Admin, Developer
level: Beginner, Intermediate
keywords: Headless-CMS, adaptive Formulare, Headless-Benutzeroberfläche, Headful-CMS, Sprachassistenten, Alexa, Chatbots, WhatsApp-Architektur
hide: true
hidefromtoc: true
source-git-commit: 78ae6bc3e390d6a8e46d10d3ad3580c4268bf4ed
workflow-type: tm+mt
source-wordcount: '403'
ht-degree: 92%

---

# Einführung

Die adaptiven Headless-Formulare von Adobe Experience Manager (AEM) bilden eine Lösung zum Erstellen und Verwalten von Headless-Web-Formularen auf der Adobe Experience Manager-Plattform. Diese Funktion ermöglicht es Organisationen, interaktive Formulare zu erstellen, zu veröffentlichen und zu verwalten, bei denen Zugriffe und Interaktionen statt über eine herkömmliche grafische Benutzeroberfläche über APIs erfolgen. Adaptive Headless-Formulare von AEM ermöglichen eine größere Flexibilität und Skalierbarkeit bei der Formularentwicklung und -bereitstellung sowie ein verbessertes Kundenerlebnis durch die Möglichkeit, Formular-Design und -funktionalität an spezifische Anforderungen anzupassen. Durch die Nutzung der Funktionen von AEM und Headless-Technologie bietet diese Lösung eine robuste Plattform für die Erstellung, Verwaltung und Bereitstellung von Web-Formularen für verschiedene Nutzungsszenarien und Anwendungen.

![Erstellen und natives Rendern eines Formulars auf einer Website, in einer Anwendung oder in nicht visuellen Interaktionen](/help/assets/headless-forms-for-any-device.jpeg)

Adaptive Headless-Formulare unterstützen Sie bei Folgendem:

* Erstellen hochwertiger Mehrkanal-Formulare in der gewünschten Programmiersprache
* Native Integration von Formularen in Ihre Desktop- und Mobile Apps, Websites und Chat-Anwendungen
* Wiederverwenden Ihrer proprietären UI-Komponenten mit Formularanwendungen
* Nutzung der [Leistungsfähigkeit von Adobe Experience Manager Forms](https://experienceleague.adobe.com/docs/experience-manager-65/forms/getting-started/introduction-aem-forms.html?lang=de)

Darüber hinaus können Sie eigene Komponenten entwickeln, um ein Formular mit einem beliebigen UI-Framework und einer beliebigen Programmiersprache wiederzugeben. Sie können auch vordefinierte React-Komponenten verwenden, um ein adaptives Headless-Formular zu rendern.

## Wichtigste Funktionen

<!-- 

<table style="width:100%;">
  <tr>
    <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px;">
        <img src="/help/assets/01-overview-responsive-forms.jpeg" alt="Card Image 1" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Responsive Forms</h2>
          <p>The adaptive form feature enables you to create a single source for a form that automatically sizes and re-flows on mobile devices.</p>
        </div>
      </div>
    </td>
    <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px; ">
        <img src="/help/assets/01-overview-responsive-forms.jpeg" alt="Card Image 1" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Communication API</h2>
          <p>The adaptive form feature enables you to create a single source for a form that automatically sizes and re-flows on mobile devices.</p>
        </div>
      </div>
    </td>
    <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px; ">
        <img src="/help/assets/02-overview-backend-systems.jpeg" alt="Card Image 2" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Business Process Management</h2>
          <p>Integrate RDBMS, OData, Or Microsoft SOAP services, as well as protocols like Swagger 2.0 to connect to just about anything.</p>
        </div>
      </div>
    </td>
  </tr>
  <tr>
    <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px; ">
        <img src="/help/assets/03-overview-save-and-resume.jpeg" alt="Card Image 3" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Save and resume forms</h2>
          <p>Allow clients to save in-progress forms and return later to complete them, even on another device.</p>
        </div>
      </div>
    </td>
    <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px; ">
        <img src="/help/assets/04-overview-search.jpeg" alt="Card Image 1" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Forms Search and Discovery</h2>
          <p>Let customers easily find relevant forms based on a simple search query, tags, filters, and even geolocation — on any device through a personalized portal, with or without authentication.
          </p>
        </div>
      </div>
    </td>
      <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px; ">
        <img src="/help/assets/04-overview-search.jpeg" alt="Card Image 1" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Forms Search and Discovery</h2>
          <p>Let customers easily find relevant forms based on a simple search query, tags, filters, and even geolocation — on any device through a personalized portal, with or without authentication.
          </p>
        </div>
      </div>
    </td>
  </tr>
  <tr>
    <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px; ">
        <img src="/help/assets/05-overview-analytics.jpeg" alt="Card Image 2" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Form analytics and reporting</h2>
          <p>Out-of-the-box, customizable dashboards make it easy to apply analytics to forms to gain insight for actionable areas of improvement.</p>
        </div>
      </div>
    </td>
    <td style="width:33.33%;">
      <div style="width: 250px; border: 1px solid #ccc; border-radius: 8px; ">
        <img src="/help/assets/06-overview-business-process.jpeg" alt="Card Image 3" style="width:33.33; height: auto;">
        <div style="padding: 20px;">
          <h2 style="margin-top: 0;">Business Process Management</h2>
          <p>Route application submissions through customized workflows and a centralized dashboard for review, approval, and digital signatures by back-office employees — even when employees are on the go on a mobile device.
          </p>
        </div>
      </div>
    </td>
  </tr>
</table>

-->


<div style="display: flex; flex-wrap: wrap; justify-content: space-between; margin: 20px;">
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/01-overview-responsive-forms.jpeg" alt="Symbol 1" style="width: 50px; height: 50px;">
        <h2 style="margin-top: 10px;">Überschrift 1</h2>
        <p>Beschreibung 1</p>
    </div>
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/02-overview-backend-systems.jpeg" alt="Symbol 2" style="width: 50px; height: 50px;">
        <h2 style="margin-top: 10px;">Überschrift 2</h2>
        <p>Beschreibung 2</p>
    </div>
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/03-overview-save-and-resume.jpeg" alt="Symbol 3" style="width: 50px; height: 50px;">
        <h2 style="margin-top: 10px;">Überschrift 3</h2>
        <p>Beschreibung 3</p>
    </div>
        <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/04-overview-search.jpeg" alt="Symbol 1" style="width: 50px; height: 50px;">
        <h2 style="margin-top: 10px;">Überschrift 1</h2>
        <p>Beschreibung 1</p>
    </div>
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/05-overview-analytics.jpeg" alt="Symbol 2" style="width: 50px; height: 50px;">
        <h2 style="margin-top: 10px;">Überschrift 2</h2>
        <p>Beschreibung 2</p>
    </div>
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/06-overview-business-process.jpeg" alt="Symbol 3" style="width: 50px; height: 50px;">
        <h2 style="margin-top: 10px;">Überschrift 3</h2>
        <p>Beschreibung 3</p>
    </div>
    <!-- Add more cards as needed -->
</div>




<div style="display: flex; flex-wrap: wrap; justify-content: space-between; margin: 20px;">
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/01-overview-responsive-forms.jpeg" alt="Bild 1" style="width: 100%; border-radius: 5px;">
        <h2 style="margin-top: 10px;">Überschrift 1</h2>
        <p>Beschreibung 1</p>
    </div>
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/02-overview-backend-systems.jpeg" alt="Bild 2" style="width: 100%; border-radius: 5px;">
        <h2 style="margin-top: 10px;">Überschrift 2</h2>
        <p>Beschreibung 2</p>
    </div>
    <div style="width: 30%; margin-bottom: 20px; border: 1px solid #ccc; border-radius: 5px; padding: 20px; box-sizing: border-box;">
        <img src="/help/assets/03-overview-save-and-resume.jpeg" alt="Bild 3" style="width: 100%; border-radius: 5px;">
        <h2 style="margin-top: 10px;">Überschrift 3</h2>
        <p>Beschreibung 3</p>
    </div>
    <!-- Add more cards as needed -->
</div>



## Wer kann adaptive Headless-Formulare verwenden? {#who-can-use-headless-adaptive-forms}

Alle Frontend-Entwicklerinnen und -Entwickler, die mit modernen JavaScript-Frameworks vertraut sind, können adaptive Headless-Formulare verwenden. Entwicklungspersonen können ihr bestehendes Know-how in Frontend-Sprachen wie React nutzen, um schöne Datenerfassungserlebnisse auf Unternehmensebene zu schaffen.

Es sind keine Vorkenntnisse von Adobe Experience Manager nötig, um adaptive Headless-Formulare zu entwickeln.

<!-- 
## How to join the early adopter program? {#how-to-join-early-adopter-forms}

The service is available for AEM Forms as a Cloud Service and AEM 6.5.16.0 Forms or later On-Premise term customers and Adobe-Managed Service enterprise customers. Send an email to [headlessadaptiveforms@adobe.com](mailto:headlessadaptiveforms@adobe.com) from your official email ID to join the early adopter program. 

-->