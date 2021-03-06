---
description: DBCC PDW_SHOWEXECUTIONPLAN (Transact-SQL)
title: DBCC PDW_SHOWEXECUTIONPLAN (Transact-SQL)
ms.custom: ''
ms.date: 07/16/2017
ms.prod: sql
ms.technology: data-warehouse
ms.prod_service: sql-data-warehouse, pdw
ms.reviewer: ''
ms.topic: language-reference
dev_langs:
- TSQL
author: pmasl
ms.author: umajay
monikerRange: '>= aps-pdw-2016 || = azure-sqldw-latest || = sqlallproducts-allversions'
ms.openlocfilehash: 67eea4a666519ec5a9dd1dce7e1e33e3c8da4831
ms.sourcegitcommit: c7f40918dc3ecdb0ed2ef5c237a3996cb4cd268d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2020
ms.locfileid: "91722421"
---
# <a name="dbcc-pdw_showexecutionplan-transact-sql"></a>DBCC PDW_SHOWEXECUTIONPLAN (Transact-SQL)

[!INCLUDE[applies-to-version/asa-pdw](../../includes/applies-to-version/asa-pdw.md)]

Zeigt den [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Ausführungsplan für eine Abfrage an, die auf einem bestimmten [!INCLUDE[ssSDW](../../includes/sssdw-md.md)]- oder [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]-Computeknoten oder -Steuerknoten ausgeführt wird. Verwenden Sie diese Funktion zum Behandeln von Problemen mit der Abfrageleistung, während Abfragen auf Compute- oder Steuerknoten ausgeführt werden.
  
Sobald Sie verstanden haben, wodurch Leistungsprobleme bei Abfragen für SMP-[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Abfragen auf den Computeknoten entstehen, können Sie diese Probleme auf verschiedene Weisen verbessern. Beispielsweise können Sie die Abfrageleistung auf Computeknoten verbessern, indem Sie Statistiken mit mehreren Spalten oder nicht gruppierte Indizes erstellen bzw. Abfragehinweise verwenden.
  
![Symbol für Themenlink](../../database-engine/configure-windows/media/topic-link.gif "Symbol für Themenlink") [Transact-SQL-Syntaxkonventionen &#40;Transact-SQL&#41;](../../t-sql/language-elements/transact-sql-syntax-conventions-transact-sql.md)
  
## <a name="syntax"></a>Syntax  
Syntax für [!INCLUDE[ssSDW](../../includes/sssdwfull-md.md)]:

```syntaxsql
DBCC PDW_SHOWEXECUTIONPLAN ( distribution_id, spid )  
[ ; ]  
```  

Syntax für [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]:
  
```syntaxsql
DBCC PDW_SHOWEXECUTIONPLAN ( pdw_node_id, spid )  
[ ; ]  
```  

[!INCLUDE[synapse-analytics-od-unsupported-syntax](../../includes/synapse-analytics-od-unsupported-syntax.md)]

## <a name="arguments"></a>Argumente  
 *distribution_id*  
 Bezeichner für die Verteilung, die den Abfrageplan ausführt. Dabei handelt es sich um einen Integer, der nicht NULL sein kann. Der Wert muss zwischen 1 und 60 liegen. Dieser Bezeichner wird verwendet, wenn für [!INCLUDE[ssSDW](../../includes/sssdw-md.md)] entwickelt wird.  
  
 *pdw_node_id*  
 Bezeichner für den Knoten, der den Abfrageplan ausführt. Dabei handelt es sich um einen Integer, der nicht NULL sein kann. Wird verwendet, wenn eine Anwendung entwickelt wird.  
  
 *spid*  
 Bezeichner für die [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]-Sitzung, die den Abfrageplan ausführt. Dabei handelt es sich um einen Integer, der nicht NULL sein kann.  
  
## <a name="permissions"></a>Berechtigungen  
 Erfordert die CONTROL-Berechtigung auf [!INCLUDE[ssSDW](../../includes/sssdw-md.md)].  
  
Erfordert die VIEW-SERVER-STATE-Berechtigung auf die Anwendung.
  
## <a name="examples-sssdw"></a>Beispiele: [!INCLUDE[ssSDW](../../includes/sssdw-md.md)]  
  
### <a name="a-dbcc-pdw_showexecutionplan-basic-syntax"></a>A. Grundlegende DBCC-PDW_SHOWEXECUTIONPLAN-Syntax  
 Wenn Sie die obenstehende Abfrage auf einer [!INCLUDE[ssSDW](../../includes/sssdw-md.md)]-Instanz ausführen, müssen Sie diese verändern, um auch distribution_id auszuwählen.  
  
```sql
SELECT [sql_spid], [pdw_node_id], [request_id], [dms_step_index], [type], [start_time], [end_time], [status], [distribution_id]  
FROM sys.dm_pdw_dms_workers   
WHERE [status] <> 'StepComplete' and [status] <> 'StepError'  
order by request_id, [dms_step_index];  
```  
  
Dadurch wird für jede aktiv ausgeführte Verteilung eine SPID zurückgegeben. Wenn Sie gerne wissen möchten, was Verteilung 1 in Sitzung 375 ausgeführt hat, können Sie den folgenden Befehl ausführen.
  
```sql
DBCC PDW_SHOWEXECUTIONPLAN ( 1, 375 );  
```  

## <a name="examples-sspdw"></a>Beispiele: [!INCLUDE[ssPDW](../../includes/sspdw-md.md)]  
### <a name="b-dbcc-pdw_showexecutionplan-basic-syntax"></a>B. Grundlegende DBCC-PDW_SHOWEXECUTIONPLAN-Syntax  
 Die Abfrage, die zu lange ausgeführt wird, führt entweder einen Vorgang für einen DMS-Abfrageplan oder für einen SQL-Abfrageplan aus.  
  
Wenn die Abfrage einen Vorgang für einen DMS-Abfrageplan ausführt. können Sie die folgende Abfrage verwenden, um eine Liste der Knoten- und Sitzungs-IDs für noch nicht abgeschlossene Schritte abzufragen.
  
```sql
SELECT [sql_spid], [pdw_node_id], [request_id], [dms_step_index], [type], [start_time], [end_time], [status]   
FROM sys.dm_pdw_dms_workers   
WHERE [status] <> 'StepComplete' and [status] <> 'StepError'  
AND pdw_node_id = 201001   
ORDER BY request_id, [dms_step_index], [distribution_id];  
```  
  
Verwenden Sie anhand des Ergebnisses der vorherigen Abfrage sql_spid und pdw_node_id als Parameter für DBCC PDW_SHOWEXECUTIONPLAN. Beispielsweise zeigt das folgende Beispiel den Ausführungsplan für pdw_node_id 201001 und sql_spid 375.
  
```sql
DBCC PDW_SHOWEXECUTIONPLAN ( 201001, 375 );  
```  

## <a name="see-also"></a>Weitere Informationen

- [DBCC PDW_SHOWPARTITIONSTATS &#40;Transact-SQL&#41;](dbcc-pdw-showpartitionstats-transact-sql.md)  
- [DBCC PDW_SHOWSPACEUSED &#40;Transact-SQL&#41;](dbcc-pdw-showspaceused-transact-sql.md)
