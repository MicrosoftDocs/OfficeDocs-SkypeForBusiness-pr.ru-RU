---
title: Управление настройками собраний в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2e6c4f48-464e-4b8e-b7f4-68cdc1ae4ad9
description: Сводка. Сведения об управлении настройками конфигурации собраний в Skype для бизнеса Server.
ms.openlocfilehash: c34723219839061e36b2684dff81efd5cd914843
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828089"
---
# <a name="manage-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="07f72-103">Управление настройками собраний в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="07f72-103">Manage meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="07f72-104">**Сводка:** Узнайте, как управлять настройками конфигурации собраний в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="07f72-104">**Summary:** Learn how to manage meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="07f72-105">В этом разделе описывается, как управлять настройками конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="07f72-105">This topic describes how to manage meeting configuration settings.</span></span> <span data-ttu-id="07f72-106">Дополнительные сведения о планировании и развертывании [conferencing](../../plan-your-deployment/conferencing/conferencing.md) см. в дополнительных сведениях о планировании и развертывании в Skype для бизнеса [Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="07f72-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="07f72-107">Параметры конфигурации собраний определяют тип собраний, которые могут создавать пользователи, в дополнение к управлению тем, как анонимные пользователи и пользователи с телефонным доступом могут присоединяться к этим собраниям (или даже могут ли они присоединяться).</span><span class="sxs-lookup"><span data-stu-id="07f72-107">Meeting configuration settings dictate the type of meetings that users can create, in addition to controlling how (or even if) anonymous users and dial-in conferencing users can join these meetings.</span></span> <span data-ttu-id="07f72-108">Обратите внимание, что эти параметры влияют только на запланированные собрания; Они не влияют на нечеткие собрания, созданные с помощью параметра "Выполнить собрание" в Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="07f72-108">Note that these settings only affect scheduled meetings; they do not affect ad-hoc meetings created by clicking the Meet Now option in Skype for Business.</span></span>
  
<span data-ttu-id="07f72-109">Параметры конфигурации собраний определяют следующее:</span><span class="sxs-lookup"><span data-stu-id="07f72-109">Meeting configuration settings define the following:</span></span>
  
- <span data-ttu-id="07f72-110">попадают ли пользователи, подключающиеся из ТСОП, в зал ожидания;</span><span class="sxs-lookup"><span data-stu-id="07f72-110">Whether users dialing in from the public switched telephone network (PSTN) go to the lobby</span></span>
    
- <span data-ttu-id="07f72-111">кто может провести презентацию;</span><span class="sxs-lookup"><span data-stu-id="07f72-111">Who can be a presenter</span></span>
    
- <span data-ttu-id="07f72-112">назначается ли тип конференции по умолчанию;</span><span class="sxs-lookup"><span data-stu-id="07f72-112">Whether conference type is assigned by default</span></span>
    
- <span data-ttu-id="07f72-113">допускаются ли анонимные (непроверенные) пользователи по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="07f72-113">Whether anonymous (unauthenticated) users are admitted by default</span></span>
    
<span data-ttu-id="07f72-114">Характеристики собраний можно определить с помощью панели управления Skype для бизнеса Server или с помощью skype для бизнеса Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="07f72-114">You can define characteristics of meetings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span> 
  
<span data-ttu-id="07f72-115">Параметры собраний можно указать на глобальном уровне (по умолчанию создается), на уровне сайта или на уровне пула.</span><span class="sxs-lookup"><span data-stu-id="07f72-115">You can specify meeting settings at the global level (created by default), site level, or pool level.</span></span> <span data-ttu-id="07f72-116">По умолчанию глобальные параметры определяют процесс проведения собрания.</span><span class="sxs-lookup"><span data-stu-id="07f72-116">By default, the global settings define the meeting experience.</span></span> <span data-ttu-id="07f72-117">При создании параметров уровня пула эти параметры применяются ко всем собраниям, размещенным в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="07f72-117">If you create pool-level settings, those settings apply to all meetings hosted by that pool.</span></span> <span data-ttu-id="07f72-118">В отсутствие параметров уровня пула применяются параметры уровня сайта (при наличии).</span><span class="sxs-lookup"><span data-stu-id="07f72-118">If you do not create pool-level settings, site-level settings apply, if they exist.</span></span> <span data-ttu-id="07f72-119">Если параметры уровня сайта также не заданы, ко всем собраниям применяются глобальные параметры.</span><span class="sxs-lookup"><span data-stu-id="07f72-119">If you do not define site-level settings, the global settings apply to all meetings.</span></span>
  
## <a name="manage-meeting-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="07f72-120">Управление настройками собраний с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="07f72-120">Manage meeting settings by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="07f72-121">Для управления настройками собраний с помощью панели управления Skype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="07f72-121">To manage meeting settings by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="07f72-122">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="07f72-122">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="07f72-123">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="07f72-123">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="07f72-124">В левой панели навигации щелкните **"Conferencing"**(Конфигурация собрания) и выберите **"Конфигурация собрания".**</span><span class="sxs-lookup"><span data-stu-id="07f72-124">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
## <a name="manage-meeting-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="07f72-125">Управление настройками собраний с помощью оболочки управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="07f72-125">Manage meeting settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="07f72-126">Для управления собраниями с помощью skype for Business Server Management Shell используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="07f72-126">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="07f72-127">**Параметры конфигурации собрания**</span><span class="sxs-lookup"><span data-stu-id="07f72-127">**Meeting configuration settings**</span></span>

|<span data-ttu-id="07f72-128">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="07f72-128">**Cmdlet**</span></span>|<span data-ttu-id="07f72-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="07f72-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="07f72-130">Get-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="07f72-130">Get-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="07f72-131">Возвращает сведения о параметрах конфигурации собраний, которые в настоящее время используются в организации.</span><span class="sxs-lookup"><span data-stu-id="07f72-131">Returns information about the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="07f72-132">New-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="07f72-132">New-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="07f72-133">Создает новую коллекцию настроек конфигурации собраний на уровне сайта или службы.</span><span class="sxs-lookup"><span data-stu-id="07f72-133">Creates a new collection of meeting configuration settings at the site or service scope.</span></span>  <br/> |
|[<span data-ttu-id="07f72-134">Remove-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="07f72-134">Remove-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="07f72-135">Удаляет существующую коллекцию параметров конфигурации собраний.</span><span class="sxs-lookup"><span data-stu-id="07f72-135">Deletes an existing collection of meeting configuration settings.</span></span>  <br/> |
|[<span data-ttu-id="07f72-136">Set-CsMeetingConfiguration</span><span class="sxs-lookup"><span data-stu-id="07f72-136">Set-CsMeetingConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csmeetingconfiguration?view=skype-ps) <br/> |<span data-ttu-id="07f72-137">Изменяет параметры конфигурации собраний, которые в настоящее время используются в организации.</span><span class="sxs-lookup"><span data-stu-id="07f72-137">Modifies the meeting configuration settings currently in use in your organization.</span></span>  <br/> |
   

