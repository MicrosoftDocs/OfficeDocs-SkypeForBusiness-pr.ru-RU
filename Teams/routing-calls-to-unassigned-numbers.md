---
title: Маршруты звонков на ненаписаные номера
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Узнайте, как перена маршрутизации звонков на ненанамер номера в организации.
ms.openlocfilehash: 4d9c40a0b4a01f7fae4a755603cb5cf7eb132f5c
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767372"
---
# <a name="routing-calls-to-unassigned-numbers"></a>Маршруты звонков на ненаписаные номера

Как администратор вы можете перенаправление звонков на ненаправленные номера в организации. Например, вам может потребоваться перенанакомить звонки на ненанаписаные номера следующим образом: 

- Перенакомьть все звонки на заданный ненаданный номер на настраиваемый извешение.

- Перенаключение всех звонков на заданный ненаданный номер на основную кнопу.

Вы можете перена маршрутизируются вызовы на ненастройные номера для пользователя, на учетную запись ресурса, связанную с автозавершением или очередью звонков, или в службу объявления, которая будет использовать для звоняющего настраиваемый звуковой файл.

## <a name="configuration"></a>Конфигурация

Для переназначения звонков на неназначенный номер используйте командлет New/Get/Set/Remove-CsTeamsNussignedNumberTreatment, доступный в модуле Teams PowerShell 2.5.1 или более поздней.

Необходимо указать номер или диапазон номеров, а также связанную маршрутику для звонков на эти номера. Например, следующая команда указывает, что все вызовы на номер +1 (555) 222-3333 будут перенаадресовы на учетную запись aa@contoso.com:

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

В следующем примере указывается, что все звонки в диапазон номеров +1 (555) 333-0000 на +1 (555) 333-9999 будут переналаны в службу объявления, которая будет использовать звуковой файл MainAnnouncement.wav вызываемой службе.

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>Notes

- Если маршрутия к объявлению, звуковой файл будет один разыграно вызываемой.

- Чтобы перена маршрутизировать звонки на ненаназваченные абонентские номера плана звонков Майкрософт, ваш клиент должен иметь доступные кредиты [на](what-are-communications-credits.md)связь.

- Чтобы перена маршрутизировать звонки на нена назначенные номера служб плана звонков Майкрософт, у вашего клиента должна быть по крайней мере одна лицензия телефонная система — виртуальный пользователь.

- Поддерживаются пользовательские форматы звуковых файлов: WAV (без сжимаемого, линейный PCM с моно- или стереофоной глубиной 8/16/32-битной глубины), WMA (только моно) и MP3. Размер звукового файла не может быть больше 5 МБ.

## <a name="related-topics"></a>Статьи по теме

- [Get-CsTeamsNussignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsNussignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsNussignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsNussignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)
