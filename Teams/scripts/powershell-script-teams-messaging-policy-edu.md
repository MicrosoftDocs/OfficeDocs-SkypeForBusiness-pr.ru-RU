---
title: Пример сценария PowerShell — создание и назначение политики обмена сообщениями
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
description: Используйте этот сценарий PowerShell для создания политики обмена сообщениями в группах и назначать пользователей в вашей организации.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d65deff9f424fad8fed11d7b10cbe40ced387161
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32205076"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Пример сценария PowerShell — создание и назначение политики обмена сообщениями
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


