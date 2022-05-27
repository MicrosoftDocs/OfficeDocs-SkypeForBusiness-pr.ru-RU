---
title: Управление доступом на основе смен для сотрудников без компьютеров в Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте, как управлять доступом на основе смен в Teams для сотрудников без компьютеров в организации.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9cb488dfb95647079b51269059ee5c0b120cb9cc
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675221"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Управление доступом на основе смен для сотрудников без компьютеров в Teams
## <a name="overview"></a>Обзор

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Присутствие в Microsoft Teams указывает на текущую доступность и состояние пользователя для других пользователей. Присутствие сотрудников переднего плана часто менее предсказуемо, чем у других сотрудников, так как их рабочее время обычно не совпадает каждый день. Как администратор вы можете настроить Teams для отображения набора состояний присутствия на основе смен для сотрудников, работающих с внешними службами в организации, чтобы указать, когда они находятся в режиме "вкл." и "выкл.".

Эти состояния присутствия на основе смены сплошной&mdash;![зеленой галочки обозначают on shift.](../../media/flw-presence-on-shift.png) **При смене** серый ![круг с x указывает на отключенную смену.](../../media/flw-presence-off-shift.png) **Off shift**, ![Solid red circle, indicates Busy](../../media/flw-presence-busy.png) **Busy**&mdash;are separate from the [default set of presence states](../../presence-admins.md) in Teams. С помощью этих двух наборов состояний присутствия можно настроить различные возможности для сотрудников в организации в зависимости от их роли.

С помощью доступа на основе смены вы можете управлять доступом к Teams, когда сотрудники переднего плана находятся вне смены. Например, можно настроить Teams, чтобы отобразить сообщение, которое сотрудники переднего плана должны подтвердить, чтобы они могли использовать Teams, когда они не находятся в запланированной смене.  

## <a name="scenario"></a>Сценарий

Ниже приведен пример того, как ваша организация может управлять доступом на основе смен.

У вас есть сотрудники без компьютеров в организации, которые должны быть оплачены только в течение нескольких часов, в течение которых они работают в смене, запланированной и утвержденной руководителем. Они не должны быть оплачены за время, затраченное на работу вне запланированной смены, включая использование Teams приложения. Вы настроили настраиваемое сообщение "Ваше время в Teams при смене не учитывается в расчетных часах", которое отображается, когда сотрудники без смены пытаются получить доступ к Teams в нерабочее время. Если они решили использовать Teams, они нажимают кнопку **"Я принимаю**" с пониманием того, что они не будут оплачены за это время.

В вашей организации также есть информационные работники, которые получают заработную плату и не работают в смену. Вы настраиваете информационные работники для использования состояний присутствия по умолчанию в Teams при одновременном предоставлении сотрудникам переднего плана сведений о присутствии на основе смен.

## <a name="shift-based-presence-states"></a>Состояния присутствия на основе смены

Ниже приведены состояния присутствия на основе смены.

|Настроено в приложении |Настроено пользователем  |Дополнительные сведения  |
|---------|---------|---------|
|![Сплошной зеленый флажок указывает на "В смене".](../../media/flw-presence-on-shift.png) На смену     |         |Автоматическое задание в начале смены         |
|![Серый круг с x, обозначает отключение смены](../../media/flw-presence-off-shift.png) Выкл. смена     |         |Автоматическое задание в конце смены         |
|![Сплошной красный кружок означает "Занят(а)".](../../media/flw-presence-busy.png) Занят(а)      | ![Сплошной красный кружок означает "Занят(а)"](../../media/flw-presence-busy.png) Занят(а)         |Автоматически задается. Можно также задать вручную, когда сотрудник переднего плана находится в режиме смены.|

## <a name="off-shift-access-to-teams"></a>Отключение доступа к Teams

Эта функция позволяет управлять доступом к Teams при отключении сотрудников без смены. Вы можете настроить Teams, чтобы отобразить сообщение для сотрудников переднего плана, если они Teams при смене. Прежде чем использовать Teams,  необходимо нажать кнопку "Я принимаю", чтобы подтвердить Teams.

Вы можете использовать сообщение по умолчанию, выбрать из набора предварительно определенных сообщений или настроить сообщение для отображения любого нужного текста. Ниже приведено сообщение по умолчанию:

![Снимок экрана: сообщение по умолчанию.](../../media/shifts-presence-message.png)

Вы также можете задать частоту отображения сообщения и установить льготный период между началом первой или последней смены и ограничением доступа к Teams смены.

## <a name="manage-shift-based-access"></a>Управление доступом на основе смен

Как администратор вы используете политики для управления присутствием на основе смен для сотрудников без компьютеров в организации. Управление этими политиками выполняется с помощью следующих командлетов PowerShell:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Используйте командлет New-CsTeamsShiftsPolicy, чтобы создать новую политику, задать нужные параметры политики, а затем использовать командлет Grant-CsTeamsShiftsPolicy, чтобы назначить политику пользователям.

Вот некоторые примеры. Подробные сведения о каждом параметре политики, включая список предварительно определенных сообщений о смене, которые можно выбрать, см. в разделе [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Пример 1

В этом примере мы создадим новую политику с именем Off Shift Teams Access Default Message. В этой политике включено присутствие на основе смены, и сообщение по умолчанию отображается каждый раз, когда пользователь, которому назначена эта политика, Teams при отключении смены. Пользователь может использовать Teams, если он принимает сообщение, и льготный период между началом первой или последней смены и ограничением доступа — 10 минут.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Используйте параметр **ShiftNoticeMessageType** , чтобы задать сообщение, которое требуется отобразить. Список предварительно определенных сообщений, которые можно выбрать для этого параметра, см. в разделе [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Пример 2 

В этом примере мы создадим новую политику с именем Off Shift Teams Access Custom Message. В этой политике включено присутствие на основе смены, и настраиваемое сообщение отображается каждый раз, когда пользователь, которому назначена эта политика, Teams при переходе на смену. Пользователь может использовать Teams, если он принимает сообщение, и льготный период между началом первой или последней смены и ограничением доступа — 15 минут.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Используйте параметр **ShiftNoticeMessageType** , чтобы задать сообщение, которое требуется отобразить. Дополнительные сведения см. [в разделе New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Пример 3

В этом примере мы создадим новую политику с именем Off Shift Teams Access Message1. В этой политике включено присутствие на основе смен, и следующее предопределенное сообщение отображается каждый раз, когда пользователь, которому назначена эта политика, Teams при смене.

  "Ваш работник не разрешает или не утверждает использование своей сети, приложений, систем или средств сотрудниками, не являыми сотрудниками без исключения или почасового использования в нерабочее время. Принимая условия, вы подтверждаете, что использование Teams во время смены не авторизовано и вам не будет компенсация". 

Пользователь может использовать Teams, если он принимает сообщение, и льготный период между началом первой или последней смены и ограничением доступа — три минуты.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Используйте параметр **ShiftNoticeMessageType** , чтобы задать сообщение, которое требуется отобразить. Список предварительно определенных сообщений, которые можно выбрать для этого параметра, см. в разделе [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-4"></a>Пример 4

В этом примере мы назначаем политику Off Shift Teams Access Custom Message пользователю с именем remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Статьи по теме

- [Управление приложением "Смены" для организации в Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Обзор PowerShell в Teams](../../teams-powershell-overview.md)