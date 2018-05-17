---
title: Настройка параметров сосуществования
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: bjwhalen
description: Это поможет вам выбрать режиме сосуществования и задайте другие параметры совместной работы.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: add6436d66c088d6ffa14867cc03268cb082f0b3
ms.sourcegitcommit: 265fbdc1a8ac566751e707874656bd6b90de980d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/16/2018
---
# <a name="setting-your-coexistence-settings"></a><span data-ttu-id="be205-103">Настройка параметров сосуществования</span><span class="sxs-lookup"><span data-stu-id="be205-103">Setting your coexistence settings</span></span>


> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<Intro text here>

[<span data-ttu-id="be205-104">Понять сосуществования и обновление режимы для Скайп для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="be205-104">Understand coexistence and upgrade modes for Skype for Business and Teams</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

## <a name="setting-your-upgrade-options-for-your-users"></a><span data-ttu-id="be205-105">Настройка личных параметров обновления для пользователей</span><span class="sxs-lookup"><span data-stu-id="be205-105">Setting your upgrade options for your users</span></span>

<span data-ttu-id="be205-106">![команды логотип 30x30.png](media/teams-logo-30x30.png) **с помощью групп Майкрософт и Скайп по центру администрирования бизнеса**</span><span class="sxs-lookup"><span data-stu-id="be205-106">![teams-logo-30x30.png](media/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="be205-107">В левой области переходов, перейдите в раздел **масштабе организации параметры** > **Обновление группы**.</span><span class="sxs-lookup"><span data-stu-id="be205-107">In the left navigation, go to **Org-wide settings** > **Teams upgrade**.</span></span> 

2. <span data-ttu-id="be205-108">В верхней части страницы **Страница группы обновления** внесите следующие изменения, если они будут работать для вас.</span><span class="sxs-lookup"><span data-stu-id="be205-108">At the top of the **Teams upgrade page** page, make the following changes if they will work for you.</span></span>
- <span data-ttu-id="be205-109">Режим **совместимости**</span><span class="sxs-lookup"><span data-stu-id="be205-109">Set the **Coexistence** mode</span></span>
    - <span data-ttu-id="be205-110">**Острова** — используйте этот параметр, при наличии некоторые пользователи Скайп для бизнеса и некоторые пользователи, использующие группами.</span><span class="sxs-lookup"><span data-stu-id="be205-110">**Islands** - use this setting when you have some users on Skype for Business and some users that use Teams.</span></span>
    - <span data-ttu-id="be205-111">**Скайп для бизнеса только** — используйте этот параметр, если только Скайп для коммерческих пользователей.</span><span class="sxs-lookup"><span data-stu-id="be205-111">**Skype for Business only** - use this setting if you only have Skype for Business users.</span></span>
    - <span data-ttu-id="be205-112">**Только группы** — используйте этот параметр, если только группам пользователей.</span><span class="sxs-lookup"><span data-stu-id="be205-112">**Teams only** - use this setting if you only have Teams users.</span></span>
- <span data-ttu-id="be205-113">Установка **уведомления Скайп для бизнес-пользователи, который групп доступна для обновления.**</span><span class="sxs-lookup"><span data-stu-id="be205-113">Set **Notify Skype for Business users that Teams is available for upgrade.**</span></span>
    - <span data-ttu-id="be205-114">Если включить это, он сообщит Скайп для бизнес-пользователи, которые они можно выполнить обновление до приложения группы.</span><span class="sxs-lookup"><span data-stu-id="be205-114">If you turn this on, it will tell the Skype for Business users that they can upgrade to the Teams app.</span></span>
- <span data-ttu-id="be205-115">Задайте **Предпочитаемый приложение для пользователям присоединяться к Скайп для деловых встреч** , этот параметр определяет, какое приложение используется для присоединения к Скайп для бизнеса собраний и удостоился независимо от значения режима совместной работы.</span><span class="sxs-lookup"><span data-stu-id="be205-115">Set the **Preferred app for users to join Skype for Business meetings**  This setting determines which app is used for joining Skype for Business meetings and is honored regardless of the value of coexistence mode.</span></span>
    - <span data-ttu-id="be205-116">**Приложение Скайп собрания (по умолчанию)**</span><span class="sxs-lookup"><span data-stu-id="be205-116">**Skype Meetings app (default)**</span></span>
    - <span data-ttu-id="be205-117">**Скайп для бизнеса с ограниченными функциями**</span><span class="sxs-lookup"><span data-stu-id="be205-117">**Skype for Business with limited features**</span></span>
- <span data-ttu-id="be205-118">Задайте, будет ли для **загрузки приложения группы в фоновом режиме для Скайп для бизнес-пользователей** этот параметр без предупреждения файлы для загрузки приложения группы для пользователей, работающих с Скайп для бизнеса на Windows.</span><span class="sxs-lookup"><span data-stu-id="be205-118">Set whether to **Download the Teams app in the background for Skype for Business users**  This setting silently downloads the Teams app for users running Skype for Business on Windows.</span></span> <span data-ttu-id="be205-119">Применяется только в том случае, если режим сосуществования для пользователя — только группы или уведомления о ожидающие обновления включены в Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="be205-119">It is honored only if coexistence mode for the user is Teams Only, or if notifications of pending upgrade are enabled in Skype for Business.</span></span>
1. <span data-ttu-id="be205-120">После внесения изменений нажмите кнопку **Сохранить** .</span><span class="sxs-lookup"><span data-stu-id="be205-120">Click **Save** after you make your changes.</span></span>


### <a name="related-topics"></a><span data-ttu-id="be205-121">See also</span><span class="sxs-lookup"><span data-stu-id="be205-121">Related topics</span></span>
<span data-ttu-id="be205-122">[Планирование пути](upgrade-plan-journey.md)
[понять сосуществования и обновление режимов для Скайп для бизнеса и рабочих групп](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span><span class="sxs-lookup"><span data-stu-id="be205-122">[Plan the journey](upgrade-plan-journey.md)
[Understand coexistence and upgrade modes for Skype for Business and Teams](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)</span></span>