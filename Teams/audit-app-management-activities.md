---
title: Поиск событий управления приложениями в журналах аудита
author: ashishguptaiitb
ms.author: guptaashish
manager: prkosh
ms.topic: article
ms.service: msteams
ms.subservice: teams-apps
audience: admin
ms.date: 12/02/2022
ms.collection:
- M365-collaboration
search.appverid: MET150
f1keywords: ''
description: Сведения об аудите действий пользователей и администраторов в приложении Teams в организации.
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.openlocfilehash: 5aee5bf00d486586b4bc8e9583504be5e4a9b922
ms.sourcegitcommit: 54c691bd34980a47a5ebf58555529a618a8cada7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2022
ms.locfileid: "69251882"
---
# <a name="search-audit-logs-for-app-management-activities-and-events"></a>Поиск журналов аудита для действий и событий управления приложениями

Аудит Microsoft Purview (стандарт) в Microsoft 365 позволяет искать записи аудита для действий, выполняемых в различных службах Microsoft 365 конечными пользователями и администраторами.

Прежде чем выполнять поиск в записях аудита, убедитесь, что выполнены следующие предварительные требования:

* [Получите подписку организации и лицензирование пользователей](/microsoft-365/compliance/set-up-basic-audit).
* [Включите аудит на портале соответствия требованиям Microsoft Purview](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
* [Назначьте разрешения для поиска в журнале аудита](/microsoft-365/compliance/set-up-basic-audit).

## <a name="search-the-audit-logs-for-app-events-in-teams"></a>Поиск событий приложения в журналах аудита в Teams

Журналы аудита для событий приложений в Teams помогают исследовать конкретные действия, связанные с управлением приложениями администраторами. Хотя вы можете искать в журналах широкий спектр действий, в следующей таблице перечислены некоторые такие действия, которые регистрируются в журнале.

| Действие приложения Teams | Имя действия на портале | Описание  |
|-------|-------|:-------|
| **Установлено приложение**                 | `AppInstalled`               | Приложение устанавливается или добавляется в клиент Teams. |
| **Обновлено приложение**                  | `AppUpgraded`                | Приложение обновлено до последней версии в каталоге. |
| **Удалено приложение**               | `AppUninstalled`             | Приложение удаляется или удаляется из клиента Teams.                                   |
| **Опубликовано приложение**                 | `AppPublishedToCatalog`      | Приложение добавлено в каталог.                          |
| **Приложение обновлено**                   | `AppUpdatedInCatalog`        | Приложение обновлено в каталоге.                        |
| **Удалено приложение**                   | `AppDeletedFromCatalog`      | Приложение удалено из каталога.                      |
| **Удалены все приложения организации** | `DeletedAllOrganizationApps` | Удалены все приложения организации из каталога.          |

<!--- organization apps = custom or 3p --->

Полный список действий Teams, для которых выполняется аудит, см. в разделе [Действия Teams](audit-log-events.md#teams-activities) и [Смены в действиях Teams](audit-log-events.md#shifts-in-teams-activities).

> [!NOTE]
> События приложений из частных каналов также регистрируются по мере того, как эти события выполняются в Teams и в стандартных каналах.

Чтобы выполнить поиск в журналах аудита действий приложений Teams, выполните следующие действия.

1. Войдите на портал соответствия требованиям Microsoft Purview и выберите **Решения** > **[Аудит](https://compliance.microsoft.com/auditlogsearch)**.
1. На странице **Аудит** обновите следующие поля при необходимости:

   * **Диапазон даты и времени**. Выберите начальную и конечную даты периода времени, за который вы хотите проверить журналы аудита.
   * **Действия**: введите действия Microsoft Teams. В списке выберите одно или несколько действий приложения. Чтобы быстро найти действия Teams, вы можете выполнить поиск слова в `Teams activities` поле поиска **Действия**.
   * **Файл, папка или сайт**: введите имя файла, URL-адрес или его часть.
   * **Пользователи**: добавьте пользователей, в журнале аудита которых нужно выполнить поиск.

1. Выберите **Поиск**.

   :::image type="content" source="media/compliance-search-teams-activities-trimmed.png" alt-text="Выполните поиск действий Teams на портале соответствия требованиям Microsoft Purview для аудита событий Teams." lightbox="media/compliance-search-teams-activities.png":::

Вы можете экспортировать искомые записи аудита в виде CSV-файла. Дополнительные сведения см. в статье [Экспорт, настройка и просмотр журнала аудита](/microsoft-365/compliance/export-view-audit-log-records).

> [!NOTE]
> Когда одно из указанных выше действий выполняется пользователем или администратором, Teams создает и сохраняет запись аудита. При использовании Аудита (стандарт) записи хранятся 90 дней, что означает, что вы можете искать действия, совершенные за последние три месяца.

> [!TIP]
> Если вы хотите создать отчет для каждого пользователя, чтобы узнать, заблокировал или отключил ли пользователь бот, см. статью [Общие сведения о том, кто заблокировал, отключил или удалил бота](/microsoftteams/platform/bots/how-to/conversations/send-proactive-messages?#understand-who-blocked-muted-or-uninstalled-a-bot).

## <a name="related-articles"></a>Статьи по теме

* [Использование журналов аудита для изучения действий установки Microsoft Power Platform](manage-power-platform-apps.md#use-audit-logs-to-investigate-microsoft-power-platform-installation-activity)
* [Поиск подписи аудита на портале соответствия требованиям](/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance).
* [Обзор Аудита премиум Microsoft Purview](/microsoft-365/compliance/advanced-audit).
* [Включение или отключение аудита](/microsoft-365/compliance/turn-audit-log-search-on-or-off).
