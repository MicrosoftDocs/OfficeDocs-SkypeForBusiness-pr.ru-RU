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
ms.openlocfilehash: 282a5442b6d4bf64771e741e75fab45bc87f6bd4
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/04/2018
ms.locfileid: "25371240"
---
<a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="e93ec-103">Пример сценария PowerShell — Создание и назначение политики обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="e93ec-103">PowerShell script sample - Create and assign a messaging policy</span></span>
-------------------------------------------------------------------------

<span data-ttu-id="e93ec-104">Используйте этот сценарий PowerShell для создания политики обмена сообщениями в группами Майкрософт и ее назначение пользователям.</span><span class="sxs-lookup"><span data-stu-id="e93ec-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="e93ec-105">Дополнительные сведения об использовании этого скрипта PowerShell [Quick start - команды для образовательных заведений](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)см.</span><span class="sxs-lookup"><span data-stu-id="e93ec-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="e93ec-106">Если вы новичок в PowerShell и вам требуется помощь, см. раздел [Общие сведения об Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span><span class="sxs-lookup"><span data-stu-id="e93ec-106">If you're new to PowerShell and need help getting started, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/overview?view=azurermps-5.1.1).</span></span>


## <a name="sample-script"></a><span data-ttu-id="e93ec-107">Пример сценария</span><span class="sxs-lookup"><span data-stu-id="e93ec-107">Sample script</span></span>

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


