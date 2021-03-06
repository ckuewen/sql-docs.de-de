---
title: Übersicht über SQL Server für Linux
description: In diesem Artikel wird beschrieben, wie SQL Server für Linux ausgeführt wird, und er enthält weitere Informationen, wie Sie mehr erfahren können.
author: VanMSFT
ms.author: vanto
ms.date: 11/04/2019
ms.topic: conceptual
ms.prod: sql
ms.technology: linux
ms.assetid: 9dcc6a90-0add-42c2-815b-862e4e2a21ac
ms.openlocfilehash: 3ecec5879e66f17426b9aa68014c2b2d0f751153
ms.sourcegitcommit: 22102f25db5ccca39aebf96bc861c92f2367c77a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "92115527"
---
# <a name="sql-server-on-linux"></a>SQL Server unter Linux

[!INCLUDE [SQL Server - Linux](../includes/applies-to-version/sql-linux.md)]

::: moniker range="= sql-server-2017 || = sqlallproducts-allversions"
Ab SQL Server 2017 wird SQL Server unter Linux ausgeführt. Dabei handelt es sich unabhängig von Ihrem Betriebssystem um dieselbe SQL Server-Datenbank-Engine mit vielen ähnlichen Features und Diensten.
::: moniker-end

::: moniker range=">= sql-server-ver15 || >= sql-server-linux-ver15"
SQL Server 2019 wird unter Linux ausgeführt. Dabei handelt es sich unabhängig von Ihrem Betriebssystem um dieselbe SQL Server-Datenbank-Engine mit vielen ähnlichen Features und Diensten. Weitere Informationen zu diesem Release finden Sie unter [Neues in SQL Server 2019 unter Linux](sql-server-linux-whats-new-2019.md).
::: moniker-end

::: moniker range="= sql-server-2017"
> [!TIP]
> [SQL Server 2019](sql-server-linux-overview.md?view=sql-server-ver15) ist verfügbar. Unter [Neues in SQL Server 2019 unter Linux](sql-server-linux-whats-new-2019.md?view=sql-server-ver15) erfahren Sie, was im aktuellen Release für Linux neu ist.
::: moniker-end

::: moniker range="= sql-server-linux-2017"
> [!TIP]
> [SQL Server 2019](sql-server-linux-overview.md?view=sql-server-linux-ver15) ist verfügbar. Unter [Neues in SQL Server 2019 unter Linux](sql-server-linux-whats-new-2019.md?view=sql-server-linux-ver15) erfahren Sie, was im aktuellen Release für Linux neu ist.
::: moniker-end

::: moniker range="= sqlallproducts-allversions"
> [!TIP]
> SQL Server 2019 ist verfügbar. Unter [Neues in SQL Server 2019 unter Linux](sql-server-linux-whats-new-2019.md) erfahren Sie, was im aktuellen Release für Linux neu ist.
::: moniker-end

## <a name="install"></a>Installieren

Installieren Sie zunächst SQL Server für Linux mithilfe einer der nachfolgenden Schnellstarts:

- [Installation unter Red Hat Enterprise Linux](quickstart-install-connect-red-hat.md)
- [Installation unter SUSE Linux Enterprise Server](quickstart-install-connect-suse.md)
- [Installation unter Ubuntu](quickstart-install-connect-ubuntu.md)
- [Ausführung in Docker](quickstart-install-connect-docker.md)
- [Provision a SQL VM in Azure (Bereitstellen einer SQL-VM in Azure)](/azure/virtual-machines/linux/sql/provision-sql-server-linux-virtual-machine?toc=/sql/toc/toc.json)

> [!NOTE]
> Docker selbst kann auf mehreren Plattformen ausgeführt werden. Dies bedeutet, dass Sie das Docker-Image unter Linux, Mac und Windows ausführen können.

## <a name="connect"></a>Verbinden

Stellen Sie nach der Installation eine Verbindung mit der SQL Server-Instanz auf Ihrem Linux-Computer her. Sie können eine lokale oder Remoteverbindung mit einer Vielzahl von Tools und Treibern herstellen. Die Schnellstarts veranschaulichen die Verwendung des [sqlcmd](sql-server-linux-setup-tools.md)-Befehlszeilentools. Zu anderen Tools gehören die folgenden:

| Tool | Lernprogramm |
|-----|-----|
| Visual Studio Code (VS Code) | [Verwenden von Visual Studio Code zum Erstellen und Ausführen von Transact-SQL-Skripts](../tools/visual-studio-code/sql-server-develop-use-vscode.md) |
| SQL Server Management Studio (SSMS) | [Verwenden von SQL Server Management Studio unter Windows zum Verwalten von SQL Server für Linux](sql-server-linux-manage-ssms.md) |
| SQL Server Data Tools (SSDT) | [Verwenden von Visual Studio zum Erstellen von Datenbanken für SQL Server für Linux](sql-server-linux-develop-use-ssdt.md) |

## <a name="explore"></a>Erkunden

<!--SQL Server 2017 on Linux-->
::: moniker range="= sql-server-linux-2017 || = sql-server-2017"

SQL Server 2017 verfügt auf allen unterstützten Plattformen, einschließlich Linux, über dieselbe zugrunde liegende Datenbank-Engine. Daher funktionieren viele vorhandene Features und Funktionen unter Linux auf dieselbe Weise. In diesem Bereich der Dokumentation werden einige dieser Features aus der Perspektive von Linux dargestellt. Außerdem werden Bereiche mit besonderen Anforderungen für Linux hervorgehoben.

Wenn Sie bereits mit SQL Server vertraut sind, lesen Sie die [Anmerkungen zu dieser Version](sql-server-linux-release-notes.md), um sich über allgemeine Richtlinien und bekannte Probleme zu informieren. Informieren Sie sich dann über die [Neuerungen für SQL Server für Linux](sql-server-linux-whats-new.md) sowie die [Neuerungen bei SQL Server 2017 insgesamt](../sql-server/what-s-new-in-sql-server-2017.md).

::: moniker-end
<!--SQL Server 2019 on Linux-->
::: moniker range=">= sql-server-linux-ver15 || >= sql-server-ver15"

[!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] verfügt auf allen unterstützten Plattformen, einschließlich Linux, über dieselbe zugrunde liegende Datenbank-Engine. Daher funktionieren viele vorhandene Features und Funktionen unter Linux auf dieselbe Weise. In diesem Bereich der Dokumentation werden einige dieser Features aus der Perspektive von Linux dargestellt. Außerdem werden Bereiche mit besonderen Anforderungen für Linux hervorgehoben.

Wenn Sie bereits mit SQL Server für Linux vertraut sind, lesen Sie die [Anmerkungen zu dieser Version](sql-server-linux-release-notes-2019.md), um sich über allgemeine Richtlinien und bekannte Probleme zu informieren. Finden Sie heraus, was es [Neues in SQL Server 2019 unter Linux](../sql-server/what-s-new-in-sql-server-ver15.md?view=sql-server-ver15) gibt.

::: moniker-end

<!--SQL Server All Versions-->
::: moniker range="=sqlallproducts-allversions"

SQL Server 2017 und [!INCLUDE[SQL Server 2019](../includes/sssqlv15-md.md)] verfügen auf allen unterstützten Plattformen, einschließlich Linux, über dieselbe zugrunde liegende Datenbank-Engine. Daher funktionieren viele vorhandene Features und Funktionen unter Linux auf dieselbe Weise. In diesem Bereich der Dokumentation werden einige dieser Features aus der Perspektive von Linux dargestellt. Außerdem werden Bereiche mit besonderen Anforderungen für Linux hervorgehoben.

Wenn Sie bereits mit SQL Server für Linux vertraut sind, lesen Sie die Anmerkungen zu dieser Version:

- [SQL Server 2017 release notes (Versionsanmerkungen zu SQL Server 2017)](sql-server-linux-release-notes.md)
- [Versionsanmerkungen zu SQL Server 2019](sql-server-linux-release-notes-2019.md)

Informieren Sie sich anschließend über die Neuerungen:

- [Neuerungen bei SQL Server 2017](sql-server-linux-whats-new.md)
- [Neues in SQL Server 2019 unter Linux](../sql-server/what-s-new-in-sql-server-ver15.md#sql-server-on-linux)

::: moniker-end

> [!TIP]
> Antworten auf häufig gestellte Fragen finden Sie unter [Häufig gestellte Fragen zu SQL Server für Linux](sql-server-linux-faq.md).

[!INCLUDE[Get Help Options](../includes/paragraph-content/get-help-options.md)]

[!INCLUDE[contribute-to-content](../includes/paragraph-content/contribute-to-content.md)]