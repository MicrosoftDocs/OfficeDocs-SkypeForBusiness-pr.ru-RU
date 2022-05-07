---
title: Маршрутизация вызовов неназначенных номеров
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
description: Узнайте, как маршрутизировать вызовы на неназначенных номерах в организации.
ms.openlocfilehash: cc464419375b6391d0d95d6e99441777a40da9cb
ms.sourcegitcommit: bc73017b4a3fe6271830bc8c5044bfd43eec80c0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2022
ms.locfileid: "65266930"
---
# <a name="routing-calls-to-unassigned-numbers"></a>Маршрутизация вызовов неназначенных номеров

Администратор может направлять вызовы на неназначенных номерах в организации. Например, можно перенаправить вызовы на неназначенных номерах следующим образом: 

- Перенаправь все вызовы на указанный неназначенных номеров в настраиваемое объявление.

- Перенаправляйте все вызовы на указанный неназначенных номеров в основную коммутаторную систему.

Вы можете направлять вызовы на неназначенных номерах пользователю, в учетную запись ресурса, связанную с автосекретарем или очередью звонков, или в службу объявлений, которая будет воспроизводить пользовательский звуковой файл для вызывающего абонента.

## <a name="configuration"></a>Конфигурация

Для маршрутизации вызовов на неназначенный номер используйте командлет New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment, доступный в Teams PowerShell 2.5.1 или более поздней версии.

Необходимо указать вызываемый номер или диапазон номеров и связанную маршрутизацию для вызовов этих номеров. Например, приведенная ниже команда указывает, что все вызовы на номер +1 (555) 222-3333 будут направляться в учетную запись ресурса aa@contoso.com:

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

В следующем примере указывается, что все вызовы в диапазоне номеров +1 (555) от 333-0000 до +1 (555) 333-9999 будут направляться в службу объявлений, которая будет воспроизводить звуковой файл MainAnnouncement.wav вызывающей стороне.

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>Notes

- При маршрутизации к объявлению звуковой файл будет воспроизводиться один раз вызываемой стороне.

- Чтобы маршрутизировать вызовы на неназначенных номерах подписчиков плана звонков Майкрософт, ваш клиент должен иметь доступные кредиты [на](what-are-communications-credits.md) связь.

- Чтобы перенаправить вызовы на неназначенных номера служб плана звонков Майкрософт, у клиента должна быть по крайней мере одна лицензия телефонная система виртуального пользователя.

- Пользовательские форматы аудиофайла поддерживают WAV (несжатое линейное БПО с глубиной 8/16/32 бит в моно или стерео), WMA (только моно) и MP3. Содержимое звукового файла не может превышать 5 МБ.

- Как входящие вызовы Microsoft Teams, так и исходящие вызовы из Microsoft Teams будут проверяться на соответствие диапазону неназначенных номеров.

- Если указанный шаблон или диапазон содержит номера телефонов, назначенные пользователю или учетной записи ресурса в клиенте, вызовы этих телефонных номеров будут направляться в соответствующий целевой объект, а не на указанную обработку неназначенных номеров. Другие проверки чисел в диапазоне отсутствуют. Если диапазон содержит допустимый внешний номер телефона, исходящие звонки из Microsoft Teams на этот номер будут направляться в соответствии с процедурой.

## <a name="related-topics"></a>Статьи по теме

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
