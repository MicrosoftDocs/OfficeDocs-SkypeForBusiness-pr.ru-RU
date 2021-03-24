---
title: Управление политиками конференциинга в Skype для бизнеса Server
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
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: Сводка. Узнайте, как управлять политиками конференций в Skype для бизнеса Server.
ms.openlocfilehash: 39855aac09b88852d0931c9b8fbdb8e2e9187c71
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099105"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="0dfad-103">Управление политиками конференциинга в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0dfad-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="0dfad-104">**Сводка:** Узнайте, как управлять политиками конференций в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="0dfad-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="0dfad-105">В этом разделе описывается управление политиками конференций.</span><span class="sxs-lookup"><span data-stu-id="0dfad-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="0dfad-106">Дополнительные сведения о планировании и развертывании конференций см. в веб-сведениях Plan [for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) и Deploy [conferencing in Skype for Business Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="0dfad-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="0dfad-107">Политики конференциации позволяют определить самые разнообразные варианты планирования и участия, начиная от того, может ли собрание включать ip-аудио и видео до максимального числа людей, которые могут присутствовать.</span><span class="sxs-lookup"><span data-stu-id="0dfad-107">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="0dfad-108">Политики проведения собраний можно использовать для управления безопасностью, пропускной способностью и юридическими аспектами собраний.</span><span class="sxs-lookup"><span data-stu-id="0dfad-108">You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="0dfad-109">Политику конференц-связи можно определить на трех уровнях: в глобальной области действия, на уровне сайта и на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="0dfad-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="0dfad-110">Параметры применяются к конкретному пользователю от самой узкой до самой широкой области.</span><span class="sxs-lookup"><span data-stu-id="0dfad-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="0dfad-111">Если назначить политику пользователю, эти параметры будут иметь приоритет.</span><span class="sxs-lookup"><span data-stu-id="0dfad-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="0dfad-112">Если политика уровня пользователя не назначена, применяется политика уровня сайта.</span><span class="sxs-lookup"><span data-stu-id="0dfad-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="0dfad-113">Если не применяется ни политика уровня пользователя, ни политика уровня сайта, то используется глобальная политика, которая определяет настройки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0dfad-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="0dfad-p104">Глобальная политика существует по умолчанию, поэтому ее невозможно создать. Существующую глобальную политику также нельзя удалить, однако ее можно изменить, чтобы настроить параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0dfad-p104">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="0dfad-116">Управление политиками конференций с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="0dfad-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="0dfad-117">Управление политиками конференций с помощью панели управления Skype для бизнес-серверов:</span><span class="sxs-lookup"><span data-stu-id="0dfad-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="0dfad-118">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="0dfad-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="0dfad-119">Откройте панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="0dfad-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="0dfad-120">В левой панели навигации нажмите **кнопку Conferencing** и нажмите кнопку **Политика конференциации**.</span><span class="sxs-lookup"><span data-stu-id="0dfad-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="0dfad-121">Управление политиками конференциинга с помощью оболочки управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="0dfad-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="0dfad-122">Для управления собраниями с помощью skype for Business Server Management Shell используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="0dfad-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="0dfad-123">**Параметры политики conferencing**</span><span class="sxs-lookup"><span data-stu-id="0dfad-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="0dfad-124">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="0dfad-124">**Cmdlet**</span></span>|<span data-ttu-id="0dfad-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="0dfad-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="0dfad-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="0dfad-126">Get-CsConferencingPolicy</span></span>](/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="0dfad-127">Возвращает сведения о политиках проведения конференций, используемых в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0dfad-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="0dfad-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="0dfad-128">Grant-CsConferencingPolicy</span></span>](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="0dfad-129">Назначает политику конференций на уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="0dfad-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="0dfad-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="0dfad-130">New-CsConferencingPolicy</span></span>](/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="0dfad-131">Создает новую политику конференций в организации.</span><span class="sxs-lookup"><span data-stu-id="0dfad-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="0dfad-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="0dfad-132">Remove-CsConferencingPolicy</span></span>](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="0dfad-133">Удаляет указанную политику конференций.</span><span class="sxs-lookup"><span data-stu-id="0dfad-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="0dfad-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="0dfad-134">Set-CsConferencingPolicy</span></span>](/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="0dfad-135">Изменяет существующую политику конференции.</span><span class="sxs-lookup"><span data-stu-id="0dfad-135">Modifies an existing conferencing policy.</span></span>  <br/> |
