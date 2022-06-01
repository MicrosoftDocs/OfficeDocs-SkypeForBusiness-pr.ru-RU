---
title: Пример сценария PowerShell. Создание & политики обмена сообщениями
author: serdars
ms.author: serdars
manager: serdars
ms.topic: article
ms.reviewer: ritikag
ms.service: msteams
audience: admin
description: Используйте этот сценарий PowerShell, чтобы создать политику обмена сообщениями в Teams и назначить ее пользователям в организации.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 09254f9ed85f69551ee825dbeb8ae063a010f780
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823710"
---
# <a name="powershell-script-sample---create-and-assign-a-messaging-policy"></a>Пример сценария PowerShell — создание и назначение политики обмена сообщениями

Используйте этот сценарий PowerShell, чтобы создать политику обмена сообщениями в Microsoft Teams и назначить ее пользователям. 

Дополнительные сведения об использовании этого скрипта PowerShell см. в [кратком руководстве по Teams для образования](../teams-quick-start-edu.yml).

Этот сценарий использует [командлет Grant-CsTeamsMessagingPolicy](/powershell/module/skype/grant-csteamsmessagingpolicy), который находится в Skype для бизнеса PowerShell Online. [Дополнительные Teams powerShell](../teams-powershell-overview.md) см. в Teams powerShell.


## <a name="before-you-start"></a>Перед началом работы

Скачайте и установите [Skype для бизнеса PowerShell Online](https://www.microsoft.com/download/details.aspx?id=54616), а затем перезапустите компьютер при появлении соответствующего запроса.

Дополнительные сведения см. в статье ["Управление Skype для бизнеса Online с помощью Office 365 PowerShell"](/office365/enterprise/powershell/manage-skype-for-business-online-with-office-365-powershell).

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
> Вы также можете назначить политику обмена сообщениями непосредственно пользователям в большом масштабе с помощью назначения пакетной политики или группе, в которую являются пользователи. Дополнительные [сведения см.](../batch-group-policy-assignment-edu.md) в статье "Назначение политик большим наборам пользователей в учебном заведении" и "[Назначение](../policy-assignment-overview.md) политик пользователям в Teams".