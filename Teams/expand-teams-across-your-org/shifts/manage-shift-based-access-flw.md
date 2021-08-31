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
ms.openlocfilehash: dd02c93639f0756982c35972e563e06cc41a0687
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726828"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Управление доступом на основе смен для сотрудников, работающих с телефоном, в Teams

> [!IMPORTANT]
> Поддержка Microsoft StaffHub прекращена с 30 июня 2020 г. Мы будем строить возможности StaffHub в Microsoft Teams. В настоящее время в состав Teams входит приложение "Смены" для управления расписанием, и со временем будут развернуты дополнительные возможности. Приложение StaffHub перестало работать для всех пользователей 30 июня 2020 г. При любой попытке открыть StaffHub отображается сообщение, ведущее на скачивание Teams. Дополнительные сведения см. в статье [Поддержка Microsoft StaffHub прекращена](microsoft-staffhub-to-be-retired.md).  

## <a name="overview"></a>Обзор

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Присутствие в Microsoft Teams указывает на текущую доступность и статус пользователя для других пользователей. Присутствие сотрудников, работающих на переднем телефоне, часто менее предсказуемо, чем у других сотрудников, так как их рабочие часы обычно не одинаковы каждый день. Как администратор вы можете настроить Teams, чтобы показать сотрудникам вашей организации набор состояния присутствия на основе смены, чтобы они могли указать, когда они находятся в работе и отключается.

Эти состояния присутствия на основе смены обозначены зеленой сплошной зеленой &mdash; ![ меткой, которая указывает на "В смене".](../../media/flw-presence-on-shift.png) **On shift**, ![ Gray circle with x, indicates Off shift.](../../media/flw-presence-off-shift.png) **Отключенная смена**, ![ сплошной красный кружок, означает, что занят не является набором состояния присутствия по умолчанию в ](../../media/flw-presence-busy.png)  &mdash; Teams. [](../../presence-admins.md) С помощью этих двух наборов состояния присутствия вы можете настраивать разные функции для пользователей в организации в зависимости от их роли.

С помощью shift-based access вы можете управлять доступом к Teams, когда сотрудники, не работающие на переднем телефоне, не работают в смену. Например, можно настроить отображение Teams, что сотрудники переднего экрана должны подтвердить, что они смогут использовать Teams, если они не в запланированной смене.  

## <a name="scenario"></a>Сценарий

Вот пример того, как ваша организация может управлять доступом на основе смен.

У вас есть сотрудники, которые работают в вашей организации только в течение нескольких часов, запланированных и утвержденных руководителем. Им не следует платить за время, затраченное на работу вне запланированной смены, включая использование Teams приложения. Вы настроили настраиваемое сообщение "Ваше время в Teams при выходе из смены не будет учитываться в качестве часов оплаты", которое отображается при попытке сотрудников, не работающих с телефоном, обращаться к Teams при выходе из смены. Если они будут использовать Teams, то смогут нажать кнопку Я **принимаю,** чтобы понять, что за это время они не будут оплачены.

В вашей организации также есть информационные работники, которые получают зарплату и не работают в смену. Информационные работники настраивают использование стандартных состояния присутствия в Teams при одновременном предоставлении сотрудникам сменного присутствия.

## <a name="shift-based-presence-states"></a>Состояния присутствия на основе смены

Ниже перейти к состояниям присутствия с учетом смены.

|Настроено в приложении |Настроено пользователем  |Дополнительные сведения  |
|---------|---------|---------|
|![Сплошная зеленая метка, которая означает В сдвиге.](../../media/flw-presence-on-shift.png) На смене     |         |Автоматическое настройка в начале смены         |
|![Серый кружок с x, означает Отключение смены](../../media/flw-presence-off-shift.png) Отключена смена     |         |Автоматическое изменение в конце смены         |
|![Сплошной красный круг, который означает Занят.](../../media/flw-presence-busy.png) Занят(а)      | ![Сплошной красный кружок означает "Занят(а)"](../../media/flw-presence-busy.png) Занят(а)         |Настроить автоматически. Можно также вручную настроить, когда сотрудник в режиме смены.|

## <a name="off-shift-access-to-teams"></a>Отключение shift access для Teams

Эта функция позволяет управлять доступом к учетным Teams, когда сотрудники, работающие в переднем телефоне, отключались от смены. Можно настроить отображение Teams для сотрудников, работающих с передней линией, если они работают с Teams при выходе из смены. Перед использованием  этого сообщения сотрудники, работающие с frontline, должны нажать кнопку Я принимаю, чтобы подтвердить Teams.

Вы можете использовать сообщение по умолчанию, выбрать один из стандартных сообщений или настроить отображение нужного текста. Сообщение по умолчанию:

![Снимок экрана: сообщение по умолчанию.](../../media/shifts-presence-message.png)

Вы также можете настроить частоту отображения сообщения и установить льготный период между началом первой или последней смены и ограничением доступа к Teams сменам.

## <a name="manage-shift-based-access"></a>Управление доступом на основе смен

Администраторы могут управлять присутствием сотрудников в вашей организации с учетом смены. Управлять этими политиками можно с помощью следующих cmdlets PowerShell:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Используйте New-CsTeamsShiftsPolicy для создания новой политики, задайте нужные параметры политики, а затем используйте Grant-CsTeamsShiftsPolicy для назначения политики пользователям.

Вот некоторые примеры. Подробные сведения о каждом параметре политики и параметре, включая список предопределений сообщений о сменах, которые можно выбрать, см. в описании [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-1"></a>Пример 1

В этом примере мы создадим политику Off Shift Teams Access Default Message. В этой политике включено присутствие с учетом смены, и сообщение по умолчанию отображается каждый раз, когда пользователь, которому назначена эта политика, Teams при выходе из нее. Пользователь может использовать Teams, если принимает сообщение, и период отсрочки между началом первой или последней сменой и ограничением доступа составляет 10 минут.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> С помощью **параметра ShiftNoticeMessageType** можно настроить сообщение, которое вы хотите отобразить. Список предварительно определенных сообщений, которые можно выбрать для этого параметра, см. в списке [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-2"></a>Пример 2 

В этом примере мы создадим политику Off Shift Teams Access Custom Message. В этой политике присутствие на основе смены включено, и пользователь, которому назначена эта политика, будет отображаться пользовательское сообщение, которое будет Teams при выходе из нее. Пользователь может использовать Teams при выходе из смены, если принимает сообщение, и период отсрочки между началом первой смены или окончанием последней смены и ограничением доступа составляет 15 минут.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> С помощью **параметра ShiftNoticeMessageType** можно настроить сообщение, которое вы хотите отобразить. Дополнительные информации см. [в new-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>Пример 3

В этом примере мы создадим политику Off Shift Teams Access Message1. В этой Teams политике включено присутствие на основе смены, и при каждом выходе из нее пользователю, которому назначена эта политика, отображается следующее предопределированное сообщение.

  "Ваш работодатель не разрешает или не утверждает использование его сети, приложений, систем или инструментов нерабоочными или нерабоочными сотрудниками в нерабоочные часы. Принимая приглашение, вы подтверждаете, что ваше использование Teams смены не разрешено и вы не сможете компенсацию". 

Пользователь может использовать Teams при выходе из смены, если принимает сообщение, и период отсрочки между началом первой смены или окончанием последней смены и ограничением доступа составляет три минуты.  

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