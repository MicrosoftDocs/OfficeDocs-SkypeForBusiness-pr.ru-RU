---
title: Управление владельцами расписания для управления сменами
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Узнайте, как управлять владельцами смен для управления расписанием. Вы можете настроить политику, чтобы сделать участника группы более владельцем расписания.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 702ca0fd5b392755b1966d16024d5ecf10cdacab
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58627541"
---
# <a name="schedule-owner-for-shift-management"></a>Запланировать владельца для управления сменами

## <a name="overview"></a>Обзор

Владелец расписания — это функция, которая позволяет повысить разрешения участника группы до владельца расписания, не назначить сотрудника владельцем команды. Это означает, что сотруднику разрешено управлять расписанием группы, не изменяя другие свойства команды, такие как обновление, изменение и удаление каналов группы.

Что может делать пользователь с разрешениями владельца календарного плана?

- Создание, изменение и публикация расписаний для управления сменами группы.
- Просмотр и утверждение запросов на смену, включая запросы на обмен сменами и открытые смены.
- Управляйте настройками в сменах, чтобы включить определенные функции для команды.
- Просматривайте и изменяйте расшифлет группы для обработки заработной платы сотрудников.

## <a name="why-schedule-owner"></a>Зачем нужно планировать владельца?

Без функции "Владелец расписания" бизнес-функции, которые ежедневно выполняются, могут быть нарушены. Хотя владелец команды помогает управлять командой, он может не обязательно быть лицом, отвечающим за ежедневное планирование. В этом случае передача ответственности за управление расписанием другому участнику упрощает повседневную работу в группе и устраняет путаницу с двумя участниками группы с одинаковыми привилегиями доступа.

## <a name="scenario"></a>Сценарий

Ниже показан пример использования функции "Владелец расписания" в вашей организации.

Вы работаете в крупной организации, где руководители отделов сообщают напрямую руководителю магазина. Руководитель магазина имеет больше полномочий в вашей компании и является владельцем команды в shifts. С другой стороны, руководители отделов добавляются в смены только в качестве участников команды. Руководители магазинов имеют больше руководителей высшего звена, чем руководители отделов, но руководителям отделов имеет смысл работать с расписаниями сотрудников своей группы.

*Без владельца расписания* руководители отделов должны иметь те же права, что и владелец команды. Недавно руководители отделов перемещали информацию и меняли названия каналов, что вызывал сложности с работой руководителя магазина. Руководитель магазина хочет, чтобы руководители отделов могли упорядоизировать свои расписания, но не хотели бы, чтобы они могли изменять что-либо еще в команде, кроме Смены.

*Владелец расписания* предоставляет руководителям отделов права на планирование без каких-либо других прав владельца группы.

## <a name="manage-schedule-ownership"></a>Управление владением расписанием

Администраторы могут управлять управлением расписаниями в организации с помощью политик. Управлять этими политиками можно с помощью следующих cmdlets PowerShell:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy?view=teams-ps)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy?view=teams-ps)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy?view=teams-ps)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy?view=teams-ps)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy?view=teams-ps)

### <a name="example-1"></a>Пример 1

Здесь мы создадим политику ScheduleOwnerPolicy с включенной функцией "Владелец расписания".

```powershell
New-CsTeamsShiftsPolicy –Identity ScheduleOwnerPolicy  -EnableScheduleOwnerPermissions $true -AccessType UnrestrictedAccess_TeamsApp
```

### <a name="example-2"></a>Пример 2

В этом примере мы назначим политику ScheduleOwnerPolicy пользователю с именем remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName ScheduleOwnerPolicy
```

## <a name="related-articles"></a>Статьи по теме

- [Управление приложением "Смены" для организации в Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Управление доступом на основе смен для сотрудников, работающих с телефоном, в Teams](manage-shift-based-access-flw.md) 
