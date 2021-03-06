---
title: Kusto-Erweiterung (KQL) für Azure Data Studio
description: In diesem Artikel wird beschrieben, wie Sie mithilfe von Azure Data Studio eine Verbindung zu Azure Data Explorer-Clustern herstellen und sie abfragen können.
ms.prod: azure-data-studio
ms.technology: azure-data-studio
ms.topic: conceptual
author: markingmyname
ms.author: maghan
ms.reviewer: jukoesma
ms.custom: ''
ms.date: 10/29/2020
ms.openlocfilehash: 0c77b957f14401aec3130fa5fa4f78f0d34de9b5
ms.sourcegitcommit: 894c1a23e922dc29b82c1d2c34c7b0ff28b38654
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "93067202"
---
# <a name="kusto-kql-extension-for-azure-data-studio-preview"></a>Kusto-Erweiterung (KQL) für Azure Data Studio (Vorschau)

Die Kusto-Erweiterung (KQL) für [Azure Data Studio](../what-is-azure-data-studio.md) ermöglicht es Ihnen, eine Verbindung zu [Azure Data Explorer](/azure/data-explorer/data-explorer-overview)-Clustern herzustellen und sie abzufragen.

Benutzer können KQL-Abfragen schreiben und ausführen und Notebooks mit dem [Kusto-Kernel](../notebooks/notebooks-kusto-kernel.md) vollständig mit IntelliSense erstellen.

Indem die native Kusto-Funktion (KQL) in Azure Data Studio aktiviert wird, können technische und wissenschaftliche Fachkräfte für Daten und Data Analysts schnell Trends und Anomalien für große in Azure Data Explorer gespeicherte Datenmengen erkennen.

Diese Erweiterung befindet sich zurzeit in der Vorschau.

## <a name="prerequisites"></a>Voraussetzungen

Wenn Sie über kein Azure-Abonnement verfügen, können Sie ein [kostenloses Azure-Konto](https://azure.microsoft.com/free/) erstellen, bevor Sie beginnen.

Die folgenden Voraussetzungen müssen ebenfalls erfüllt sein:

- [Azure Data Studio-Installation](../download-azure-data-studio.md).
- [Schnellstart: Erstellen eines Azure Data Explorer-Clusters und einer Datenbank](/azure/data-explorer/create-cluster-database-portal).

## <a name="install-the-kusto-kql-extension"></a>Installieren der Kusto-Erweiterung (KQL)

Führen Sie die folgenden Schritte aus, um die Kusto-Erweiterung (KQL) in Azure Data Studio zu installieren.

1. Öffnen Sie den Erweiterungs-Manager in Azure Data Studio. Dazu können Sie entweder auf das Erweiterungssymbol oder im Menü „Ansicht“ auf **Erweiterungen** klicken.

2. Geben Sie in der Suchleiste *Kusto* ein.

3. Wählen Sie die Erweiterung **Kusto** aus, und zeigen Sie die Details an.

4. Klicken Sie auf **Installieren**.

:::image type="content" source="media/kusto-extension/kusto-extension-icon.png" alt-text="Kusto-Erweiterung":::

## <a name="how-to-connect-to-an-azure-data-explorer-cluster"></a>Herstellen einer Verbindung zu einem Azure Data Explorer-Cluster

### <a name="find-your-azure-data-explorer-cluster"></a>Suchen nach Ihrem Azure Data Explorer-Cluster

Suchen Sie im [Azure-Portal](https://ms.portal.azure.com/#home) nach Ihrem Azure Data Explorer-Cluster und dann nach dem URI für den Cluster.

:::image type="content" source="media/kusto-extension/kusto-extension-adx-cluster-uri.png" alt-text="URI":::

Sie können jedoch auch sofort mit dem *help.kusto.windows.net* -Cluster loslegen.

Für diesen Artikel werden zu Beispielzwecken die Daten aus dem help.kusto.windows.net-Cluster verwendet.

### <a name="connection-details"></a>Verbindungsdetails

Befolgen Sie die folgenden Schritte, um einen Azure Data Explorer-Cluster einzurichten, zu dem Sie eine Verbindung herstellen können.

1. Klicken Sie im Bereich **Verbindungen** auf **Neue Verbindung**.

2. Geben Sie im Feld **Verbindungsdetails** die erforderlichen Informationen ein.
    1. Wählen Sie für **Verbindungstyp** die Option *Kusto* aus.
    2. Geben Sie unter **Cluster** Ihren Azure Data Explorer-Cluster ein.

        > [!Note]
        > Achten Sie darauf, beim Eingeben des Clusternamens das `https://`-Präfix oder ein nachstehendes `/`-Zeichen nicht mit einzugeben.

    3. Verwenden Sie als **Authentifizierungstyp** den Standardwert: *Azure Active Directory: universell mit MFA*.
    4. Geben Sie unter **Konto** Ihre Kontoinformationen an.
    5. Nutzen Sie für **Datenbank** die Option *Standard*.
    6. Nutzen Sie für **Servergruppe** die Option *Standard*.
        1. Sie können dieses Feld verwenden, um Ihre Server in einer bestimmten Gruppe zu organisieren.
    7. Lassen Sie das Feld **Name (optional)** leer.
        1. Sie können dieses Feld nutzen, um Ihrem Server einen Alias zuzuweisen.

    :::image type="content" source="media/kusto-extension/kusto-extension-connection-details.png" alt-text="Verbindungsdetails":::

## <a name="how-to-query-an-azure-data-explorer-database-in-azure-data-studio"></a>Abfragen einer Azure Data Explorer-Datenbank in Azure Data Studio

Nach Einrichtung einer Verbindung zu Ihrem Azure Data Explorer-Cluster können Sie Ihre Datenbanken mithilfe von Kusto (KQL) abfragen.

Zur Erstellung einer neuen Abfrageregisterkarte können Sie entweder auf **Datei > Neue Abfrage** klicken, die Tastenkombination *STRG + N* nutzen oder auf die Datenbank rechtsklicken und dann auf **Neue Abfrage** klicken.

Sobald eine neue Abfrageregisterkarte geöffnet ist, geben Sie Ihre Kusto-Abfrage ein.

Hier finden Sie einige KQL-Beispielabfragen:

```kusto
StormEvents
| limit 1000
```

```kusto
StormEvents
| where EventType == "Waterspout"
```

Weitere Informationen zum Schreiben von KQL-Abfragen finden Sie unter [Schreiben von Abfragen für Azure Data Explorer](/azure/data-explorer/write-queries#overview-of-the-query-language).

## <a name="view-extension-settings"></a>Anzeigen von Erweiterungseinstellungen

Führen Sie die folgenden Schritte aus, um die Einstellungen für die Kusto-Erweiterung zu ändern.

1. Öffnen Sie den Erweiterungs-Manager in Azure Data Studio. Dazu können Sie entweder auf das Erweiterungssymbol oder im Menü „Ansicht“ auf **Erweiterungen** klicken.

2. Suchen Sie nach der Erweiterung **Kusto (KQL)** .

3. Klicken Sie auf das Symbol **Verwalten**.

4. Klicken Sie auf das Symbol **Erweiterungseinstellungen**.

Die Erweiterungseinstellungen sehen wie folgt aus:

:::image type="content" source="media/kusto-extension/kusto-extension-settings.png" alt-text="Einstellungen für die Kusto-Erweiterung (KQL)":::

## <a name="sanddance-visualization"></a>SandDance-Visualisierung

Die [SandDance-Erweiterung](sanddance-extension.md) in Kombination mit der Kusto-Erweiterung (KQL) in Azure Data Studio bringt eine umfangreiche interaktive Visualisierung mit sich. Klicken Sie im Resultset der KQL-Abfrage auf die Schaltfläche **Schnellansicht** , um [SandDance](https://sanddance.js.org/) zu starten.

:::image type="content" source="media/kusto-extension/kusto-extension-sanddance-demo.gif" alt-text="SandDance-Visualisierung":::

## <a name="known-issues"></a>Bekannte Probleme

| Details | Problemumgehung |
|---------|------------|
| [In einem Kusto-Notebook wird der Änderungsvorgang für eine Datenbankverbindung für eine gespeicherte Aliasverbindung nach einem Fehler bei der Codezellenausführung unterbrochen.](https://github.com/microsoft/azuredatastudio/issues/12384) | Schließen Sie das Notebook, öffnen Sie es wieder, und stellen Sie dann eine Verbindung mit dem richtigen Cluster mit der Datenbank her. |
| [In einem Kusto-Notebook funktioniert das Ändern einer Datenbankverbindung für eine nicht gespeicherte Aliasverbindung nicht.](https://github.com/microsoft/azuredatastudio/issues/12843) |Erstellen Sie über das Verbindungs-Viewlet eine neue Verbindung, und speichern Sie sie mit einem Alias. Erstellen Sie dann ein neues Notebook, und stellen Sie eine Verbindung mit der neu gespeicherten Verbindung her. | 
| [In einem Kusto-Notebook werden beim Erstellen einer neuen ADX-Verbindung keine Einträge in der Dropdownliste für Datenbanken angezeigt.](https://github.com/microsoft/azuredatastudio/issues/12666) | Erstellen Sie über das Verbindungs-Viewlet eine neue Verbindung, und speichern Sie sie mit einem Alias. Erstellen Sie dann ein neues Notebook, und stellen Sie eine Verbindung mit der neu gespeicherten Verbindung her. |

Sie können eine [Featureanforderung](https://github.com/microsoft/azuredatastudio/issues/new?assignees=&labels=&template=feature_request.md&title=) senden, um Feedback für das Produktteam bereitzustellen.  
Sie können einen [Fehlerbericht](https://github.com/microsoft/azuredatastudio/issues/new?assignees=&labels=&template=bug_report.md&title=) senden, um Feedback für das Produktteam bereitzustellen.

## <a name="next-steps"></a>Nächste Schritte

- [Erstellen und Ausführen eines Kusto-Notebooks](../notebooks/notebooks-kusto-kernel.md)
- [Kqlmagic-Notebook in Azure Data Studio](../notebooks/notebooks-kqlmagic.md)
- [Cheat Sheet für die Übersetzung von SQL in Kusto](/azure/data-explorer/kusto/query/sqlcheatsheet)
- [Was ist der Azure-Daten-Explorer?](/azure/data-explorer/data-explorer-overview)
- [Verwenden von SandDance-Visualisierungen](https://sanddance.js.org/)
