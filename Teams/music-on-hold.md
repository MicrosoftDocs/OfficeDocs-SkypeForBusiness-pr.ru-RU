---
title: Музыка при удержании
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: ''
description: Узнайте, как управлять функцией "Музыка при удержании" в телефонная система.
ms.openlocfilehash: 7a7a79bb2d96bcd43e12b27424630acd7a0c90eb
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355738"
---
# <a name="music-on-hold"></a>Музыка при удержании

Когда Microsoft Teams входящий звонок из телефонной сети общего перейти на удержание, звонящая по ПСПС может прослушивать выбранную музыку.

Она является либо музыкой по умолчанию, предоставляемой корпорацией Майкрософт, либо настраиваемой музыкой, которую вы загружаете и настраиваете. Администратор клиента настраивает, доступна ли музыка при удержании, создавая политику Teams звонков и назначая ее Teams пользователю.

Музыка по умолчанию, Microsoft Teams в сценариях вызовов через ПСС, не должна быть бесплатной в вашей организации.

Обратите внимание на то, что в других сценариях звоня люди, вызыватели ПСОП, могут прослушивать музыку при удержании. Например, если звонок находится в очереди облачных зовов или когда звонок находится в Microsoft Teams пользователем. Эти сценарии не охватываются функциями, упомянутыми в этой статье, и не контролируются этими возможностями.

## <a name="configure-music-on-hold"></a>Настройка музыки при удержании

Чтобы настроить музыку при удержании:

1.  В левой области навигации Центра администрирования Teams перейдите в > **голосовой почты**.

2.  На **вкладке Управление политиками** выберите одну из существующих политик или создайте новую.

3.  В поле  **"Музыка при удержании"** для вызывающих ПСОП выберите в меню пункт Включено.

Вы также можете настроить музыку при удержании с помощью Teams PowerShell. В TeamsCallingPolicy измените параметр MusicOnHoldEnabledType на Enabled (Включено), а затем о предоставлении экземпляра политики одному или нескольким пользователям.

Если для Teams настроена политика Teams музыки при удержании отключена, то при Teams пользователь не будет играть музыку.

## <a name="configure-custom-music"></a>Настройка пользовательской музыки

Помимо воспроизведения музыки по умолчанию для вызывающих ПСОП, вы можете добавить пользовательский звуковой файл с музыкой или другим звуком и настроить его для воспроизведения вызываемому звоняну через ПСОП.
Например, отделу или организации может потребоваться поставить на удержание настраиваемую рекламу или музыку, если внешние звонители по ПСОП поставлены на удержание.  

> [!NOTE]
> Вы несете ответственность за независимое очистку и обеспечение всех необходимых прав и разрешений на использование музыки или звуковых файлов в Microsoft Teams службе. Это может быть интеллектуальная собственность и другие права в музыке, звуковых эффектах, звуке, марках, именах и другом содержимом звуковых файлов от всех соответствующих владельцев прав. Владельцы могут включать в себя исполнителей, субъектов, исполнителей, зауметелей, авторов, редакторов, записных наклеев, издателей музыки, издателей музыки, юниверсов, авторов прав, коллективных организаций и любых других лиц, которые являются владельцами, контролируют или лицензируют музыкальные авторские права, звуковые эффекты, звуковые и другие права интеллектуальной собственности.

Чтобы настроить настраиваемую музыку при удержании, используйте командлеты PowerShell New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy и Import/Get/Remove-CsOnlineAudioFile в модуле Teams PowerShell 2.5.0 или более поздней.


1. Убедитесь, Teams включена музыка для вызывающих ЗВОНКОВ по ПСОП, в политике Teams звонков. 

2. Upload настраиваемый звуковой файл.

3. Создайте политику Teams удержания вызовов со ссылкой на настраиваемый звуковой файл и назначьте его Teams пользователю.

### <a name="upload-the-custom-audio-file"></a>Upload настраиваемый звуковой файл

Настройка пользовательской музыки при удержании начинается с отправки звукового файла. Для этого используется Import-CsOnlineAudioFile PowerShell. Ниже показан пример отправки звукового файла MP3 с помощью интерфейса PowerShell.

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Ссылка на звуковой файл в политике Teams удержания зовов

После отправки звукового файла необходимо создать ссылку на файл в политике Teams удержания звонка с помощью его ИД при создании или Teams удержания зова. Например:

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

После создания политики удержания Teams вы можете предоставить ее пользователям, используя Grant-CsTeamsCallHoldPolicy:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Чтобы получить сведения о добавленных звуковых файлах, воспользуйтесь Get-CsOnlineAudioFile видео.

Чтобы удалить добавленный звуковой файл, воспользуйтесь Remove-CsOnlineAudioFile видео. Прежде чем удалять звуковой файл, убедитесь, что он не используется в TeamsCallHoldPolicy.

## <a name="feature-availability"></a>Доступность функций

В таблице ниже указано, какие функции клиентов и устройств поддерживают музыку при удержании и пользовательскую музыку при удержании. Корпорация Майкрософт продолжает добавлять поддержку функций, поэтому часто проверяйте наличие дополнительных возможностей.


| Компонент | Рабочие журналы <br> Windows/Mac OS | Браузер | Мобильный <br> iOS | Мобильный <br> Android | Teams Телефон |
| :------------| :------- | :------- | :------- | :------- | :------- |
| Удержание звонка через ПСС 1:1 | -Музыка при удержании<br>-Custom Music on Hold | -Музыка при удержании<br>-Custom Music on Hold | -Музыка при удержании<br>-Custom Music on Hold | Музыка при удержании | Музыка при удержании |
| Удержание для консультационной передачи при вызове 1:1 по ДНР |-Музыка при удержании<br>-Custom Music on Hold | | | | |

## <a name="restrictions"></a>Ограничения

- Музыка при удержании доступна только в коммерческом облаке.

- Музыка при удержании доступна только в режиме TeamsOnly.

- Если вызываемая Teams включена для Location-Based маршрутизов, вызываемая музыка при удержании не может быть включена.

- После отправки звуковой файл экспортировать нельзя. его можно удалить только.

- Пользовательская музыка при удержании недоступна для пользователей, настроенных для внешнего вида (делегирования) общей строки и при вызове в парке вызовов. Будет играть стандартная музыка при удержании.

- В некоторых случаях для воспроизведения музыки при удержании вызов об обхода прямой маршрутации мультимедиа преобразуется в обход без мультимедиа, а звонок будет оставаться в обходе без мультимедиа, пока звонок не будет завершен.

## <a name="related-topics"></a>Статьи по теме

- [Назначение политик пользователям](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)
