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
- Microsoft Cloud for Retail
description: Узнайте, как управлять владельцами смен для управления расписанием. Вы можете настроить политику, чтобы сделать участника группы более владельцем расписания.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
- microsoftcloud-retail
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 12cf33f193e7f1d1a976e5cde8612df19108cb69
ms.sourcegitcommit: 159399f2325af644c20551925c1fa34bf76aad43
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/01/2022
ms.locfileid: "62288637"
---
# <a name="schedule-owner-for-shift-management"></a>Расписание владельца для управления сменами

## <a name="overview"></a>Обзор

С помощью функции "Владелец расписания" можно повысить разрешения участника группы, чтобы он могли управлять расписаниями, не сделав сотрудника владельцем команды. С разрешениями владельца календарного плана сотрудник может управлять расписанием своей команды, не изменяя другие свойства команды, такие как обновление, изменение и удаление каналов группы.

Что может делать пользователь с разрешениями владельца календарного плана?

- Создавайте, редактируете и публикуйте расписания для управления сменами группы.
- Просмотр и утверждение запросов на смену, включая запросы на обмен сменами и открытые смены.
- Управляйте настройками в сменах, чтобы включить определенные функции для команды.
- Просматривайте и изменяйте рас времени своей группы для обработки заработной платы сотрудников.

## <a name="why-schedule-owner"></a>Зачем нужно планировать владельца?

Без функции "Владелец расписания" бизнес-функции, которые ежедневно выполняются, могут быть нарушены. Хотя владелец команды помогает управлять командой, он может не обязательно быть лицом, отвечающим за ежедневное планирование. В этом случае передача ответственности только за управление расписанием другому участнику группы упрощает повседневную работу в группе и устраняет путаницу с двумя членами группы с одинаковыми привилегиями доступа.

## <a name="scenario"></a>Сценарий

Ниже показан пример использования функции "Владелец расписания" в вашей организации.

Вы работаете в крупной организации, где руководители отделов сообщают напрямую руководителю магазина. Руководитель магазина имеет больше полномочий в вашей компании и является владельцем команды в shifts. С другой стороны, руководители отделов добавляются в смены только в качестве членов команды. Руководители магазинов имеют большее количество сотрудников, чем руководители отделов, но руководители отделов могут лучше управлять расписанием сотрудников своей группы.

*Без владельца расписания* руководители отделов должны иметь те же права, что и владелец команды. В последнее время руководители отделов перемещали информацию и меняли названия каналов, что вызывал сложности с работой руководителя магазина. Руководитель магазина хочет, чтобы руководители отделов могли упорядоизировать свои расписания, но не хотели бы, чтобы они могли изменять что-либо еще в команде, кроме смен.

*Владелец расписания может* назначить руководителям отделов права на планирование без каких-либо других прав владельца группы.

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
