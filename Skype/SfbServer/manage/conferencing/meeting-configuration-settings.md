---
title: Управление параметров конфигурации собрания в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Сводка: Сведения об управлении параметров конфигурации собрания в Скайп для Business Server.'
ms.openlocfilehash: 28f0dc37579f762b8ae3b0ac8ac58440c6ce5e24
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966068"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="c4533-103">Управление параметров конфигурации собрания в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="c4533-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="c4533-104">**Сводка:** Сведения об управлении параметров конфигурации собрания в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="c4533-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="c4533-105">В этом разделе рассматривается задание параметров конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="c4533-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="c4533-106">Дополнительные сведения о планировании и развертывании конференц-связи видеть [план для конференц-связи в Скайп для Business Server](../../plan-your-deployment/conferencing/conferencing.md) и [Развертывание конференц-связи в Скайп для Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="c4533-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="c4533-107">Параметры конфигурации собраний определяют тип собраний, которые могут создаваться пользователями, а также возможность и способ присоединения к собраниям анонимных пользователей и пользователей, подключающихся по телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="c4533-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="c4533-108">Обратите внимание на то, что эти параметры влияют только на запланированные собрания; они не влияют на незапланированных собраний, нажав кнопку «провести собрание» в Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="c4533-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="c4533-109">С помощью параметров конфигурации собраний задаются следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="c4533-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="c4533-110">может ли пользователь, выполняющий вызов из ТСОП, переходить в зал;</span><span class="sxs-lookup"><span data-stu-id="c4533-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="c4533-111">кто может быть докладчиком;</span><span class="sxs-lookup"><span data-stu-id="c4533-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="c4533-112">назначается ли тип конференции по умолчанию;</span><span class="sxs-lookup"><span data-stu-id="c4533-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="c4533-113">допускаются ли анонимные (непроверенные) пользователи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c4533-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="c4533-114">Вы можете определить характеристики собраний с помощью Скайп для панели управления Business Server или с помощью Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="c4533-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="c4533-115">Можно указать собрания параметры на глобальном уровне (создаваться по умолчанию), веб-сайтов уровне или уровне пула.</span><span class="sxs-lookup"><span data-stu-id="c4533-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="c4533-116">По умолчанию взаимодействие с пользователями определяется глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="c4533-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="c4533-117">Параметры, заданные на уровне пула, применяются ко всем собраниям, размещенным в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="c4533-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="c4533-118">При отсутствии параметров уровня пула применяются параметры уровня сайта, если они заданы.</span><span class="sxs-lookup"><span data-stu-id="c4533-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="c4533-119">Если на уровне сайта параметры также не заданы, ко всем собраниям применяются глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="c4533-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c4533-120">Управление параметрами собрания с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="c4533-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="c4533-121">Для управления параметрами собрания с помощью Скайп для панели управления Business Server:</span><span class="sxs-lookup"><span data-stu-id="c4533-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="c4533-122">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c4533-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="c4533-123">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c4533-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="c4533-124">В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="c4533-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c4533-125">Управление параметрами собрания с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="c4533-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="c4533-126">Для управления встречами с помощью Скайп для консоли Business Server, используйте следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="c4533-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="c4533-127">**Параметры конфигурации собрания**</span><span class="sxs-lookup"><span data-stu-id="c4533-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="c4533-128">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="c4533-128">**Cmdlet**</span></span>|<span data-ttu-id="c4533-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="c4533-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="c4533-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c4533-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="c4533-131">Возвращает сведения о параметрах конфигурации собраний, в настоящее время используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="c4533-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="c4533-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c4533-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="c4533-133">Создает новую коллекцию параметров конфигурации собраний на уровне сайта или службы.</span><span class="sxs-lookup"><span data-stu-id="c4533-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="c4533-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c4533-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="c4533-135">Удаляет существующую коллекцию параметров конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="c4533-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="c4533-136">SET-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c4533-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="c4533-137">Изменение параметров конфигурации собраний, действующих в организации на данный момент.</span><span class="sxs-lookup"><span data-stu-id="c4533-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

