---
description: Alle Abonnements überprüfen
title: Alle Abonnements überprüfen | Microsoft-Dokumentation
ms.custom: ''
ms.date: 03/01/2017
ms.prod: sql
ms.prod_service: database-engine
ms.reviewer: ''
ms.technology: replication
ms.topic: conceptual
f1_keywords:
- sql13.rep.validate.allsubscriptions.f1
helpviewer_keywords:
- Validate All Subscriptions dialog box
ms.assetid: 32e31469-36e4-42d9-a57a-12388bfd229d
author: MashaMSFT
ms.author: mathoma
monikerRange: =azuresqldb-current||>=sql-server-2016||=sqlallproducts-allversions
ms.openlocfilehash: f2302499c6ea6a17e165f647823b3dfb6a48895f
ms.sourcegitcommit: e700497f962e4c2274df16d9e651059b42ff1a10
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "88455543"
---
# <a name="validate-all-subscriptions"></a>Alle Abonnements überprüfen
[!INCLUDE[sql-asdb](../../includes/applies-to-version/sql-asdb.md)]
  Im Dialogfeld **Alle Abonnements überprüfen** können Sie angeben, dass alle Abonnements für eine Mergeveröffentlichung überprüft werden sollen, sobald der Merge-Agent für die einzelnen Abonnements das nächste Mal ausgeführt wird. Die Ergebnisse der Überprüfung werden im Replikationsmonitor angezeigt. Weitere Informationen finden Sie unter [Validate Data at the Subscriber](../../relational-databases/replication/validate-data-at-the-subscriber.md).  
  
 Wenn Sie in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] mit der rechten Maustaste auf ein Abonnement klicken und dann auf **Abonnement überprüfen**klicken, können Sie auch ein einzelnes Abonnement überprüfen.  
  
## <a name="options"></a>Optionen  
 **Nur Zeilenanzahl überprüfen**  
 Wählen Sie diese Option aus, um zu überprüfen, ob die Anzahl der Zeilen in der Tabelle auf dem Abonnenten mit der Anzahl der Zeilen in der Tabelle auf dem Verleger übereinstimmt. Mit dieser Methode wird nicht überprüft, ob die Inhalte der Zeilen übereinstimmen. Die Überprüfung der Zeilenanzahl bietet einen Überprüfungsansatz, der kaum Ressourcen beansprucht und Sie Probleme bei den Daten erkennen lässt.  
  
 **Die Zeilenanzahl überprüfen und Prüfsummen vergleichen, um die Zeilendaten zu überprüfen**  
 Zusätzlich zum Einbinden einer Reihe von Zeilen auf Verleger- und Abonnentenebene wird eine Prüfsumme aller Daten mit dem binären Prüfsummenalgorithmus berechnet. Ist die Zeilenanzahl fehlerhaft, wird die Berechnung der Prüfsumme nicht ausgeführt. Diese Option gilt nicht für [!INCLUDE[ssEW](../../includes/ssew-md.md)].  
  
## <a name="see-also"></a>Siehe auch  
 [Überprüfen von replizierten Daten](../../relational-databases/replication/validate-data-at-the-subscriber.md)  
  
  
