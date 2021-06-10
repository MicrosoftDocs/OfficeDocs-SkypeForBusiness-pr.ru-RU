---
title: Обновление приложений в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: v-tbasra
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как обновить приложения в Microsoft Teams.
ms.openlocfilehash: b39b831b644b19038b8f4574acf3e5bc5c50d73c
ms.sourcegitcommit: 40f76bc6b5e304faea8516a78f8576ba1cdb7f7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/12/2021
ms.locfileid: "52337833"
---
# <a name="update-apps-in-microsoft-teams"></a><span data-ttu-id="c739a-103">Обновление приложений в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c739a-103">Update apps in Microsoft Teams</span></span>

<span data-ttu-id="c739a-104">В большинстве случаев после публикации обновления приложения для пользователей автоматически появляется новая версия.</span><span class="sxs-lookup"><span data-stu-id="c739a-104">In most cases, after app developers publish an app update, the new version automatically appears for users.</span></span> <span data-ttu-id="c739a-105">Однако существуют некоторые обновления манифеста <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams,</a> которые требуют принятия пользователем:</span><span class="sxs-lookup"><span data-stu-id="c739a-105">However, there are some updates to the <a href="/microsoftteams/platform/resources/schema/manifest-schema" target="_blank">Microsoft Teams manifest</a> that require user acceptance to complete:</span></span>

* <span data-ttu-id="c739a-106">Бот был добавлен или удален</span><span class="sxs-lookup"><span data-stu-id="c739a-106">A bot was added or removed</span></span>
* <span data-ttu-id="c739a-107">Изменено свойство botId существующего бота</span><span class="sxs-lookup"><span data-stu-id="c739a-107">An existing bot's "botId" property changed</span></span>
* <span data-ttu-id="c739a-108">Изменено свойство isNotificationOnly существующего бота</span><span class="sxs-lookup"><span data-stu-id="c739a-108">An existing bot's "isNotificationOnly" property changed</span></span>
* <span data-ttu-id="c739a-109">Изменено свойство бота "supportsFiles"</span><span class="sxs-lookup"><span data-stu-id="c739a-109">The bot's "supportsFiles" property changed</span></span>
* <span data-ttu-id="c739a-110">Добавлено или удалено расширение для сообщений</span><span class="sxs-lookup"><span data-stu-id="c739a-110">A messaging extension was added or removed</span></span>
* <span data-ttu-id="c739a-111">Добавлен новый соединител</span><span class="sxs-lookup"><span data-stu-id="c739a-111">A new connector was added</span></span>
* <span data-ttu-id="c739a-112">Добавлена новая статическая вкладка</span><span class="sxs-lookup"><span data-stu-id="c739a-112">A new static tab was added</span></span>
* <span data-ttu-id="c739a-113">Добавлена новая настраиваемая вкладка</span><span class="sxs-lookup"><span data-stu-id="c739a-113">A new configurable tab was added</span></span>
* <span data-ttu-id="c739a-114">Свойства внутри "webApplicationInfo" изменены</span><span class="sxs-lookup"><span data-stu-id="c739a-114">Properties inside "webApplicationInfo" changed</span></span>

![Доступна новая версия](media/manage-your-custom-apps-update1.png)

![Параметр обновления для приложения](media/manage-your-custom-apps-update2.png)

> [!NOTE] 
> <span data-ttu-id="c739a-117">Процесс обновления применяется ко всем обновлениям приложений Майкрософт, пользовательских приложений и сторонних приложений.</span><span class="sxs-lookup"><span data-stu-id="c739a-117">The update process applies to all app updates for Microsoft apps, custom apps, and third-party apps.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="c739a-118">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c739a-118">Related topics</span></span>

[<span data-ttu-id="c739a-119">Управление приложениями</span><span class="sxs-lookup"><span data-stu-id="c739a-119">Manage apps</span></span>](manage-apps.md)