---
title: Управление политиками конференц-связи в Скайп для Business Server
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Сводка: Узнайте, как управлять политиками конференц-связи в Скайп для Business Server.'
ms.openlocfilehash: d5fed0c6615747069d71015fca33144ca41dd64b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20986659"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="edb17-103">Управление политиками конференц-связи в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="edb17-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="edb17-104">**Сводка:** Узнайте, как управлять политиками конференц-связи в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="edb17-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="edb17-105">В этом разделе описывается, каким образом можно управлять политиками конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="edb17-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="edb17-106">Дополнительные сведения о планировании и развертывании конференц-связи видеть [план для конференц-связи в Скайп для Business Server](../../plan-your-deployment/conferencing/conferencing.md) и [Развертывание конференц-связи в Скайп для Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="edb17-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="edb17-p102">Политика конференц-связи позволяет определить широкий спектр параметров расписания и участия, от возможности включения в собрание IP-аудио и видео, до максимального количества участников. Политики конференц-связи можно использовать для управления безопасностью, пропускной способностью и правовыми аспектами собраний.</span><span class="sxs-lookup"><span data-stu-id="edb17-p102">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend. You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="edb17-p103">Политику конференц-связи можно определить на трех уровнях: в глобальной области действия, на уровне сайта и на уровне пользователя. Параметры применяются к конкретному пользователю от самой узкой до самой широкой области. Политика уровня пользователя имеет наивысший приоритет. Если политика не назначена, применяется политика уровня сайта. Если не применяется ни политика уровня пользователя, ни политика уровня сайта, то используется глобальная политика, которая определяет настройки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="edb17-p103">You can define conferencing policy on three levels: global scope, site scope, and user scope. Settings apply to a specific user from the narrowest scope to the widest scope. If you assign a policy to a user, those settings take precedence. If you do not assign a user policy, site settings apply. If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="edb17-p104">Глобальная политика существует по умолчанию, поэтому ее невозможно создать. Существующую глобальную политику также нельзя удалить, однако ее можно изменить, чтобы настроить параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="edb17-p104">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="edb17-116">Управление политиками конференц-связи с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="edb17-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="edb17-117">Управление политик конференц-связи с помощью Скайп для панели управления Business Server:</span><span class="sxs-lookup"><span data-stu-id="edb17-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="edb17-118">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="edb17-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="edb17-119">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="edb17-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="edb17-120">На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="edb17-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="edb17-121">Управление политиками конференц-связи с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="edb17-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="edb17-122">Для управления встречами с помощью Скайп для консоли Business Server, используйте следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="edb17-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="edb17-123">**Параметры политик конференц-связи**</span><span class="sxs-lookup"><span data-stu-id="edb17-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="edb17-124">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="edb17-124">**Cmdlet**</span></span>|<span data-ttu-id="edb17-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="edb17-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="edb17-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="edb17-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="edb17-127">Возвращает сведения о политиках проведения конференций, используемых в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="edb17-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="edb17-128">GRANT-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="edb17-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="edb17-129">Назначает политику конференций на уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="edb17-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="edb17-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="edb17-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="edb17-131">Создает новую политику конференций в организации.</span><span class="sxs-lookup"><span data-stu-id="edb17-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="edb17-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="edb17-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="edb17-133">Удаляет выбранную политику конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="edb17-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="edb17-134">SET-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="edb17-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="edb17-135">Изменяет существующую политику конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="edb17-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

