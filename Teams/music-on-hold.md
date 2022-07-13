---
title: Музыка на удержании
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
description: Узнайте, как управлять функцией "Музыка при удержании" в телефонной системе.
ms.openlocfilehash: 9d8fa247ffdc982c5d41777c68f6b620a92644e3
ms.sourcegitcommit: 8fc2d6a824e1e119f54ea2347bc5c10cc076956d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2022
ms.locfileid: "66773758"
---
# <a name="music-on-hold"></a>Музыка на удержании

Когда пользователь Microsoft Teams помещает входящий звонок на удержание, вызывающий абонент может прослушивать выбранную музыку.

Воспроизводимая музыка — это либо музыка по умолчанию, предоставляемая корпорацией Майкрософт, либо пользовательская музыка, которую вы отправляете и настраиваете. Администратор клиента может настроить доступность музыки при удержании, создав политику звонков Teams и назначив ее пользователю Teams.

Музыка по умолчанию, предоставляемая в сценариях вызовов Microsoft Teams, не оплачивается вашей организацией.

Обратите внимание, что вызывающие абоненты могут прослушивать музыку при удержании в других сценариях. Например, при вызове в очередь облачных звонков или при парковке звонка пользователем Microsoft Teams. Эти сценарии не рассматриваются и не контролируются функциями, упомянутыми в этой статье.

## <a name="configure-music-on-hold"></a>Настройка музыки при удержании

Чтобы настроить музыку при удержании:

1. В левой области навигации Центра администрирования Teams перейдите к политикам **голосовых > вызовов**.

2. На **вкладке "Управление политиками** " выберите одну из существующих политик или создайте новую.

3. В поле **"Музыка при удержании" для** вызывающих абонентов ТСОП выберите "Включено **" в** раскрывающемся меню.

Вы также можете настроить музыку на удержании с помощью модуля Teams PowerShell. В TeamsCallingPolicy измените параметр MusicOnHoldEnabledType на "Включено", а затем предоставьте этот экземпляр политики одному или нескольким пользователям.

Если для пользователя Teams политика звонков Teams с параметром "Музыка на удержании" отключена, то при переводе звонка на удержание пользователь Teams не будет воспроизводить музыку.

## <a name="configure-custom-music"></a>Настройка пользовательской музыки

Помимо воспроизведения музыки по умолчанию для вызывающих абонентов, вы можете передать пользовательский звуковой файл с музыкой или другим звуковым содержимым и настроить его для воспроизведения вызывающей стороне.
Например, отделу или организации может потребоваться воспроизвести настраиваемое объявление или пользовательскую музыку, когда внешние вызывающие абоненты ТСОП помещаются на удержание.

Настройка выполняется с помощью политик удержания вызовов.

> [!NOTE]
> Вы несете ответственность за независимую очистку и защиту всех необходимых прав и разрешений для использования любого звукового или звукового файла в службе Microsoft Teams. Это может включать интеллектуальную собственность и другие права на музыку, звуковые эффекты, звук, торговые марки, имена и другое содержимое в звуковом файле от всех соответствующих владельцев прав. Владельцы могут включать в себя исполнителей, субъектов, исполнителей, оркестров, авторов, авторов, записей, издателей музыки, объединений, организаций, ответственных за права, организаций управления совместной работы, а также любых других лиц, которые владеют, контролирует или лицензируют авторские права на музыку, звуковые эффекты, звуковые и другие права интеллектуальной собственности.

### <a name="use-the-teams-admin-center"></a>Использование Центра администрирования Teams
Вы можете использовать Центр администрирования Teams, чтобы настроить пользовательскую музыку при удержании для пользователей, создав или изменяя политики удержания вызовов.

Чтобы настроить новую политику удержания  вызовов:

1. В Центре администрирования Teams перейдите **к политикам** >  удержания **голосовых вызовов**.

2. Выберите вкладку **"Добавить** ".

3. Присвойте политике имя и описание.

4. Выберите **"Отправить файл** ", чтобы отправить пользовательский звуковой файл музыки.

5. Нажмите **кнопку "Применить"**.

### <a name="assign-a-custom-call-hold-policy-to-users"></a>Назначение пользовательской политики удержания  вызовов пользователям

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="use-powershell"></a>Использование PowerShell
Чтобы настроить пользовательскую музыку при удержании, используйте командлеты PowerShell New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy и Import/Get/Remove/Export-CsOnlineAudioFile в модуле Teams PowerShell 3.0.0 или более поздней версии.

Поддерживаемые форматы звука и максимальный размер файла см. в [разделе Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

1. Убедитесь, что в политике звонков Teams для вызывающих абонентов ТСОП установлено значение "Включено" для пользователя Teams. 

2. Отправьте пользовательский звуковой файл.

3. Создайте политику удержания  вызовов Teams, ссылаясь на пользовательский звуковой файл, и назначьте ее пользователю Teams.

### <a name="upload-the-custom-audio-file"></a>Отправка пользовательского звукового файла

Настройка пользовательской музыки на удержании начинается с отправки звукового файла. Для этой цели используется командлет PowerShell [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) .

Ниже приведен пример отправки звукового файла MP3 с Windows PowerShell 5.1. Другие примеры см. в [разделе Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile).

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Ссылка на звуковой файл в политике удержания  вызовов Teams

После отправки звукового файла необходимо указать ссылку на файл в политике удержания  вызовов Teams, используя идентификатор файла при создании или настройке политики удержания параметров зова Teams. Например:

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

После создания новой политики удержания  вызовов Teams вы можете предоставить ее пользователям, используя Grant-CsTeamsCallHoldPolicy следующим образом:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Чтобы получить сведения об отправленных звуковых файлах, используйте Get-CsOnlineAudioFile командлета.

Чтобы удалить отправленный звуковой файл, используйте Remove-CsOnlineAudioFile командлета. Перед удалением звукового файла убедитесь, что вы не используете этот звуковой файл в TeamsCallHoldPolicy.

Чтобы экспортировать отправленный звуковой файл, используйте Export-CsOnlineAudioFile командлета.

## <a name="feature-availability"></a>Доступность функций

В следующей таблице показано, какие функции, на которых клиенты и устройства поддерживают музыку при удержании и пользовательскую музыку при удержании. Корпорация Майкрософт продолжает добавлять поддержку функций, поэтому часто проверяйте наличие дополнительной доступности.

| Компонент | Рабочие журналы <br> Ос Windows или Mac | Браузер | Мобильный <br> iOS | Мобильный <br> Android | Телефон Teams |
| :------------| :------- | :------- | :------- | :------- | :------- |
| Удержание при вызове ТСОП 1:1 | -Музыка при удержании<br>-Custom Music on Hold | -Музыка при удержании<br>-Custom Music on Hold | -Музыка при удержании<br>-Custom Music on Hold | -Музыка при удержании<br>-Custom Music on Hold | -Музыка при удержании<br>-Custom Music on Hold |
| Удержание при вызове Teams 1:1 | -Музыка при удержании<br>-Custom Music on Hold | -Музыка при удержании<br>-Custom Music on Hold | -Музыка при удержании<br>-Custom Music on Hold | -Музыка при удержании<br>-Custom Music on Hold | -Музыка при удержании<br>-Custom Music on Hold |
| Удержание на консультации при вызове ТСОП 1:1 |-Музыка при удержании<br>-Custom Music on Hold || -Музыка при удержании<br>-Custom Music on Hold | -Музыка при удержании<br>-Custom Music on Hold | -Музыка при удержании<br>-Custom Music on Hold |
| Удержание на консультации при вызове Teams 1:1 |-Музыка при удержании<br>-Custom Music on Hold || -Музыка при удержании<br>-Custom Music on Hold | -Музыка при удержании<br>-Custom Music on Hold | -Музыка при удержании<br>-Custom Music on Hold |

## <a name="restrictions"></a>Ограничения

- Музыка при удержании доступна только в коммерческих и облачных экземплярах GCC.

- Музыка при удержании доступна только в том случае, если пользователь находится в режиме TeamsOnly.

- Если для вызываемого пользователя Teams включена Location-Based маршрутизации, звук при удержании не может воспроизводиться вызываемой стороне.

- Пользовательская музыка при удержании недоступна для пользователей, настроенных для общего вида строки (делегирование) и при использовании парковки вызовов. Будет воспроизводиться стандартная музыка на удержании.

- В некоторых сценариях вызов обхода сервера-посредника прямой маршрутизации будет преобразован в обход без носителя для воспроизведения музыки при удержании, а вызов будет оставаться обходом без носителя до завершения вызова.

## <a name="related-topics"></a>Статьи по теме

- [Назначение политик пользователям](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

- [Export-CsOnlineAudioFile](/powershell/module/skype/export-csonlineaudiofile)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)
