---
title: Управление параметрами конфигурации собраний в Skype для бизнеса Server 2015
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Сводка: Сведения об управлении параметров конфигурации собрания в Скайп для Business Server 2015.'
ms.openlocfilehash: 30b19eee5e298bfaa5eefe1eee50c9ea615b5682
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server-2015"></a><span data-ttu-id="6cdf3-103">Управление параметрами конфигурации собраний в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="6cdf3-103">Manage meeting configuration settings in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6cdf3-104">**Сводка:** Сведения об управлении параметров конфигурации собрания в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6cdf3-105">В этом разделе рассматривается задание параметров конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="6cdf3-106">Дополнительные сведения о планировании и развертывании конференц-связи видеть [план для конференц-связи в Скайп для Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) и [Развертывание конференц-связи в Скайп для Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="6cdf3-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server 2015](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server 2015](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="6cdf3-107">Параметры конфигурации собраний определяют тип собраний, которые могут создаваться пользователями, а также возможность и способ присоединения к собраниям анонимных пользователей и пользователей, подключающихся по телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="6cdf3-108">Обратите внимание на то, что эти параметры влияют только на запланированные собрания; они не влияют на незапланированных собраний, нажав кнопку «провести собрание» в Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="6cdf3-109">С помощью параметров конфигурации собраний задаются следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="6cdf3-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="6cdf3-110">может ли пользователь, выполняющий вызов из ТСОП, переходить в зал;</span><span class="sxs-lookup"><span data-stu-id="6cdf3-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="6cdf3-111">кто может быть докладчиком;</span><span class="sxs-lookup"><span data-stu-id="6cdf3-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="6cdf3-112">назначается ли тип конференции по умолчанию;</span><span class="sxs-lookup"><span data-stu-id="6cdf3-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="6cdf3-113">допускаются ли анонимные (непроверенные) пользователи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="6cdf3-114">Вы можете определить характеристики собраний с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="6cdf3-115">Можно указать собрания параметры на глобальном уровне (создаваться по умолчанию), веб-сайтов уровне или уровне пула.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="6cdf3-116">По умолчанию взаимодействие с пользователями определяется глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="6cdf3-117">Параметры, заданные на уровне пула, применяются ко всем собраниям, размещенным в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="6cdf3-118">При отсутствии параметров уровня пула применяются параметры уровня сайта, если они заданы.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="6cdf3-119">Если на уровне сайта параметры также не заданы, ко всем собраниям применяются глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6cdf3-120">Управление параметрами собрания с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="6cdf3-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="6cdf3-121">Для управления параметрами собрания с помощью Скайп для панели управления Business Server:</span><span class="sxs-lookup"><span data-stu-id="6cdf3-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="6cdf3-122">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="6cdf3-123">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="6cdf3-124">В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="6cdf3-125">Управление параметрами собрания с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="6cdf3-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="6cdf3-126">Для управления встречами с помощью Скайп для консоли Business Server, используйте следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="6cdf3-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="6cdf3-127">**Параметры конфигурации собрания**</span><span class="sxs-lookup"><span data-stu-id="6cdf3-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="6cdf3-128">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="6cdf3-128">**Cmdlet**</span></span>|<span data-ttu-id="6cdf3-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="6cdf3-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="6cdf3-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="6cdf3-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="6cdf3-131">Возвращает сведения о параметрах конфигурации собраний, в настоящее время используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="6cdf3-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="6cdf3-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="6cdf3-133">Создает новую коллекцию параметров конфигурации собраний на уровне сайта или службы.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="6cdf3-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="6cdf3-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="6cdf3-135">Удаляет существующую коллекцию параметров конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="6cdf3-136">SET-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="6cdf3-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="6cdf3-137">Изменение параметров конфигурации собраний, действующих в организации на данный момент.</span><span class="sxs-lookup"><span data-stu-id="6cdf3-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

