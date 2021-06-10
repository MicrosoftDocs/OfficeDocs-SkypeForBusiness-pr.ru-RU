---
title: 'Пример сценария PowerShell: создание политики & сообщений'
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Используйте этот сценарий PowerShell для создания политики обмена сообщениями в Teams и назначения ее пользователям в организации.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: c665b96c0c44c2ea763c343bb2857d4c2b9dbb26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117277"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Пример сценария PowerShell — создание и назначение политики обмена сообщениями

Используйте этот сценарий PowerShell, чтобы создать политику обмена сообщениями в Microsoft Teams назначить ее пользователям. 

Дополнительные сведения об использовании этого сценария PowerShell см. в кратком Teams [для образования.](../teams-quick-start-edu.yml)

Этот сценарий использует [командлет Grant-CsTeamsMessagingPolicy,](/powershell/module/skype/grant-csteamsmessagingpolicy) который находится в модуле Skype для бизнеса Online PowerShell. Дополнительные [Teams powerShell](../teams-powershell-overview.md) см. в Teams PowerShell.


## <a name="before-you-start"></a>Перед началом работы

Скачайте и установите [модуль Skype для бизнеса Online PowerShell](https://www.microsoft.com/download/details.aspx?id=39366), а затем перезагрузите компьютер, если будет предложено.

Подробнее об этом можно узнать в [Skype для бизнеса Online с помощью Office 365 PowerShell.](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell)

## <a name="sample-script"></a>Пример сценария

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
> Вы также можете назначить политику обмена сообщениями непосредственно пользователям в масштабе с помощью назначения пакетной политики или группе, участниками которую они являются. Дополнительные сведения [см.](../batch-group-policy-assignment-edu.md) в [Teams.](../assign-policies.md)