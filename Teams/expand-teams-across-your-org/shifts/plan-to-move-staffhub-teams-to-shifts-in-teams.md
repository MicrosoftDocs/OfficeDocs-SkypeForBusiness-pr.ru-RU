---
title: Планирование перемещения StaffHubных групп в смену
author: LanaChin
ms.author: v-lanac
ms.reviewer: gumariam,aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Получите рекомендации по планированию перемещения StaffHub Teams на смену в Microsoft Teams.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 41fd33c384bf6f91ae760d539e18ea7ee74a8503
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "43139588"
---
# <a name="plan-to-move-your-staffhub-teams-to-shifts-in-microsoft-teams"></a>Планирование перемещения StaffHub Teams на смену в Microsoft Teams

> [!IMPORTANT]
> Вступление в силу 31 декабря 2019 г. Корпорация Microsoft StaffHub будет прекращена. Мы создаем возможности StaffHub в Microsoft Teams. Сегодня команды включают в себя приложение смен для управления планированием и дополнительные возможности, которые будут вычислены с течением времени. StaffHub перестанет работать для всех пользователей 31 декабря 2019 г. Каждый, кто пытается открыть StaffHub, будет показывать сообщение, направленное на загрузку групп. Дополнительные сведения можно найти в [статье Microsoft StaffHub](microsoft-staffhub-to-be-retired.md). 

Переход с StaffHub на Teams начнется, когда вы начнете планирование изменения. Для обеспечения успеха перемещения в Teams мы создали образец временной шкалы, демонстрирующий типичный план перехода. Пример структуры временной шкалы планируют действия для подготовки к перемещению и переход от StaffHub Teams Организации к Teams.

Используйте временную шкалу как руководство по планированию перехода с StaffHub на Teams и их настройки в соответствии с потребностями Организации. Убедитесь, что вы просматриваете ресурсы, связанные с шагами на временной шкале.

## <a name="prepare-to-move-your-staffhub-teams-to-teams"></a>Подготовка к перемещению StaffHub Teams в Teams

|Шаг |Рекомендации  |Центр |
|---------|---------|---------|
|1    |Подготовка и определение заинтересованных лиц         |         |
|2     |Ознакомьтесь с документацией по переходу с StaffHub на команды Teams и Teams         |[StaffHub на пенсию](microsoft-staffhub-to-be-retired.md)<br><br>[Перемещение StaffHubных групп в смену в Teams](move-staffhub-teams-to-shifts-in-teams.md)<br><br>[Начало работы с Teams](../../get-started-with-teams-quick-start.md)         |
|3    |Включение групп Office 365 для Организации        |[Группы и команды Office 365](../../Office-365-groups.md)      |
|4    |Убедитесь в том, что необходимые условия выполнены         |[Проверка соответствия требованиям](move-staffhub-teams-to-shifts-in-teams.md#check-that-prerequisites-are-met)       |
|5   |Назначение лицензий Teams StaffHub пользователям в Организации|[Назначение лицензий Teams](move-staffhub-teams-to-shifts-in-teams.md#assign-teams-licenses)<br><br>[Управление доступом пользователей к Teams](../../user-access.md)      |
|6    |Установка модуля StaffHub PowerShell        |[Установка модуля StaffHub PowerShell](install-the-staffhub-powershell-module.md)        |
|7     |Определение временной шкалы и определение пользователей StaffHub для перехода в Teams       |[Запуск отчета для отображения активного использования StaffHub](run-report-to-show-staffhub-usage.md) |
|No8     |Определите пользователей StaffHub, у которых нет учетной записи Azure AD (она отображается в StaffHub) и свяжите ее с учетной записью.     |[Связывание учетной записи Azure AD с участниками группы StaffHub, у которых нет одной](move-staffhub-teams-to-shifts-in-teams.md#link-an-azure-ad-account-for-staffhub-team-members-who-dont-have-one)        |
|@    |Создание обучающего содержимого для пользователей, адаптированных для Организации         |[Подготовка плана готовности пользователя для Teams](../../upgrade-user-readiness.md)     |
|5-10    |Взаимодействие с пользователями StaffHub о переходе на смену в Teams         |[Пример взаимодействия пользователей с электронной почтой в StaffHub в Teams](staffhub-to-teams-email-template.md)         |
|11     |Установка клиентов Teams         |[Получите клиенты для Teams](../../get-clients.md) |
|12    |Назначение пользователям политики настройки приложения FirstLineWorker (или создание и назначение настраиваемой политики настройки приложения) для закрепления приложения "Смена" для клиентов Teams  |[Назначение пользователям политики настройки приложения FirstlineWorker](move-staffhub-teams-to-shifts-in-teams.md#assign-the-firstlineworker-app-setup-policy-to-users)         |
|рис     |Обучение пользователей по использованию смен и команд         |[Встроенные пользователи в Teams](move-staffhub-teams-to-shifts-in-teams.md#onboard-users-to-teams)<br><br>[Справочная документация по сменам](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b)<br><br>[Справочная документация для Teams](https://support.office.com/teams)<br><br>[Обучающие видео для Teams](https://support.office.com/article/microsoft-teams-video-training-4f108e54-240b-4351-8084-b1089f0d21d7)       |
|14     |Ознакомьтесь со списком StaffHub Teams, чтобы убедиться в том, что все пользователи в этих группах должны переноситься в Teams. Удаление пользователей, которые не должны быть в расписании. |         |

## <a name="move-your-organizations-staffhub-teams-to-teams"></a>Перемещение групп StaffHub Организации в Teams

|Шаг |Рекомендации |Центр  |
|---------|---------|---------|
|1  |Определение пилотной команды и перемещение одной команды          |[Перемещение команды StaffHub](move-staffhub-teams-to-shifts-in-teams.md#move-a-staffhub-team)          |
|2    |Проверка пилотной команды и определение проблем с перемещением. Обновите учебную документацию по мере необходимости.         |         |
|3     |Определение дополнительных пилотных групп и переход от пяти до десяти групп         |[Перемещение StaffHubных групп](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|4     |Определение остающихся StaffHubных команд и их перемещение в поэтапной методике         |[Перемещение StaffHubных групп](move-staffhub-teams-to-shifts-in-teams.md#go-beyond-your-pilot-and-move-all-staffhub-teams)         |
|5     |Предоставление поддержки смен и команд         |         |
|6     |Если включена автоматическая смена пароля, запустите отчет для поддержки проблем входа в Teams.       |[Запуск отчета для самостоятельной настройки сброса пароля](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-reporting)        |
