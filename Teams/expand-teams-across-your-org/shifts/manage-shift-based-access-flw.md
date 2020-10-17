---
title: Управление доступом на основе смены для Firstline работников в Teams
author: LanaChin
ms.author: v-lanac
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Сведения о том, как управлять доступом на основе смены в Teams для Firstline работников в Организации.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9ec470422e402da07171bef627d1592c73d6c12f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514136"
---
# <a name="manage-shift-based-access-for-firstline-workers-in-teams"></a>Управление доступом на основе смены для Firstline работников в Teams

> [!IMPORTANT]
> Действующий 30 июня 2020 г. Корпорация Microsoft StaffHub устарела. Мы создаем возможности StaffHub в Microsoft Teams. Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени. StaffHub перестает работать для всех пользователей 30 июня 2020 г. Каждый, кто пытается открыть StaffHub, показывает сообщение, направленное на загрузку групп. Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md)устарела.  

## <a name="overview"></a>Обзор

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Присутствие в Microsoft Teams показывает текущее состояние и доступность пользователя для других пользователей. Присутствие Firstline работников часто менее предсказуемо, чем другие сотрудники, как и в случае с другими сотрудниками, как правило, не один и тот же рабочий день. Администраторы могут настроить в Teams набор состояний присутствия, основанных на сменах, для сотрудников Firstline в вашей организации, чтобы указать, когда они будут включены и выключены.

Это состояние присутствия, основанное на сдвиге, — сплошная зеленая галочка, обозначающая смещение на смене &mdash; ![ ](../../media/flw-presence-on-shift.png) **On shift**, ![ серый круг с крестиком, обозначает отключение смещения ](../../media/flw-presence-off-shift.png) **Off shift**, ![ сплошного красного круга, указывает на то, что занятая ](../../media/flw-presence-busy.png) **Busy** &mdash; работа отделена от [набора состояний присутствия по умолчанию](../../presence-admins.md) в Teams. С помощью этих двух наборов состояний присутствия можно настроить различные возможности для пользователей в вашей организации в зависимости от их роли.

С помощью смена доступа вы можете управлять доступом к Teams, когда Firstline работники отключаются от смены. Например, можно настроить отображение сообщения, которое сотрудники Firstline, должны подтвердить, прежде чем они смогут использовать команды, если они не запланированы на смену.  

## <a name="scenario"></a>Сценарий

Вот пример того, как ваша организация может управлять доступом на основе смены.

У вас есть работники Firstline в вашей организации, которые должны быть оплачены только за часы, которые они работают на смене, запланированной и утвержденной руководителем. Они не должны оплачиваться за время, затраченное на работу за пределами запланированного сдвига, в том числе с помощью приложения Teams. Вы настроили настраиваемое сообщение, в котором указано, что время, в течение которого в Teams On Off, не подсчитывается на счет в расчетные часы, которое отображается, когда Firstline работники пытаются получить доступ к командам после ее отключения. Если вы решите использовать Teams, они нажимают, что они не будут оплачиваться **в течение** этого времени.

Кроме того, у вас есть сотрудники вашей организации, которые загружаются и не работают с сменами. Вы настраиваете сотрудников данных для использования состояний присутствия по умолчанию в Teams при предоставлении сотрудникам Firstline на основе смены.

## <a name="shift-based-presence-states"></a>Состояния присутствия, основанные на сменах

Ниже указаны состояния присутствия, основанные на сменах.

|Настроено в приложении |Настроено пользователем  |Дополнительные сведения  |
|---------|---------|---------|
|![Сплошной зеленый галочка, обозначается нажатием клавиши Shift](../../media/flw-presence-on-shift.png) На смену     |         |Автоматическая установка в начале смены         |
|![Серый круг с крестиком означает, что клавиша Shift нажата](../../media/flw-presence-off-shift.png) Выключить смену     |         |Автоматическая установка по завершении смены         |
|![Сплошной красный кружок означает "Занят(а)"](../../media/flw-presence-busy.png) Занят(а)      | ![Сплошной красный кружок означает "Занят(а)"](../../media/flw-presence-busy.png) Занят(а)         |Задается автоматически. Также можно задать вручную при смене рабочего процесса FIRSTLINE.|

## <a name="off-shift-access-to-teams"></a>Отключение доступа на смену в Teams

Эта функция позволяет управлять доступом к Teams, когда Firstline работники отключили смену. Вы можете настроить в Teams отображение сообщения для Firstline работников, если они обращаются к Teams при выключенном смещении. Firstline работники должны нажать кнопку " **принять** ", чтобы подтвердить сообщение, прежде чем они смогут использовать Teams.

Вы можете использовать сообщение по умолчанию, выбрать набор предварительно определенных сообщений или настроить сообщение для отображения любого нужного текста. Вот сообщение по умолчанию:

![Снимок экрана: сообщение по умолчанию](../../media/shifts-presence-message.png)

Вы также можете задать частоту отображения сообщения и задать льготный период между завершением первой смены и окончанием последнего смены и при ограниченном доступе к Teams.

## <a name="manage-shift-based-access"></a>Управление доступом на основе смен

Администраторы используют политики для управления состоянием присутствия, основанным на сменах сотрудников Firstline в Организации. Управление этими политиками осуществляется с помощью следующих командлетов PowerShell:

- [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

Используйте командлет New-CsTeamsShiftsPolicy для создания новой политики, задайте нужные параметры политики, а затем с помощью командлета Grant-CsTeamsShiftsPolicy назначьте политику пользователям.

Вот несколько примеров. Подробные сведения о каждом параметре политики и параметре, включая список стандартных сообщений с сменами, которые вы можете выбрать, можно найти в статьях [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Пример 1

В этом примере мы создаем новую политику с именем Off, доступную по умолчанию для команды Shift. В этой политике состояние, основанное на смене, включено, и сообщение по умолчанию отображается каждый раз, когда пользователь, которому назначена эта политика, получает доступ к командам, если они не были смещены. Пользователь может использовать Teams при отключенной смене, если он примет сообщение, и льготный период между моментом начала или последнего сдвига, а также в том случае, если доступ ограничен 10 минутами.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> С помощью параметра **ShiftNoticeMessageType** задайте сообщение, которое вы хотите отобразить. Чтобы просмотреть список предварительно определенных сообщений, которые можно выбрать для этого параметра, ознакомьтесь с разрешениями [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Пример 2 

В этом примере мы создаем новую политику с именем Off, настраиваемым сообщением Teams Access. В этой политике состояние, основанное на смене, включено, а настраиваемое сообщение выводится каждый раз, когда пользователь, которому назначена эта политика, получает доступ к Teams при отключенной смене. Пользователь может использовать Teams при отключенной смене, если он примет сообщение, и льготный период между моментом, когда начало первой смены начинается или заканчивается, а также в том случае, если доступ ограничен 15 минутами.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> С помощью параметра **ShiftNoticeMessageType** задайте сообщение, которое вы хотите отобразить. Дополнительные сведения можно найти в статье [Создание и CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Пример 3

В этом примере мы создаем новую политику с именем "message1", а затем — команды "Shift Access". В этой политике состояние, основанное на смене, включено, а следующее предопределенное сообщение отображается каждый раз, когда пользователь, которому назначена эта политика, получает доступ к Teams при отключенной смене.

  "Ваш работодатель не авторизует и не утверждает использование своей сети, приложений, систем или средств за пределами, не являющимися сотрудниками, а также не используй часы рабочих часов. Принимая это согласие, вы подтверждаете, что использование команд при выключенном смещении не авторизовано и вы не будете компенсировать " 

Пользователь может использовать Teams при отключенной смене, если он примет сообщение, и льготный период между моментом, когда начало первой смены начинается или заканчивается, а также в том случае, если доступ ограничен 3 минутами.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> С помощью параметра **ShiftNoticeMessageType** задайте сообщение, которое вы хотите отобразить. Чтобы просмотреть список предварительно определенных сообщений, которые можно выбрать для этого параметра, ознакомьтесь с разрешениями [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-4"></a>Пример 4

В этом примере мы назначаем политику с именем Откл., настраиваемое сообщение Teams Access пользователю с именем remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Статьи по теме

- [Управление приложением "Смены" для организации в Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Обзор PowerShell в Teams](../../teams-powershell-overview.md)
