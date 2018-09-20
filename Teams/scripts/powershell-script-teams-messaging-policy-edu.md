---
title: Пример сценария PowerShell — Создание и назначение политики обмена сообщениями
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
description: Используйте этот сценарий PowerShell для создания политики обмена сообщениями в группах и назначать пользователей в вашей организации.
localization_priority: Normal
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 108272636925daadfb361c1e79ff14b9c04f514a
ms.sourcegitcommit: ab4476127222d9f0aa9ee503132ff9bdabcaf9bc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "24021860"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Пример сценария PowerShell — Создание и назначение политики обмена сообщениями
-------------------------------------------------------------------------

Используйте этот сценарий PowerShell для создания политики обмена сообщениями в группами Майкрософт и ее назначение пользователям. 

Дополнительные сведения об использовании этого скрипта PowerShell [Quick start - команды для образовательных заведений](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)см.

Если вы новичок в PowerShell и вам требуется помощь, см. раздел [Общие сведения об Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).


## <a name="sample-script"></a>Пример сценария

````powershell
<#
.SYNOPSIS
This script creates a messaging policy in Teams and assigns it to users.
.DESCRIPTION
Use this script to create a messaging policy and assign it to users in your organization.
#>

$dataSetFilePath = "<csv file with user ids for newly provisioned students> "
 $dataSet = Import-Csv "$($dataSetFilePath)" -Header UserId –delimiter ","
 foreach($line in $dataSet)
 {
    $userId = $line.UserId
    Write-Host $userId
    Grant-CsTeamsMessagingPolicy -PolicyName "<<PolicyName for a policy created with Chat Off>>" -Identity $userId
   
 }

````


