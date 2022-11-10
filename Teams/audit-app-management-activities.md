---
title: Поиск событий управления приложениями в журналах аудита
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 08/24/2022
ms.collection:
- M365-collaboration
search.appverid: MET150
f1keywords: ''
description: Сведения об аудите действий пользователей и администраторов в приложении Teams в организации.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 0fd3feb73705a95e0729cb1819d9f355ce3ef711
ms.sourcegitcommit: 22f66e314e631b3c9262c5c7dc5664472f42971e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/10/2022
ms.locfileid: "68912788"
---
# <a name="audit-logs-of-app-management-activities-and-events"></a>Журналы аудита действий и событий управления приложениями

Аудит Microsoft Purview (стандарт) в Microsoft 365 позволяет искать записи аудита для действий, выполняемых в различных службах Microsoft 365 конечными пользователями и администраторами.

Прежде чем выполнять поиск в службе аудита, выполните следующие предварительные требования.

* [Получите подписку организации и лицензии пользователей](/microsoft-365/compliance/set-up-basic-audit).
* [Включите аудит на портале соответствия требованиям Microsoft Purview](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
* [Назначьте разрешения для поиска в журнале аудита](/microsoft-365/compliance/set-up-basic-audit).

## <a name="search-the-audit-logs-for-app-events-in-teams"></a>Поиск событий приложения в журналах аудита в Teams

Журналы аудита событий приложений в Teams помогают исследовать конкретные действия. Вы можете искать в журналах широкий спектр действий. В следующей таблице перечислены некоторые действия приложения Teams, которые регистрируются в журнале. Кроме того, вы можете выполнять поиск действий, связанных с соединителями, ботами, вкладками и т. д.

| Действие приложения Teams                  | Название действия                | Описание                                              |
|-----------------------------------|------------------------------|:---------------------------------------------------------|
| **Установлено приложение**                 | `AppInstalled`               | Приложение установлено.                                     |
| **Обновлено приложение**                  | `AppUpgraded`                | Приложение обновлено до последней версии в каталоге. |
| **Удалено приложение**               | `AppUninstalled`             | Приложение удалено.                                   |
| **Опубликовано приложение**                 | `AppPublishedToCatalog`      | Приложение добавлено в каталог.                          |
| **Приложение обновлено**                   | `AppUpdatedInCatalog`        | Приложение обновлено в каталоге.                        |
| **Удалено приложение**                   | `AppDeletedFromCatalog`      | Приложение удалено из каталога.                      |
| **Удалены все приложения организации** | `DeletedAllOrganizationApps` | Удалены все приложения организации из каталога.          |

Полный список действий Teams, для которых выполняется аудит, см. в разделе [Действия Teams](audit-log-events.md#teams-activities) и [Смены в действиях Teams](audit-log-events.md#shifts-in-teams-activities).

> [!NOTE]
> События приложений из частных каналов также регистрируются, так как они предназначены для Teams и стандартных каналов.

Используйте средство поиска в журнале аудита на портале соответствия требованиям для поиска записей аудита. Чтобы найти событие приложения в журналах аудита, выполните следующие действия.

1. Войдите на портал соответствия требованиям Microsoft Purview и выберите **Решения** > **[Аудит](https://compliance.microsoft.com/auditlogsearch)**.
1. На странице аудита обновите следующие поля в соответствии со своими требованиями.

   * **Дата и диапазон времени**: выберите дату начала и окончания.
   * **Действия**: введите действия Microsoft Teams. В списке выберите одно или несколько действий приложения. Чтобы быстро найти действия Teams, вы можете выполнить поиск слова в `Teams activities` поле поиска **Действия**.
   * **Файл, папка или сайт**: введите имя файла, URL-адрес или его часть.
   * **Пользователи**: добавьте пользователей, в журнале аудита которых нужно выполнить поиск.

1. Выберите **Поиск**.

   :::image type="content" source="media/compliance-search-teams-activities-trimmed.png" alt-text="Выполните поиск действий Teams на портале соответствия требованиям Microsoft Purview для аудита событий Teams." lightbox="media/compliance-search-teams-activities.png":::

После поиска подписи аудита на портале соответствия требованиям вы можете экспортировать записи аудита в виде CSV-файла. Дополнительные сведения см. в статье [Экспорт, настройка и просмотр журнала аудита](/microsoft-365/compliance/export-view-audit-log-records).

> [!NOTE]
> Когда одно из указанных выше действий выполняется пользователем или администратором, Teams создает и сохраняет запись аудита. При использовании Аудита (стандарт) записи хранятся 90 дней, что означает, что вы можете искать действия, совершенные за последние три месяца.

> [!TIP]
> Если вы хотите создать отчет для каждого пользователя, чтобы узнать, заблокировал или отключил ли пользователь бот, см. статью [Общие сведения о том, кто заблокировал, отключил или удалил бота](/microsoftteams/platform/bots/how-to/conversations/send-proactive-messages?#understand-who-blocked-muted-or-uninstalled-a-bot).

## <a name="related-articles"></a>Статьи по теме

* [Использование журналов аудита для изучения действий установки Microsoft Power Platform](manage-power-platform-apps.md#use-audit-logs-to-investigate-microsoft-power-platform-installation-activity)
* [Поиск подписи аудита на портале соответствия требованиям](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).
* [Обзор Аудита премиум Microsoft Purview](/microsoft-365/compliance/advanced-audit).
* [Включение или отключение аудита](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
