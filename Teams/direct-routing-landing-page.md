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
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Узнайте больше о прямой маршрутике, например о конфигурации, необходимых основных решениях по развертыванию и о перенаправке голоса.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c5120f60778879be0978cb80c56daf99e5b5a38
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031825"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="59976-103">Прямая маршрутизация телефонной системы</span><span class="sxs-lookup"><span data-stu-id="59976-103">Phone System Direct Routing</span></span>

<span data-ttu-id="59976-104">Вы выполнили задачу [Начало работы](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="59976-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="59976-105">Вы развернули Teams с [чатом, командами, каналами и приложениями](deploy-chat-teams-channels-microsoft-teams-landing-page.md) в пределах всей организации.</span><span class="sxs-lookup"><span data-stu-id="59976-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="59976-106">Возможно, вы развернули & [для собраний.](deploy-meetings-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="59976-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="59976-107">Теперь вы готовы добавить облачную голосовую нагрузку и решили использовать собственный оператор телефонии для подключения к телефонной сети общего пользования с использованием прямой маршрутичности телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="59976-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="59976-108">Благодаря прямой маршрутизации вы можете использовать телефонную систему практически с любым оператором телефонной связи.</span><span class="sxs-lookup"><span data-stu-id="59976-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="59976-109">В этой статье описаны основные решения по развертыванию для прямой маршрутизации, а также дополнительные факторы, которые может потребоваться учитывать в зависимости от потребностей вашей организации.</span><span class="sxs-lookup"><span data-stu-id="59976-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="59976-110">Дополнительные сведения о предложениях Microsoft Cloud Voice вы также можете прочитать в [Microsoft Teams.](cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="59976-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="59976-111">Подробнее о прямой маршрутике</span><span class="sxs-lookup"><span data-stu-id="59976-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="59976-112">В следующих статьях вы можете получить дополнительные сведения о настройке и использовании прямой маршрутии телефонной системы.</span><span class="sxs-lookup"><span data-stu-id="59976-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="59976-113">Чтобы настроить прямую маршрутику, необходимо понимать, как она настраивается.</span><span class="sxs-lookup"><span data-stu-id="59976-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="59976-114">Чтобы понять, как планировать и настраивать прямую маршрутную маршрутику, ознакомьтесь со всеми этими статьями:</span><span class="sxs-lookup"><span data-stu-id="59976-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="59976-115">Планирование прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="59976-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="59976-116">Настройка прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="59976-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="59976-117">Список пограничных контроллеров сеансов, сертифицированных для прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="59976-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="59976-118">Отслеживание и устранение неполадок прямой маршрутизации</span><span class="sxs-lookup"><span data-stu-id="59976-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="59976-119">Кроме того, в зависимости от своих требований вам может потребоваться прочитать следующие статьи:</span><span class="sxs-lookup"><span data-stu-id="59976-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="59976-120">Настройка множества клиентов в пограничном контроллере сеансов</span><span class="sxs-lookup"><span data-stu-id="59976-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="59976-121">Переход на прямую маршрутизацию</span><span class="sxs-lookup"><span data-stu-id="59976-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="59976-122">Учетные записи пользователей в гибридной среде со связью с ТСОП</span><span class="sxs-lookup"><span data-stu-id="59976-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="59976-123">Просмотрите следующий сеанс, чтобы узнать больше о прямой маршрутике: [прямая маршрутия в Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="59976-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="59976-124">Основные решения по развертыванию</span><span class="sxs-lookup"><span data-stu-id="59976-124">Core deployment decisions</span></span>

<span data-ttu-id="59976-125">Это ключевые решения, которые следует рассмотреть при прямой маршрутии.</span><span class="sxs-lookup"><span data-stu-id="59976-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="59976-126">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="59976-126">Ask yourself</span></span>|<span data-ttu-id="59976-127">Действие</span><span class="sxs-lookup"><span data-stu-id="59976-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="59976-128">Для каких пользователей нужно включить прямую маршрутику?</span><span class="sxs-lookup"><span data-stu-id="59976-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="59976-129">Дополнительные сведения см. в подмножке "Включить пользователей [для прямой маршрутинга".](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="59976-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md).</span></span> |
<span data-ttu-id="59976-130">Есть ли у меня лицензии, необходимые для прямой маршрутинга?</span><span class="sxs-lookup"><span data-stu-id="59976-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="59976-131">Дополнительные сведения см. [в лицензиях и других требованиях.](direct-routing-plan.md#licensing-and-other-requirements)</span><span class="sxs-lookup"><span data-stu-id="59976-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="59976-132">Вопросы, учитывая контроллер границы сеанса (SBC)</span><span class="sxs-lookup"><span data-stu-id="59976-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="59976-133">При прямой маршрутике вы напрямую подключайте собственный пограничный контроллер сеанса (SBC) к телефонной системе.</span><span class="sxs-lookup"><span data-stu-id="59976-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="59976-134">Список сертифицированных SBCs см. в поддерживаемых пограничных контроллерах [сеанса.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="59976-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="59976-135">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="59976-135">Ask yourself</span></span>|<span data-ttu-id="59976-136">Действие</span><span class="sxs-lookup"><span data-stu-id="59976-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="59976-137">Где и как развернуть SBCs?</span><span class="sxs-lookup"><span data-stu-id="59976-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="59976-138">Дополнительные сведения см. в [сведениях о настройке прямой маршрутинга](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="59976-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="59976-139">У меня несколько клиентов?</span><span class="sxs-lookup"><span data-stu-id="59976-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="59976-140">Дополнительные сведения см. [в настройках граничного](direct-routing-sbc-multiple-tenants.md)геймпада сеанса для нескольких клиентов.</span><span class="sxs-lookup"><span data-stu-id="59976-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="59976-141">Факторы, которые следует учитывать при маршрутике голосовой почты</span><span class="sxs-lookup"><span data-stu-id="59976-141">Voice routing considerations</span></span>

<span data-ttu-id="59976-142">Вам потребуется настроить телефонную систему для перенастройки звонков на определенные компьютеры.</span><span class="sxs-lookup"><span data-stu-id="59976-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="59976-143">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="59976-143">Ask yourself</span></span>|<span data-ttu-id="59976-144">Действие</span><span class="sxs-lookup"><span data-stu-id="59976-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="59976-145">Какие политики маршрутинга голосовой почты, использования услуг ННР и голосовых маршрутов нужно создать?</span><span class="sxs-lookup"><span data-stu-id="59976-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="59976-146">Сведения о голосовой маршрутике см. в сведениях [о настройке маршрутинга голосовой почты.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="59976-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md).</span></span>
| <span data-ttu-id="59976-147">Какие пользователи будут назначены политике маршрутинга голосовой почты, которую я определяю?</span><span class="sxs-lookup"><span data-stu-id="59976-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="59976-148">Примеры см. в [настройках голосовой маршрутии.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="59976-148">See the examples in [Configure Voice Routing](direct-routing-configure.md).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="59976-149">Обеспечение входящих звонков в клиенте Teams с помощью TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="59976-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="59976-150">Прямая маршрутия поддерживается только в Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="59976-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="59976-151">Чтобы принимать звонки по ННР с помощью прямой маршрутизации, необходимо настроить TeamsUpgradePolicy, чтобы обеспечить прием входящих звонков в Teams.</span><span class="sxs-lookup"><span data-stu-id="59976-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="59976-152">Пользователи должны работать только в режиме Teams, что можно сделать, назначив им экземпляр UpgradeToTeams teamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="59976-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="59976-153">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="59976-153">Ask yourself</span></span>|<span data-ttu-id="59976-154">Действие</span><span class="sxs-lookup"><span data-stu-id="59976-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="59976-155">Что означает режим "Только teams"?</span><span class="sxs-lookup"><span data-stu-id="59976-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="59976-156">Дополнительные сведения см. в руководстве по миграции и совместной работе организаций, использующих [Teams вместе со Skype для бизнеса.](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)</span><span class="sxs-lookup"><span data-stu-id="59976-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="59976-157">Дополнительные соображения по развертыванию</span><span class="sxs-lookup"><span data-stu-id="59976-157">Additional deployment considerations</span></span>

<span data-ttu-id="59976-158">В зависимости от потребностей и конфигурации организации может потребоваться следующее:</span><span class="sxs-lookup"><span data-stu-id="59976-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="59976-159">Задайте себе вопрос</span><span class="sxs-lookup"><span data-stu-id="59976-159">Ask yourself</span></span>| <span data-ttu-id="59976-160">Действие</span><span class="sxs-lookup"><span data-stu-id="59976-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="59976-161">У вас есть существующее развертывание Skype для бизнеса Server с настроенными гибридными подключениями?</span><span class="sxs-lookup"><span data-stu-id="59976-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="59976-162">Чтобы узнать, как в гибридной среде подготовка и управление учетными записями пользователей, см. их в гибридной среде с подключением к [STN.](direct-routing-user-accounts-in-a-hybrid-environment.md)</span><span class="sxs-lookup"><span data-stu-id="59976-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="59976-163">Вы переходить на прямую маршрутику из плана звонков или из локальной среды Skype для бизнеса?</span><span class="sxs-lookup"><span data-stu-id="59976-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="59976-164">Дополнительные информацию о переходе на прямую маршрутику из существующей среды см. в статью "Переход на прямую [маршрутику".](direct-routing-migrating.md)</span><span class="sxs-lookup"><span data-stu-id="59976-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
