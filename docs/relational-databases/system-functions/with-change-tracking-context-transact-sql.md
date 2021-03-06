---
description: WITH CHANGE_TRACKING_CONTEXT (Transact-SQL)
title: WITH CHANGE_TRACKING_CONTEXT (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 08/08/2016
ms.prod: sql
ms.prod_service: database-engine, sql-database
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- WITH_CHANGE_TRACKING_CONTEXT_TSQL
- WITH CHANGE_TRACKING_CONTEXT
dev_langs:
- TSQL
helpviewer_keywords:
- WITH CHANGE_TRACKING_CONTEXT
- change tracking [SQL Server], WITH CHANGE_TRACKING_CONTEXT
ms.assetid: 885e33a1-602a-4b94-8380-a63ac935a683
author: rothja
ms.author: jroth
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 850a20210b503cb3e6c05ab4c1ff69ee178cbbd7
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88464748"
---
# <a name="with-change_tracking_context-transact-sql"></a>WITH CHANGE_TRACKING_CONTEXT (Transact-SQL)
[!INCLUDE [SQL Server SQL Database](../../includes/applies-to-version/sql-asdb.md)]

  Aktiviert den zu spezifizierenden Änderungskontext, z. B. eine Absender-ID, wenn Daten geändert werden. Bei Verwendung der Änderungsnachverfolgung soll eine Anwendung möglicherweise zwischen Änderungen unterschieden, die von der Anwendung selbst vorgenommen wurden, und Änderungen, die außerhalb der Anwendung an den Daten vorgenommen wurden.  

 ![Symbol für Themenlink](../../database-engine/configure-windows/media/topic-link.gif "Symbol für Themenlink") [Transact-SQL-Syntaxkonventionen](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)  
  
## <a name="syntax"></a>Syntax  
  
```  
  
WITH CHANGE_TRACKING_CONTEXT ( context )  
```  
  
#### <a name="parameters"></a>Parameter  
 *context*  
 Die Kontextinformationen, die von der aufrufenden Anwendung angegeben werden und mit den Änderungsnachverfolgungsinformationen für die Änderung gespeichert werden. der *Kontext* ist " **varbinary (128)**".  
  
 Der Wert kann eine Konstante oder eine Variable sein, jedoch nicht NULL.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird der Änderungsnachverfolgungskontext für eine Datenänderung festgelegt.  
  
```  
WITH CHANGE_TRACKING_CONTEXT ( context )  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [Änderungsnachverfolgungsfunktionen &#40;Transact-SQL&#41;](../../relational-databases/system-functions/change-tracking-functions-transact-sql.md)   
 [CHANGETABLE &#40;Transact-SQL-&#41;](../../relational-databases/system-functions/changetable-transact-sql.md)   
 [Nachverfolgen von Datenänderungen &#40;SQL Server&#41;](../../relational-databases/track-changes/track-data-changes-sql-server.md)  
  
  
