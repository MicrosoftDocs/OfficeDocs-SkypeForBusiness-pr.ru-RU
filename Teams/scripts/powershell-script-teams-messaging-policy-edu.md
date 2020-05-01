---
title: Пример сценария PowerShell — создание политики обмена сообщениями & назначение
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Используйте этот сценарий PowerShell для создания политики обмена сообщениями в Teams и назначения ее пользователям в своей организации.
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 748167dc8e03b53fc07611df0ff464d984fb5678
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951064"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Пример сценария PowerShell — создание и назначение политики обмена сообщениями

Используйте этот сценарий PowerShell для создания политики обмена сообщениями в Microsoft Teams и назначения ее пользователям. 

Дополнительные сведения об использовании этого сценария PowerShell можно найти в [кратком разделе Начало — группы для образовательных учреждений](https://docs.microsoft.com/microsoftteams/teams-quick-start-edu).

Этот сценарий использует командлет [Grant-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmessagingpolicy) , который входит в модуль PowerShell Skype для бизнеса Online. Дополнительные сведения об управлении группами с помощью PowerShell см. в разделе [Общие сведения о Teams PowerShell](../teams-powershell-overview.md) .


## <a name="before-you-start"></a>Перед началом работы

Скачайте и установите [модуль PowerShell Skype для бизнеса Online](https://www.microsoft.com/download/details.aspx?id=39366), а затем перезагрузите компьютер при появлении соответствующего запроса.

Для более рациональной работы ознакомьтесь [со списком Управление Skype для бизнеса Online в Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).


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
> Вы также можете использовать назначение пакетной политики для назначения политики обмена сообщениям большим наборам пользователей. Дополнительные сведения можно найти в разделе [назначение политик большим наборам пользователей в учебном заведении](../batch-policy-assignment-edu.md) и [назначение политик пользователям в Teams](../assign-policies.md).
