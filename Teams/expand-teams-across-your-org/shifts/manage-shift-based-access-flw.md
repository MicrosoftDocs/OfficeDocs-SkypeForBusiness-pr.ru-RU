---
title: Управление доступом на основе смен для сотрудников, работающих с телефоном, в Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте, как управлять доступом на основе смен в Teams для сотрудников с frontline в организации.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0e2bcffd23a8603acbb0954ddb6a24dad9000332
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58584613"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Управление доступом на основе смен для сотрудников, работающих с телефоном, в Teams

> [!IMPORTANT]
> Поддержка Microsoft StaffHub прекращена с 30 июня 2020 г. Мы будем строить возможности StaffHub в Microsoft Teams. В настоящее время в состав Teams входит приложение "Смены" для управления расписанием, и со временем будут развернуты дополнительные возможности. Приложение StaffHub перестало работать для всех пользователей 30 июня 2020 г. При любой попытке открыть StaffHub отображается сообщение, ведущее на скачивание Teams. Дополнительные сведения см. в статье [Поддержка Microsoft StaffHub прекращена](microsoft-staffhub-to-be-retired.md).  

## <a name="overview"></a>Обзор

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Присутствие в Microsoft Teams указывает на текущую доступность и статус пользователя для других пользователей. Присутствие сотрудников, работающих на переднем телефоне, часто менее предсказуемо, чем у других сотрудников, так как их рабочие часы обычно не одинаковы каждый день. Как администратор вы можете настроить Teams, чтобы у сотрудников вашей организации было по-настоящему указано, когда они работают или отключаются.

Эти состояния присутствия на основе смены. Сплошная зеленая метка, которая указывает на то, что при смене в смене , Серый кружок с x, означает, что отключена смена Отключена , Сплошной красный кружок, что означает, что занят не зависит от набора состояния присутствия по умолчанию в &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; Teams. [](../../presence-admins.md) С помощью этих двух наборов состояния присутствия вы можете настраивать разные функции для пользователей в организации в зависимости от их роли.

С помощью shift-based access вы можете управлять доступом к Teams, когда сотрудники, не работающие на переднем телефоне, отключались от смены. Например, можно настроить отображение Teams, чтобы сотрудники, работающие в переднем телефоне, могли использовать Teams, если они не работают в запланированную смену.  

## <a name="scenario"></a>Сценарий

Вот пример того, как ваша организация может управлять доступом на основе смен.

У вас есть сотрудники, работающие в вашей организации, которые должны платить только за часы работы в смену, запланированную и утвержденную руководителем. Им не следует платить за время, затраченное на работу вне запланированной смены, включая использование Teams приложения. Вы настроили настраиваемое сообщение "Ваше время в Teams при выходе из смены не будет учитываться в часах оплаты", которое отображается, когда при работе с Teams не на смену. Если они будут использовать Teams, он нажмет кнопку Я **принимаю** с пониманием, что оплата за это время не будет оплачена.

В вашей организации также есть информационные работники, которые получают зарплату и не работают в смену. Сотрудники, работающие с информацией, могут использовать стандартные состояния присутствия Teams при этом давая сотрудникам сменные сведения о присутствии.

## <a name="shift-based-presence-states"></a>Состояния присутствия на основе смены

Ниже перейти к состояниям присутствия на основе смены.

|Настроено в приложении |Настроено пользователем  |Дополнительные сведения  |
|---------|---------|---------|
|![Сплошная зеленая метка с отметкой "В сдвиге"](../../media/flw-presence-on-shift.png) На смене     |         |Автоматическое настройка в начале смены         |
|![Серый кружок с x, означает Отключение смены](../../media/flw-presence-off-shift.png) Отключение смены     |         |Автоматическое настройка в конце смены         |
|![Сплошной красный кружок означает "Занят(а)"](../../media/flw-presence-busy.png) Занят(а)      | ![Сплошной красный кружок означает "Занят(а)"](../../media/flw-presence-busy.png) Занят(а)         |Настроить автоматически. Можно также вручную настроить, когда сотрудник в режиме смены.|

## <a name="off-shift-access-to-teams"></a>Отключение shift access для Teams

Эта функция позволяет управлять доступом к Teams, когда сотрудники, не работающие со сменой, находятся вне связи. Можно настроить отображение Teams для сотрудников, работающих с frontline, если они работают с Teams при выходе из смены. Перед использованием  Teams. Чтобы подтвердить это сообщение, необходимо нажать кнопку Я принимаю.

Вы можете использовать сообщение по умолчанию, выбрать один из стандартных сообщений или настроить отображение нужного текста. Сообщение по умолчанию:

![Снимок экрана: сообщение по умолчанию](../../media/shifts-presence-message.png)

Вы также можете настроить частоту отображения сообщения и установить льготный период между началом первой или последней смены и ограничением доступа к Teams сменам.

## <a name="manage-shift-based-access"></a>Управление доступом на основе смен

Администраторы могут управлять присутствием сотрудников в организации с учетом смены. Управлять этими политиками можно с помощью следующих cmdlets PowerShell:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Используйте New-CsTeamsShiftsPolicy для создания новой политики, задайте нужные параметры политики, а затем используйте Grant-CsTeamsShiftsPolicy для назначения политики пользователям.

Вот некоторые примеры. Подробные сведения о каждом параметре политики и параметре, включая список предопределений сообщений со сменами, которые можно выбрать, см. в описании [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-1"></a>Пример 1

В этом примере мы создадим политику Off Shift Teams Access Default Message. В этой политике присутствие на основе смены включено, и сообщение по умолчанию отображается каждый раз, когда пользователь, которому назначена эта политика, Teams при выходе из смены. Пользователь может использовать Teams, если принимает сообщение, и период отсрочки между началом первой или последней сменой и ограничением доступа составляет 10 минут.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> С помощью **параметра ShiftNoticeMessageType** можно настроить сообщение, которое вы хотите отобразить. Список предварительно определенных сообщений, которые можно выбрать для этого параметра, см. в списке [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-2"></a>Пример 2 

В этом примере мы создадим политику Off Shift Teams Access Custom Message. В этой политике включено присутствие на основе смены, и каждый раз, когда пользователь, которому назначена эта политика, Teams при выходе из нее. Пользователь может использовать Teams, если принимает сообщение, и период отсрочки между началом первой или последней сменой и ограничением доступа составляет 15 минут.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> С помощью **параметра ShiftNoticeMessageType** можно настроить сообщение, которое вы хотите отобразить. Дополнительные информации см. [в new-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>Пример 3

В этом примере мы создадим политику Off Shift Teams Access Message1. В этой Teams политике включено присутствие на основе смены, и при каждом выходе из нее пользователю, которому назначена эта политика, отображается следующее предопределированное сообщение.

  "Ваш работодателей не разрешает или не утверждает использование его сети, приложений, систем или инструментов нерабоочными или нерабоочными сотрудниками в нерабочные часы. Принимая приглашение, вы подтверждаете, что ваше использование Teams смены не разрешено и вам не будет возмещена компенсация". 

Пользователь может использовать Teams, если принимает сообщение, и период отсрочки между началом первой или последней сменой и ограничением доступа составляет три минуты.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> С помощью **параметра ShiftNoticeMessageType** можно настроить сообщение, которое вы хотите отобразить. Список предварительно определенных сообщений, которые можно выбрать для этого параметра, см. в списке [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-4"></a>Пример 4

В этом примере мы назначим политику Отключение Teams Доступ к пользовательскому сообщению пользователю с именем remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Статьи по теме

- [Управление приложением "Смены" для организации в Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Обзор PowerShell в Teams](../../teams-powershell-overview.md)