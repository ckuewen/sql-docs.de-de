---
title: Einstellungen der SharePoint-Website für den Berichts-Viewer-Webpart (SSRS) | Microsoft-Dokumentation
description: Hier erfahren Sie, wie Sie die Einstellungen für eine SharePoint-Website im Webpart für den Berichts-Viewer im SQL Server-Berichtsserver konfigurieren.
ms.date: 11/15/2018
ms.prod: reporting-services
ms.prod_service: reporting-services-native
ms.technology: report-server-sharepoint
ms.topic: conceptual
author: jt000
ms.author: jasontre
ms.openlocfilehash: 8673f824762a9c7f6a28cd1232e742aac4428b23
ms.sourcegitcommit: 66a0672e47415dbd5cfd8d19075102c8c3973e70
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2020
ms.locfileid: "83764934"
---
# <a name="sharepoint-site-settings-for-the-report-viewer-web-part---reporting-services"></a>Einstellungen der SharePoint-Website für den Berichts-Viewer-Webpart – Reporting Services

[!INCLUDE[ssrs-appliesto](../../includes/ssrs-appliesto.md)] [!INCLUDE[ssrs-appliesto-2016-and-later](../../includes/ssrs-appliesto-2016-and-later.md)]  [!INCLUDE[ssrs-appliesto-pbirsi](../../includes/ssrs-appliesto-pbirs.md)] [!INCLUDE[ssrs-appliesto-sharepoint-2013-and-later](../../includes/ssrs-appliesto-sharepoint-2013-and-later.md)] [!INCLUDE[ssrs-appliesto-not-sharepoint-online](../../includes/ssrs-appliesto-not-sharepoint-online.md)]

Der Berichts-Viewer-Webpart weist einige Einstellungen auf, die konfiguriert werden können. Diese Einstellungen können auf der SharePoint-Websiteeinstellungenseite durch einen Websiteadministrator aktiviert und deaktiviert werden. Jede Website weist eigene Einstellungen auf. Darüber hinaus werden diese Einstellungen nach der Neuinstallation des Berichts-Viewer-Webparts nicht zurückgesetzt.

## <a name="accessing-the-site-settings-page"></a>Zugreifen auf die Websiteeinstellungenseite

So können Sie auf die Websiteeinstellungen zugreifen:

1. Klicken Sie auf Ihrer SharePoint-Website auf das **Zahnradsymbol** in der oberen linken Ecke und anschließend auf **Site Settings** (Websiteeinstellungen).

    ![Websiteeinstellungen über das Zahnradsymbol.](media/sharepoint-site-settings.png)

2. Klicken auf **Einstellungen für Berichts-Viewer-Webpart** in der Websiteeinstellungengruppe **Reporting Services**.

    > [!NOTE]
    > Die Websiteeinstellungen können Sie auch durch direktes Navigieren zu `<site>/_layouts/15/ReportViewerWebPart/ReportViewerWebPartSettings.aspx` erreichen.

## <a name="report-viewer-web-part-settings"></a>Berichts-Viewer-Webparteinstellungen

|Einstellung|Kommentare|  
|-------------|--------------|  
|Nutzungsdaten sammeln|Ermöglicht das Senden von Fehler- und Nutzungsinformationen an Microsoft, um eine Verbesserung der Produkte zu ermöglichen. Die Microsoft-Richtlinie für die Fehlerbericht-Datensammlung finden Sie in den [Microsoft SQL Server-Datenschutzbestimmungen](https://go.microsoft.com/fwlink/?LinkID=868444).|  
|Barrierefreiheit-Metadaten für Berichte aktivieren|Legt die [`AccessibleTablix`-Geräteinfo](../html-device-information-settings.md) für gerenderte Berichte fest.| 
