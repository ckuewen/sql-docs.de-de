---
description: catalog.clear_object_parameter_value (SSISDB-Datenbank)
title: catalog.clear_object_parameter_value (SSISDB-Datenbank) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/04/2017
ms.prod: sql
ms.prod_service: integration-services
ms.reviewer: ''
ms.technology: integration-services
ms.topic: language-reference
ms.assetid: dcbbb714-a051-4805-9e2b-2c2fb647c890
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 16435fdd9ccb57b648f8073290ead5eca6ae393b
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88477172"
---
# <a name="catalogclear_object_parameter_value-ssisdb-database"></a>catalog.clear_object_parameter_value (SSISDB-Datenbank)

[!INCLUDE[sqlserver-ssis](../../includes/applies-to-version/sqlserver-ssis.md)]


[!INCLUDE [SQL Server](../../includes/applies-to-version/sqlserver.md)]

  Löscht den Wert eines Parameters für ein vorhandenes [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)]-Projekt oder -Paket, das auf dem Server gespeichert wird.  
  
## <a name="syntax"></a>Syntax  
  
```sql  
catalog.clear_object_parameter [ @folder_name = ] folder_name   
    , [ @project_name = ] project_name   
    , [ @object_type = ] object_type   
    , [ @object_name = ] object_name   
    , [ @parameter_ name = ] parameter_name  
```  
  
## <a name="arguments"></a>Argumente  
 [ \@folder_name = ] *folder_name*  
 Der Name des Ordners, der das Projekt enthält. Der *folder_name* ist **nvarchar(128)** .  
  
 [ \@project_name = ] *project_name*  
 Der Name des Projekts. Der *project_name* ist **nvarchar(128)** .  
  
 [ \@object_type = ] *object_type*  
 Der Objekttyp. Gültige Werte sind `20` für ein Projekt und `30` für ein Paket. Der *object_type* ist **smallInt**.  
  
 [ \@ object _name = ] *object _name*  
 Der Name des Pakets. Der *object _name* ist **nvarchar(260)**.  
  
 [ \@parameter_ name = ] *parameter_name*  
 Der Name des Parameters. Der *parameter_ name* ist **nvarchar(128)**.  
  
## <a name="return-code-value"></a>Rückgabecodewert  
 0 (Erfolg)  
  
## <a name="result-sets"></a>Resultsets  
 Keine  
  
## <a name="permissions"></a>Berechtigungen  
 Diese gespeicherte Prozedur erfordert eine der folgenden Berechtigungen:  
  
-   READ-Berechtigung und MODIFY-Berechtigung für das Projekt  
  
-   Mitgliedschaft in der Datenbankrolle **ssis_admin**  
  
-   Mitgliedschaft in der Serverrolle **sysadmin**  
  
## <a name="errors-and-warnings"></a>Fehler und Warnungen  
 In der folgenden Liste werden Bedingungen beschrieben, die möglicherweise bewirken, dass die gespeicherte clear_object_parameter-Prozedur einen Fehler auslöst:  
  
-   Es wurde ein ungültiger Objekttyp angegeben, oder der Objektname wurde nicht im Projekt gefunden.  
  
-   Das Projekt ist nicht vorhanden, auf das Projekt kann nicht zugegriffen werden, oder der Projektname ist ungültig.  
  
-   Es wurde ein ungültiger Parametername angegeben.  
  
-   Der Benutzer verfügt nicht über die entsprechenden Berechtigungen.  
  
  
