---
title: Управление параметрами конфигурации собраний в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: 'Сводка: сведения о том, как управлять параметрами конфигурации собраний в Skype для бизнеса Server.'
ms.openlocfilehash: cefdf304d8cf5ed6ff4560dd5416283d733c3db2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818530"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="949b0-103">Управление параметрами конфигурации собраний в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="949b0-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="949b0-104">**Сводка:** Сведения о том, как управлять параметрами конфигурации собраний в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="949b0-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="949b0-105">В этом разделе рассматривается задание параметров конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="949b0-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="949b0-106">Дополнительные сведения о планировании и развертывании конференций можно найти [в разделе Планирование конференций в Skype для бизнеса Server](../../plan-your-deployment/conferencing/conferencing.md) и [развертывание конференций в Skype для бизнеса Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="949b0-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="949b0-107">Параметры конфигурации собраний определяют тип собраний, которые могут создаваться пользователями, а также возможность и способ присоединения к собраниям анонимных пользователей и пользователей, подключающихся по телефонной линии.</span><span class="sxs-lookup"><span data-stu-id="949b0-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="949b0-108">Обратите внимание, что эти параметры влияют только на запланированные собрания; они не влияют на нерегламентированные собрания, созданные с помощью команды "провести собрание" в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="949b0-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="949b0-109">С помощью параметров конфигурации собраний задаются следующие характеристики:</span><span class="sxs-lookup"><span data-stu-id="949b0-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="949b0-110">может ли пользователь, выполняющий вызов из ТСОП, переходить в зал;</span><span class="sxs-lookup"><span data-stu-id="949b0-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="949b0-111">кто может быть докладчиком;</span><span class="sxs-lookup"><span data-stu-id="949b0-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="949b0-112">назначается ли тип конференции по умолчанию;</span><span class="sxs-lookup"><span data-stu-id="949b0-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="949b0-113">допускаются ли анонимные (непроверенные) пользователи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="949b0-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="949b0-114">Вы можете определить характеристики собраний с помощью панели управления Skype для бизнеса Server или с помощью командной консоли Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="949b0-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="949b0-115">Вы можете указать параметры собрания на глобальном уровне (создан по умолчанию), на уровне сайта или на уровне пула.</span><span class="sxs-lookup"><span data-stu-id="949b0-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="949b0-116">По умолчанию взаимодействие с пользователями определяется глобальными параметрами.</span><span class="sxs-lookup"><span data-stu-id="949b0-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="949b0-117">Параметры, заданные на уровне пула, применяются ко всем собраниям, размещенным в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="949b0-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="949b0-118">При отсутствии параметров уровня пула применяются параметры уровня сайта, если они заданы.</span><span class="sxs-lookup"><span data-stu-id="949b0-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="949b0-119">Если на уровне сайта параметры также не заданы, ко всем собраниям применяются глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="949b0-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="949b0-120">Управление параметрами собраний с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="949b0-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="949b0-121">Управление параметрами собраний с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="949b0-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="949b0-122">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="949b0-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="949b0-123">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="949b0-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="949b0-124">В левой области навигации щелкните **Конференц-связь**, затем **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="949b0-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="949b0-125">Управление параметрами собраний с помощью командной консоли Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="949b0-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="949b0-126">Для управления собраниями с помощью командной консоли Skype для бизнеса Server используйте следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="949b0-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="949b0-127">**Параметры конфигурации собрания**</span><span class="sxs-lookup"><span data-stu-id="949b0-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="949b0-128">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="949b0-128">**Cmdlet**</span></span>|<span data-ttu-id="949b0-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="949b0-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="949b0-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="949b0-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="949b0-131">Возвращение сведений о параметрах конфигурации собраний, действующих в организации на данный момент.</span><span class="sxs-lookup"><span data-stu-id="949b0-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="949b0-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="949b0-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="949b0-133">Создает новую коллекцию настроек конфигурации собраний на уровне сайта или службы.</span><span class="sxs-lookup"><span data-stu-id="949b0-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="949b0-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="949b0-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="949b0-135">Удаляет существующую коллекцию параметров конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="949b0-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="949b0-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="949b0-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="949b0-137">Изменение параметров конфигурации собраний, действующих в организации на данный момент.</span><span class="sxs-lookup"><span data-stu-id="949b0-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

