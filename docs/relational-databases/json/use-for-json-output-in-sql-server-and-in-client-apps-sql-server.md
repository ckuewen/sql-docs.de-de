---
description: Verwenden der FOR JSON-Ausgabe in SQL Server und in Client-Apps (SQL Server)
title: Verwenden der FOR JSON-Ausgabe in SQL Server und in Client-Apps
ms.date: 06/03/2020
ms.prod: sql
ms.technology: ''
ms.topic: conceptual
helpviewer_keywords:
- FOR JSON, using in client apps
- FOR JSON, using in SQL Server
ms.assetid: 302e5397-b499-4ea3-9a7f-c24ccad698eb
author: jovanpop-msft
ms.author: jovanpop
ms.reviewer: jroth
ms.custom: seo-dt-2019
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions||>=sql-server-linux-2017||=azuresqldb-mi-current
ms.openlocfilehash: 9d3fdfb151acc9205693226a3c32869fba782a2d
ms.sourcegitcommit: 28fecbf61ae7b53405ca378e2f5f90badb1a296a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/04/2020
ms.locfileid: "96595082"
---
# <a name="use-for-json-output-in-sql-server-and-in-client-apps-sql-server"></a>Verwenden der FOR JSON-Ausgabe in SQL Server und in Client-Apps (SQL Server)
[!INCLUDE [SQL Server Azure SQL Database](../../includes/applies-to-version/sqlserver2016-asdb.md)]

Die folgenden Beispiele veranschaulichen einige Möglichkeiten, die **FOR JSON**-Klausel und ihre JSON-Ausgabe in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] oder Client-Apps zu verwenden.  
  
## <a name="use-for-json-output-in-sql-server-variables"></a>Verwenden der FOR JSON-Ausgabe in SQL Server-Variablen  
Die Ausgabe der FOR JSON-Klausel ist vom Typ NVARCHAR(MAX) und kann daher jeder Variablen zugewiesen werden, wie im folgenden Beispiel gezeigt.  
  
```sql  
DECLARE @x NVARCHAR(MAX) =
  (SELECT TOP 10 *
     FROM Sales.SalesOrderHeader
     FOR JSON AUTO)  
```  
  
## <a name="use-for-json-output-in-sql-server-user-defined-functions"></a>Verwenden der FOR JSON-Ausgabe in benutzerdefinierten SQL Server-Funktionen  
 Sie können benutzerdefinierte Funktionen erstellen, die Resultsets als JSON formatieren und diese JSON-Ausgabe zurückgeben. Im folgenden Beispiel wird eine benutzerdefinierte Funktion erstellt, die einige Auftragsdetailzeilen abruft und sie als JSON-Array formatiert.  
  
```sql  
CREATE FUNCTION GetSalesOrderDetails(@salesOrderId int)  
 RETURNS NVARCHAR(MAX)  
AS  
BEGIN  
   RETURN (SELECT UnitPrice, OrderQty  
           FROM Sales.SalesOrderDetail  
           WHERE SalesOrderID = @salesOrderId  
           FOR JSON AUTO)  
END
```  
  
 Sie können diese Funktion in einem Batch oder in einer Abfrage verwenden, wie im folgenden Beispiel gezeigt.  
  
```sql  
DECLARE @x NVARCHAR(MAX) = dbo.GetSalesOrderDetails(43659)

PRINT dbo.GetSalesOrderDetails(43659)

SELECT TOP 10
  H.*, dbo.GetSalesOrderDetails(H.SalesOrderId) AS Details
FROM Sales.SalesOrderHeader H
```  
  
## <a name="merge-parent-and-child-data-into-a-single-table"></a>Zusammenführen von übergeordneten und untergeordneten Daten in einer einzelnen Tabelle  
Im folgenden Beispiel wird jeder Satz von untergeordneten Zeilen als JSON-Array formatiert. Das JSON-Array wird der Wert der Spalte „Details“ in der übergeordneten Tabelle.  
  
```sql  
SELECT TOP 10 SalesOrderId, OrderDate,  
      (SELECT TOP 3 UnitPrice, OrderQty  
         FROM Sales.SalesOrderDetail D  
         WHERE H.SalesOrderId = D.SalesOrderID  
         FOR JSON AUTO) AS Details  
INTO SalesOrder  
FROM Sales.SalesOrderHeader H  
```  
  
## <a name="update-the-data-in-json-columns"></a>Aktualisieren der Daten in JSON-Spalten  
 Im folgenden Beispiel wird gezeigt, dass Sie den Wert einer Spalte aktualisieren können, die JSON-Text enthält.  
  
```sql  
UPDATE SalesOrder  
SET Details =  
     (SELECT TOP 1 UnitPrice, OrderQty  
       FROM Sales.SalesOrderDetail D  
       WHERE D.SalesOrderId = SalesOrder.SalesOrderId  
      FOR JSON AUTO) 
```  
  
## <a name="use-for-json-output-in-a-c-client-app"></a>Verwenden der FOR JSON-Ausgabe in einer C#-Client-App  
 Im folgenden Beispiel wird veranschaulicht, wie die JSON-Ausgabe einer Abfrage in ein StringBuilder-Objekt in einer C#-Client-App abgerufen wird. Angenommen, die Variable `queryWithForJson` enthält den Text einer SELECT-Anweisung mit einer FOR JSON-Klausel.  
  
```csharp  
var queryWithForJson = "SELECT ... FOR JSON";
var conn = new SqlConnection("<connection string>");
var cmd = new SqlCommand(queryWithForJson, conn);
conn.Open();
var jsonResult = new StringBuilder();
var reader = cmd.ExecuteReader();
if (!reader.HasRows)
{
    jsonResult.Append("[]");
}
else
{
    while (reader.Read())
    {
        jsonResult.Append(reader.GetValue(0).ToString());
    }
}
```  

## <a name="learn-more-about-json-in-sql-server-and-azure-sql-database"></a>Weitere Informationen zu JSON in SQL Server und Azure SQL-Datenbank  
  
### <a name="microsoft-videos"></a>Microsoft-Videos

Eine visuelle Einführung in die JSON-Unterstützung, die in SQL Server und Azure SQL-Datenbank integriert ist, finden Sie in den folgenden Videos:

-   [SQL Server 2016 and JSON Support](https://channel9.msdn.com/Shows/Data-Exposed/SQL-Server-2016-and-JSON-Support)

-   [Using JSON in SQL Server 2016 and Azure SQL Database](https://channel9.msdn.com/Shows/Data-Exposed/Using-JSON-in-SQL-Server-2016-and-Azure-SQL-Database)

-   [JSON as a bridge between NoSQL and relational worlds](https://channel9.msdn.com/events/DataDriven/SQLServer2016/JSON-as-a-bridge-betwen-NoSQL-and-relational-worlds)
 
## <a name="see-also"></a>Weitere Informationen  
 [Format Query Results as JSON with FOR JSON &#40;SQL Server&#41; (Formatieren von Abfrageergebnissen als JSON mit FOR JSON [SQL Server])](../../relational-databases/json/format-query-results-as-json-with-for-json-sql-server.md)  
  
  
