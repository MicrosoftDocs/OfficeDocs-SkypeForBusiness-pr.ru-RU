---
title: Прямая маршрутизация телефонной системы
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
description: Главная страница для прямой маршрутизации
appliesto:
- Microsoft Teams
ms.openlocfilehash: d146c2188f57dbee3887dd2fd595c1b06a86c30e
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836069"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="2861a-103">Прямая маршрутизация телефонной системы</span><span class="sxs-lookup"><span data-stu-id="2861a-103">Phone System Direct Routing</span></span>

<span data-ttu-id="2861a-104">Вы выполнили задачу [Начало работы](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="2861a-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="2861a-105">Вы развернули Teams с [чатом, командами, каналами и приложениями](deploy-chat-teams-channels-microsoft-teams-landing-page.md) в пределах всей организации.</span><span class="sxs-lookup"><span data-stu-id="2861a-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="2861a-106">Возможно, вы развернули [собрания & конференции](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="2861a-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="2861a-107">Теперь вы можете добавлять облачные рабочие нагрузки, и вы решили использовать собственную телефонную службу для подключения по коммутируемой телефонной сети (PSTN) с помощью прямой маршрутизации телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="2861a-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="2861a-108">При прямой маршрутизации вы можете использовать телефонную систему практически любого поставщика услуг телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="2861a-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="2861a-109">В этой статье описаны основные решения по развертыванию для прямой маршрутизации, а также дополнительные аспекты, о которых вы можете подумать, в зависимости от потребностей Организации.</span><span class="sxs-lookup"><span data-stu-id="2861a-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="2861a-110">Вы также должны прочитать [облачный голосовой звонок в Microsoft Teams](cloud-voice-landing-page.md) , чтобы получить дополнительные сведения о облачных голосовых предложениях Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="2861a-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="2861a-111">Дополнительные сведения о прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="2861a-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="2861a-112">В следующих статьях содержатся дополнительные сведения о настройке и использовании прямой маршрутизации для телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="2861a-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="2861a-113">Для настройки прямой маршрутизации необходимо понимать модель маршрутизации PSTN.</span><span class="sxs-lookup"><span data-stu-id="2861a-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="2861a-114">Вы должны прочитать все эти статьи, чтобы понять, как планировать и настраивать прямую маршрутизацию.</span><span class="sxs-lookup"><span data-stu-id="2861a-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="2861a-115">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="2861a-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="2861a-116">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="2861a-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="2861a-117">Список пограничных контроллеров сеансов, сертифицированных для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="2861a-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="2861a-118">Отслеживание и устранение неполадок прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="2861a-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="2861a-119">Кроме того, вам может потребоваться прочитать следующие статьи в зависимости от ваших требований:</span><span class="sxs-lookup"><span data-stu-id="2861a-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="2861a-120">Настройка множества клиентов в пограничном контроллере сеансов</span><span class="sxs-lookup"><span data-stu-id="2861a-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="2861a-121">Переход на прямую маршрутизацию</span><span class="sxs-lookup"><span data-stu-id="2861a-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="2861a-122">Учетные записи пользователей в гибридной среде со связью с ТСОП</span><span class="sxs-lookup"><span data-stu-id="2861a-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="2861a-123">Чтобы узнать больше о прямом маршруте, просмотрите следующий сеанс: [Прямая маршрутизация в Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="2861a-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="2861a-124">Основные решения по развертыванию</span><span class="sxs-lookup"><span data-stu-id="2861a-124">Core deployment decisions</span></span>

<span data-ttu-id="2861a-125">Это основные решения, которые необходимо предусмотреть для прямой маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="2861a-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="2861a-126">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="2861a-126">Ask yourself</span></span>|<span data-ttu-id="2861a-127">Действие</span><span class="sxs-lookup"><span data-stu-id="2861a-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="2861a-128">Для каких пользователей будет разрешена прямая маршрутизация?</span><span class="sxs-lookup"><span data-stu-id="2861a-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="2861a-129">Дополнительные сведения можно найти в разделе [Включение пользователей для прямой маршрутизации](direct-routing-configure.md#enable-users-for-direct-routing-service).</span><span class="sxs-lookup"><span data-stu-id="2861a-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span></span> |
<span data-ttu-id="2861a-130">У меня есть необходимые лицензии на прямую маршрутизацию?</span><span class="sxs-lookup"><span data-stu-id="2861a-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="2861a-131">Дополнительные сведения можно найти в разделе [Лицензирование и другие требования](direct-routing-plan.md#licensing-and-other-requirements).</span><span class="sxs-lookup"><span data-stu-id="2861a-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="2861a-132">Рекомендации для контроллера границ сеанса (SBC)</span><span class="sxs-lookup"><span data-stu-id="2861a-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="2861a-133">С помощью прямой маршрутизации вы подключаете свой собственный сеансовый контроллер (SBC) напрямую к телефонной системе.</span><span class="sxs-lookup"><span data-stu-id="2861a-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="2861a-134">Список сертифицированных SBCs-данных можно найти в разделе [Поддерживаемые контроллеры границ для сеансов](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="2861a-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="2861a-135">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="2861a-135">Ask yourself</span></span>|<span data-ttu-id="2861a-136">Действие</span><span class="sxs-lookup"><span data-stu-id="2861a-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="2861a-137">Где и как выполняется развертывание SBCs?</span><span class="sxs-lookup"><span data-stu-id="2861a-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="2861a-138">Дополнительные сведения можно найти в разделе [Настройка Direct Routing](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="2861a-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="2861a-139">У меня несколько клиентов?</span><span class="sxs-lookup"><span data-stu-id="2861a-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="2861a-140">Дополнительные сведения можно найти [в разделе Настройка контроллера границ сеанса для нескольких клиентов](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="2861a-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="2861a-141">Рекомендации по маршрутизации голосовых сообщений</span><span class="sxs-lookup"><span data-stu-id="2861a-141">Voice routing considerations</span></span>

<span data-ttu-id="2861a-142">Вам потребуется настроить телефонную систему так, чтобы она направляла звонки на определенную SBCs.</span><span class="sxs-lookup"><span data-stu-id="2861a-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="2861a-143">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="2861a-143">Ask yourself</span></span>|<span data-ttu-id="2861a-144">Действие</span><span class="sxs-lookup"><span data-stu-id="2861a-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="2861a-145">Какие политики маршрутизации голосовой связи, использование КТСОП и голосовые маршруты нужно создать?</span><span class="sxs-lookup"><span data-stu-id="2861a-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="2861a-146">Сведения о маршрутизации голоса можно найти в разделе [Настройка голосовой маршрутизации](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="2861a-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span>
| <span data-ttu-id="2861a-147">Пользователи, которым будут назначены политики голосовой маршрутизации, определяемые мной</span><span class="sxs-lookup"><span data-stu-id="2861a-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="2861a-148">В этом разделе приведены примеры [настройки голосовой маршрутизации](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="2861a-148">See the examples in [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="2861a-149">Обеспечение приема входящих звонков в клиенте Teams с помощью Теамсупградеполици</span><span class="sxs-lookup"><span data-stu-id="2861a-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="2861a-150">Прямая маршрутизация поддерживается только в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2861a-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="2861a-151">Чтобы принимать звонки PSTN через прямую маршрутизацию, вам нужно настроить Теамсупградеполици для обеспечения приема входящих звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="2861a-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="2861a-152">Пользователи должны находиться в режиме "только для Teams", который можно сделать, назначив им экземпляр "Упградетотеамс" для Теамсупградеполици.</span><span class="sxs-lookup"><span data-stu-id="2861a-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="2861a-153">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="2861a-153">Ask yourself</span></span>|<span data-ttu-id="2861a-154">Действие</span><span class="sxs-lookup"><span data-stu-id="2861a-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="2861a-155">Что означает режим "только для Teams"?</span><span class="sxs-lookup"><span data-stu-id="2861a-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="2861a-156">Дополнительные сведения можно найти [в статье Руководство по миграции и взаимодействию для организаций, использующих Teams вместе со Skype для бизнеса](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="2861a-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="2861a-157">Дополнительные рекомендации по развертыванию</span><span class="sxs-lookup"><span data-stu-id="2861a-157">Additional deployment considerations</span></span>

<span data-ttu-id="2861a-158">В зависимости от потребностей и конфигурации вашей организации вы можете использовать следующее:</span><span class="sxs-lookup"><span data-stu-id="2861a-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="2861a-159">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="2861a-159">Ask yourself</span></span>| <span data-ttu-id="2861a-160">Действие</span><span class="sxs-lookup"><span data-stu-id="2861a-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="2861a-161">Есть ли у вас развертывание Skype для бизнеса Server с настроенным гибридным подключением?</span><span class="sxs-lookup"><span data-stu-id="2861a-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="2861a-162">Чтобы понять, как подготавливаются и управляются учетные записи пользователей в гибридной среде, ознакомьтесь [с учетными записями пользователей в гибридной среде с подключением КТСОП](direct-routing-user-accounts-in-a-hybrid-environment.md).</span><span class="sxs-lookup"><span data-stu-id="2861a-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="2861a-163">Выполняется ли миграция на прямую маршрутизацию из плана звонков или из локальной среды Skype для бизнеса?</span><span class="sxs-lookup"><span data-stu-id="2861a-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="2861a-164">Чтобы узнать больше о переходе на прямую маршрутизацию из существующей среды, ознакомьтесь со статьей [Переход на прямую маршрутизацию](direct-routing-migrating.md).</span><span class="sxs-lookup"><span data-stu-id="2861a-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
