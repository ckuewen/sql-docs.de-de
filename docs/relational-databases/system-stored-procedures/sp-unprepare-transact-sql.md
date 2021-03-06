---
description: sp_unprepare (Transact-SQL)
title: sp_unprepare (Transact-SQL) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql
ms.prod_service: database-engine, sql-data-warehouse, pdw
ms.reviewer: ''
ms.technology: system-objects
ms.topic: language-reference
f1_keywords:
- sp_cursor_unprepare_TSQL
- sp_cursor_unprepare
dev_langs:
- TSQL
helpviewer_keywords:
- sp_unprepare
ms.assetid: 14320251-c551-49d8-b933-057406114978
author: markingmyname
ms.author: maghan
monikerRange: '>=aps-pdw-2016||=azure-sqldw-latest||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current'
ms.openlocfilehash: 4e3b2d0aadc896e24991f457721d44128023fc8b
ms.sourcegitcommit: a5398f107599102af7c8cda815d8e5e9a367ce7e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "92006142"
---
# <a name="sp_unprepare-transact-sql"></a>sp_unprepare (Transact-SQL)
[!INCLUDE [sql-asdbmi-asa-pdw](../../includes/applies-to-version/sql-asdbmi-asa-pdw.md)]

  Verwirft den Ausführungsplan, der von der gespeicherten Prozedur sp_prepare erstellt wurde. sp_unprepare wird aufgerufen, indem ID = 15 in einem Tabular Data Stream-Paket (TDS) angegeben wird.  
  
## <a name="syntax"></a>Syntax  
  
```syntaxsql  
-- Syntax for SQL Server, Azure Synapse Analytics, Parallel Data Warehouse  
  
sp_unprepare handle           
```  
  
## <a name="arguments"></a>Argumente  
 *bewältigen*  
 Der von sp_prepare zurückgegebene *handle* -Wert.  
  
## <a name="examples"></a>Beispiele  
 Im folgenden Beispiel wird eine einfache Anweisung vorbereitet, ausgeführt und deren Vorbereitung wieder aufgehoben.  
  
```SQL  
DECLARE @P1 INT;  
EXEC sp_prepare @P1 OUTPUT,   
    N'@P1 NVARCHAR(128), @P2 NVARCHAR(100)',  
    N'SELECT database_id, name FROM sys.databases WHERE name = @P1 AND state_desc = @P2';  
EXEC sp_execute @P1, N'tempdb', N'ONLINE';  
EXEC sp_unprepare @P1;  
```  
  
## <a name="examples-sssdwfull-and-sspdw"></a>Beispiele: [!INCLUDE[ssSDWfull](../../includes/sssdwfull-md.md)] und [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
 Im folgenden Beispiel wird eine einfache Anweisung vorbereitet, ausgeführt und deren Vorbereitung wieder aufgehoben.  
  
```SQL  
DECLARE @P1 INT;  
EXEC sp_prepare @P1 OUTPUT,   
    N'@P1 NVARCHAR(128), @P2 NVARCHAR(100)',  
    N'SELECT database_id, name FROM sys.databases WHERE name = @P1 AND state_desc = @P2';  
EXEC sp_execute @P1, N'tempdb', N'ONLINE';  
EXEC sp_unprepare @P1;  
```  
  
## <a name="see-also"></a>Weitere Informationen  
 [sp_prepare &#40;Transact-SQL-&#41;](../../relational-databases/system-stored-procedures/sp-prepare-transact-sql.md)   

