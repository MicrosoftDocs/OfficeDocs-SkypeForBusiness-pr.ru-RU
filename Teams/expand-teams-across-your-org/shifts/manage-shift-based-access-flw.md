---
title: Управление доступом сотрудников без сети в Teams с учетом смены
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Узнайте, как управлять доступом с учетом смены в Teams для сотрудников без компьютеров в вашей организации.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b73fe9b3c4b39e7d3fa7b31427f563c47e5a737
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823019"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a>Управление доступом сотрудников без сети в Teams с учетом смены

> [!IMPORTANT]
> С 30 июня 2020 г. больше не будет microsoft StaffHub. Мы строите возможности StaffHub в Microsoft Teams. На сегодняшний день в Teams есть приложение "Смены" для управления расписанием, а со временем будут отключаться дополнительные возможности. StaffHub перестал работать для всех пользователей 30 июня 2020 г. Всем, кто пытается открыть StaffHub, отображается сообщение с командой для скачивания Teams. Подробнее см. в том, [что служба Microsoft StaffHub больше не была установлена.](microsoft-staffhub-to-be-retired.md)  

## <a name="overview"></a>Обзор

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Присутствие в Microsoft Teams указывает на текущую доступность и статус пользователя для других пользователей. Присутствие сотрудников без работы часто менее предсказуемо, чем у других сотрудников, так как их рабочие часы обычно не одинаковы каждый день. Как администратор вы можете настроить Teams, чтобы показывать сотрудникам организации состояния присутствия с учетом смены, чтобы они могли указать, когда они включались и отключались.

Эти состояния присутствия на основе смены, сплошная зеленая метка, которая указывает на наличие смены при смене, серый кружок с x, указывает на отключение смены и сплошной красный кружок, что означает, что "Занят" не зависит от набора состояния присутствия по умолчанию в &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; Teams. [](../../presence-admins.md) С помощью этих двух наборов состояния присутствия вы можете настраивать разные функции для пользователей в организации в зависимости от их роли.

С помощью shift-based access вы можете управлять доступом к Teams, когда сотрудники без связи отключены. Например, можно настроить Teams таким образом, чтобы вы могли отобразить сообщение о том, что сотрудники, не работающие с первой телефоном, должны подтвердить, что они смогут использовать Teams, если они не назначены на запланированную смену.  

## <a name="scenario"></a>Сценарий

Вот пример того, как организация может управлять доступом на основе смен.

У вас есть сотрудники без компьютеров в вашей организации, которые должны платить только за часы, которые они работают в смену, запланированную и утвержденной руководителем. За работу вне запланированной смены, включая использование приложения Teams, не следует платить за время, проведенное за пределами запланированной смены. Вы настроили настраиваемое сообщение "Ваше время в Teams при отключаемых сменах не учитывается в часах оплаты", которое отображается, когда сотрудники без компьютеров пытаются получить доступ к Teams, когда они не работают в смену. Если они будут использовать Teams, они нажимают кнопку **"Я принимаю"** с пониманием, что на этот раз они не будут платить.

В вашей организации также есть информационные работники, которые получают зарплату и не работают сменами. Информационные работники могут использовать стандартные состояния присутствия в Teams, одновременно предоставляя сотрудникам без компьютеров смену присутствия.

## <a name="shift-based-presence-states"></a>Состояния присутствия на основе смены

Вот состояния присутствия с учетом смены.

|Настроено в приложении |Настроено пользователем  |Дополнительные сведения  |
|---------|---------|---------|
|![Сплошная зеленая метка с отметкой "В сдвиге"](../../media/flw-presence-on-shift.png) В смене     |         |Настройка автоматически в начале смены         |
|![Серый кружок с x, обозначение "Отключена"](../../media/flw-presence-off-shift.png) Отключенная смена     |         |Автоматическое настройка в конце смены         |
|![Сплошной красный кружок означает "Занят(а)"](../../media/flw-presence-busy.png) Занят(а)      | ![Сплошной красный кружок означает "Занят(а)"](../../media/flw-presence-busy.png) Занят(а)         |За устанавливается автоматически. Можно также настроить вручную, когда сотрудник без телефонной работы находится в смене.|

## <a name="off-shift-access-to-teams"></a>Отключение доступа к Teams при смене

Эта функция позволяет управлять доступом к Teams, когда сотрудники без первого доступа отключаются от смены. Вы можете настроить в Teams отображение сообщения для сотрудников без телефонов, если они будут получать доступ к Teams во время смены. Сотрудники, работающие без телефонии, должны нажать **кнопку "Я принимаю",** чтобы подтвердить сообщение, прежде чем они смогут использовать Teams.

Вы можете использовать сообщение по умолчанию, выбрать один из наборов стандартных сообщений или настроить отображение нужного текста. Вот сообщение по умолчанию:

![Снимок экрана: сообщение по умолчанию](../../media/shifts-presence-message.png)

Вы также можете настроить частоту отображения сообщения и установить льготный период между началом первой и последней смены и ограничением доступа к Teams.

## <a name="manage-shift-based-access"></a>Управление доступом на основе смен

Администраторы могут управлять присутствием сотрудников без компьютеров в организации с помощью политик. Для управления этими политиками можно использовать следующие cmdlets PowerShell:

- [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

Используйте New-CsTeamsShiftsPolicy для создания новой политики, настройки нужных параметров политики, а затем используйте Grant-CsTeamsShiftsPolicy для назначения политики пользователям.

Вот несколько примеров. Подробные сведения о каждом параметре политики и параметре, включая список предопределений сообщений о сменах, которые можно выбрать, см. в описании [New-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-1"></a>Пример 1

В этом примере мы создадим политику off Shift Teams Access Default Message. В этой политике присутствие на основе смены включено, и сообщение по умолчанию отображается каждый раз, когда пользователь, которому назначена эта политика, получает доступ к Teams, когда он не в сети. Пользователь может использовать Teams при смене без смены, если принимает сообщение, и период отсрочки между первым началом и окончанием последней смены и ограничением доступа составляет 10 минут.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> С помощью **параметра ShiftNoticeMessageType** можно настроить сообщение, которое вы хотите отобразить. Список сообщений, которые можно выбрать для этого параметра, можно найти в [new-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-2"></a>Пример 2 

В этом примере мы создадим политику Off Shift Teams Access Custom Message. В этой политике присутствие на основе смены включено, и пользователь, которому назначена эта политика, получает доступ к Teams каждый раз при смене. Пользователь может использовать Teams, если он принимает сообщение, и период отсрочки между первым началом и окончанием последней смены и ограничением доступа составляет 15 минут.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> С помощью **параметра ShiftNoticeMessageType** можно настроить сообщение, которое вы хотите отобразить. Подробнее см. в [теме New-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>Пример 3

В этом примере мы создали политику Off Shift Teams Access Message1. В этой политике включено присутствие на основе смены, и следующее предопределение отображается каждый раз, когда пользователь, которому назначена эта политика, получает доступ к Teams при смене.

  "Ваш работодателей не разрешает или не утверждает использование его сети, приложений, систем или инструментов нерабоочными или почасовой работой сотрудников в нерабо рабочее время. Принимая приглашение, вы признаете, что ваше использование Teams во время смены не уполномочено и вы не можете быть возмещены компенсацию". 

Пользователь может использовать Teams, если он принимает сообщение, и период отсрочки между первым началом и последней сменой и ограничением доступа составляет три минуты.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> С помощью **параметра ShiftNoticeMessageType** можно настроить сообщение, которое вы хотите отобразить. Список сообщений, которые можно выбрать для этого параметра, можно найти в [new-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-4"></a>Пример 4

В этом примере мы назначаем политику Off Shift Teams Access Custom Message пользователю с именем remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Статьи по теме

- [Управление приложением "Смены" для организации в Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Обзор PowerShell в Teams](../../teams-powershell-overview.md)
