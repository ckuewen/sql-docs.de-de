---
description: Überprüfungen auf allgemeine Fehler
title: Allgemeine Fehlerüberprüfungen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 01/19/2017
ms.prod: sql
ms.prod_service: connectivity
ms.reviewer: ''
ms.technology: connectivity
ms.topic: conceptual
helpviewer_keywords:
- diagnostic information [ODBC], driver manager error checking
- general error checks [ODBC]
- driver manager [ODBC], error checking
ms.assetid: 0c9a3425-0a7c-48de-9ff6-73601c26283e
author: David-Engel
ms.author: v-daenge
ms.openlocfilehash: 014959769eb9b419595f122d099efbdc8fa7c1fd
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88465772"
---
# <a name="general-error-checks"></a>Überprüfungen auf allgemeine Fehler
Der Treiber-Manager überprüft einen allgemeinen Fehler. Es wird immer SQL_ERROR zurückgegeben, wenn der folgende Fehler auftritt: die Funktion muss vom Treiber unterstützt werden.
