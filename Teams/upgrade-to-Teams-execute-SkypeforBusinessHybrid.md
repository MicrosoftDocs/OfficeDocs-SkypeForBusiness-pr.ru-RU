---
title: Обновление Скайп для гибридного развертывания бизнес группами, корпорация Майкрософт | PSTN
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Вопросы, касающиеся обновления группам из Скайп для бизнеса гибридного развертывания.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e27e36a26115acf23536edb896066d6bc78daa4e
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464814"
---
<span data-ttu-id="5b5c3-103">![Этапы обновления пути с акцентом на развертывание и стадии реализации] (media/upgrade-banner-deployment.png "Этапы обновления пути с акцентом на развертывание и стадии реализации")</span><span class="sxs-lookup"><span data-stu-id="5b5c3-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="5b5c3-104">В этой статье является частью развертывания и внедрения этапа обновления пути.</span><span class="sxs-lookup"><span data-stu-id="5b5c3-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="5b5c3-105">Прежде чем продолжить, убедитесь, что вы выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="5b5c3-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="5b5c3-106">Прикреплено другие заинтересованные стороны проекта</span><span class="sxs-lookup"><span data-stu-id="5b5c3-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="5b5c3-107">Определенные области проекта</span><span class="sxs-lookup"><span data-stu-id="5b5c3-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="5b5c3-108">Поняты сосуществования и взаимодействия Скайп для бизнеса и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="5b5c3-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="5b5c3-109">Выбранные обновления пути</span><span class="sxs-lookup"><span data-stu-id="5b5c3-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="5b5c3-110">Подготовка среды</span><span class="sxs-lookup"><span data-stu-id="5b5c3-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="5b5c3-111">Подготовлено вашей организации</span><span class="sxs-lookup"><span data-stu-id="5b5c3-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="5b5c3-112">Проведение пилотного проекта</span><span class="sxs-lookup"><span data-stu-id="5b5c3-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="5b5c3-113">Обновление с Скайп для бизнеса гибридного развертывания для группы</span><span class="sxs-lookup"><span data-stu-id="5b5c3-113">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="5b5c3-114">Следуйте рекомендациям в статье в этой статье, если развернута Скайп для бизнеса или локальной Microsoft Lync и настроенные в гибридном развертывании с помощью клиента Office 365 и организации необходимо обновить групп, либо выборочно — с помощью нескольких режимы совместная работа — или файловый.</span><span class="sxs-lookup"><span data-stu-id="5b5c3-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 tenant, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="5b5c3-115">Для любого из пути обновления необходимо переместить пользователей в Скайп для бизнеса в Интернет (если они еще не размещаются Интернет-версия) и назначить их соответствующие сосуществования и обновления режим.</span><span class="sxs-lookup"><span data-stu-id="5b5c3-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren’t already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="5b5c3-116">Шаг 1: Перемещение пользователей в Скайп для бизнеса в Интернет</span><span class="sxs-lookup"><span data-stu-id="5b5c3-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="5b5c3-117">Этот шаг применяется для пользователей, которые в настоящее время размещенные локально.</span><span class="sxs-lookup"><span data-stu-id="5b5c3-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="5b5c3-118">Дополнительные сведения о перемещении этих пользователей к Скайп для бизнеса в Интернет можно [переместить пользователей из локально - к Скайп для бизнеса в Интернет](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="5b5c3-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="5b5c3-119">Шаг 2: Назначение сосуществования и режим обновления</span><span class="sxs-lookup"><span data-stu-id="5b5c3-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="5b5c3-120">После переноса пользователей к Скайп для бизнеса в Интернет, их можно назначить соответствующие сосуществования режим по пути обновления, принято решение вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5b5c3-120">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="5b5c3-121">Для получения дополнительных сведений см [Задание вашей сосуществования и параметры обновления](https://aka.ms/SkypeToTeams-SetCoexistence) и [TeamsUpgradePolicy: управление миграция и сосуществование](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="5b5c3-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="5b5c3-122">С Скайп Business Server 2019 и будущих накопительного обновления Скайп для Business Server 2015 можно будет выполнять шаг 1 (переход на Скайп для бизнеса в Интернет) и шаг 2 (обновления пользователей группам) за один шаг.</span><span class="sxs-lookup"><span data-stu-id="5b5c3-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="5b5c3-123">Дополнительные сведения будут предоставлены после выпуска Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="5b5c3-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="5b5c3-124">Обновление телефонной системой и рабочих групп</span><span class="sxs-lookup"><span data-stu-id="5b5c3-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="5b5c3-125">При переносе данных вашей Скайп для бизнеса гибридного развертывания для телефонной системы с помощью вызова планы и Майкрософт будет ваш поставщик телефонной сети (общего пользования PSTN), и при условии, что вы выполнили телефонных номеров перенос — обновление пользователям Команды будет автоматический переход входящих PSTN, вызов к группам.</span><span class="sxs-lookup"><span data-stu-id="5b5c3-125">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="5b5c3-126">Вызов планы недоступен или которые планируется использовать поставщик существующего подключения к ТСОП, требуется ли перенос развертывания корпоративной голосовой связи — или гибридного развертывания голосовой связи, которая использует существующий локального развертывания или облака соединителя Edition — для Microsoft телефонной системой прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="5b5c3-126">If Calling Plans isn’t available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="5b5c3-127">Обновление пользователей в группы, см.в [Дополнительные вопросы для прямой маршрутизации телефонной системы](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="5b5c3-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
