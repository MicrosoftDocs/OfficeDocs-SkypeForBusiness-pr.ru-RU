---
title: 'Пример сценария PowerShell: создание политики & сообщений'
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Используйте этот сценарий PowerShell, чтобы создать политику обмена сообщениями в Teams и назначить ее пользователям в организации.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e3d1fa3ebe45785c088852c518ac5490263fa6aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804659"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a><span data-ttu-id="e85e7-103">Пример сценария PowerShell — создание и назначение политики обмена сообщениями</span><span class="sxs-lookup"><span data-stu-id="e85e7-103">PowerShell script sample - Create and assign a messaging policy</span></span>

<span data-ttu-id="e85e7-104">Используйте этот сценарий PowerShell, чтобы создать политику обмена сообщениями в Microsoft Teams и назначить ее пользователям.</span><span class="sxs-lookup"><span data-stu-id="e85e7-104">Use this PowerShell script to create a messaging policy in Microsoft Teams and assign it to users.</span></span> 

<span data-ttu-id="e85e7-105">Дополнительные сведения об использовании этого сценария PowerShell см. в кратком запуске [Teams для образования.](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu)</span><span class="sxs-lookup"><span data-stu-id="e85e7-105">For more information about using this PowerShell script, see [Quick start - Teams for Education](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).</span></span>

<span data-ttu-id="e85e7-106">Этот сценарий использует [командлет Grant-CsTeamsMessagingPolicy,](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) который находится в модуле PowerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="e85e7-106">This script uses the [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) cmdlet which is in the Skype for Business Online PowerShell module.</span></span> <span data-ttu-id="e85e7-107">Дополнительные сведения об управлении Teams с помощью [PowerShell](../teams-powershell-overview.md) см. в обзоре Teams PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e85e7-107">See [Teams PowerShell overview](../teams-powershell-overview.md) to learn more about managing Teams using PowerShell.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="e85e7-108">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="e85e7-108">Before you start</span></span>

<span data-ttu-id="e85e7-109">Скачайте и установите [модуль Skype для бизнеса Online PowerShell,](https://www.microsoft.com/download/details.aspx?id=39366)а затем перезагрузите компьютер, если будет предложено.</span><span class="sxs-lookup"><span data-stu-id="e85e7-109">Download and install the [Skype for Business Online PowerShell module](https://www.microsoft.com/download/details.aspx?id=39366), and then restart your computer if prompted.</span></span>

<span data-ttu-id="e85e7-110">Подробнее об управлении Skype для бизнеса [Online можно узнать с помощью Office 365 PowerShell.](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)</span><span class="sxs-lookup"><span data-stu-id="e85e7-110">To lean more, see [Manage Skype for Business Online with Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).</span></span>

## <a name="sample-script"></a><span data-ttu-id="e85e7-111">Пример сценария</span><span class="sxs-lookup"><span data-stu-id="e85e7-111">Sample script</span></span>

```powershell
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
```

> [!NOTE]
> <span data-ttu-id="e85e7-112">Кроме того, можно назначить политику обмена сообщениями непосредственно пользователям в масштабе с помощью пакетного назначения политики или группе, в которую они в являются.</span><span class="sxs-lookup"><span data-stu-id="e85e7-112">You can also assign a messaging policy directly to users at scale through a batch policy assignment or to a group that the users are members of.</span></span> <span data-ttu-id="e85e7-113">Дополнительные сведения [см.](../batch-group-policy-assignment-edu.md) в дополнительных сведениях о назначении политик большим наборам пользователей в учебном за учебных заведениях и о назначении политик [пользователям в Teams.](../assign-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e85e7-113">For more information see [Assign policies to large sets of users in your school](../batch-group-policy-assignment-edu.md) and [Assign policies to your users in Teams](../assign-policies.md).</span></span>
