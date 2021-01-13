---
title: Управление политиками conferencing в Skype для бизнеса Server
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
description: Сводка. Узнайте, как управлять политиками в Skype для бизнеса Server.
ms.openlocfilehash: 3ad59f186ccc4bebdefae1a6bfefdf04e9bf6851
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49835279"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="4e379-103">Управление политиками conferencing в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4e379-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="4e379-104">**Сводка:** Learn how to manage conferencing policies in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4e379-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="4e379-105">В этом разделе описывается управление политиками conferencing.</span><span class="sxs-lookup"><span data-stu-id="4e379-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="4e379-106">Дополнительные сведения о планировании и развертывании [conferencing](../../plan-your-deployment/conferencing/conferencing.md) см. в дополнительных сведениях о планировании и развертывании в Skype для бизнеса [Server.](../../deploy/deploy-conferencing/deploy-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="4e379-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="4e379-107">Политики проведения собраний позволяют определить широкий спектр параметров планирования и участия, начиная от того, может ли собрание включать IP-аудио и видео, до максимального количества участников.</span><span class="sxs-lookup"><span data-stu-id="4e379-107">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend.</span></span> <span data-ttu-id="4e379-108">Политики проведения собраний можно использовать для управления безопасностью, пропускной способностью и юридическими аспектами собраний.</span><span class="sxs-lookup"><span data-stu-id="4e379-108">You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="4e379-109">Политику конференц-связи можно определить на трех уровнях: в глобальной области действия, на уровне сайта и на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="4e379-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="4e379-110">Параметры применяются к конкретному пользователю от самой узкой до самой широкой области.</span><span class="sxs-lookup"><span data-stu-id="4e379-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="4e379-111">При назначении политики пользователю эти параметры имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="4e379-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="4e379-112">Если политика уровня пользователя не назначена, применяется политика уровня сайта.</span><span class="sxs-lookup"><span data-stu-id="4e379-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="4e379-113">Если не применяется ни политика уровня пользователя, ни политика уровня сайта, то используется глобальная политика, которая определяет настройки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4e379-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="4e379-p104">Глобальная политика существует по умолчанию, поэтому ее невозможно создать. Существующую глобальную политику также нельзя удалить, однако ее можно изменить, чтобы настроить параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="4e379-p104">A global policy exists by default, so you cannot create a new global policy. You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="4e379-116">Manage conferencing policies by using Skype for Business Server Control Panel</span><span class="sxs-lookup"><span data-stu-id="4e379-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="4e379-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span><span class="sxs-lookup"><span data-stu-id="4e379-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="4e379-118">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4e379-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="4e379-119">Откройте панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4e379-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="4e379-120">В левой панели навигации щелкните **"Conferencing" (Conferencing),** а затем щелкните **"Conferencing Policy" (Политика).**</span><span class="sxs-lookup"><span data-stu-id="4e379-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="4e379-121">Manage conferencing policies by using Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="4e379-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="4e379-122">Для управления собраниями с помощью skype for Business Server Management Shell используйте следующие команды:</span><span class="sxs-lookup"><span data-stu-id="4e379-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="4e379-123">**Параметры политики conferencing**</span><span class="sxs-lookup"><span data-stu-id="4e379-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="4e379-124">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="4e379-124">**Cmdlet**</span></span>|<span data-ttu-id="4e379-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="4e379-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="4e379-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="4e379-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="4e379-127">Возвращает сведения о политиках проведения конференций, используемых в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4e379-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="4e379-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="4e379-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="4e379-129">Назначает политику конференций на уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e379-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="4e379-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="4e379-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="4e379-131">Создает новую политику конференций в организации.</span><span class="sxs-lookup"><span data-stu-id="4e379-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="4e379-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="4e379-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="4e379-133">Удаляет указанную политику.</span><span class="sxs-lookup"><span data-stu-id="4e379-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="4e379-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="4e379-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="4e379-135">Изменяет существующую политику conferencing.</span><span class="sxs-lookup"><span data-stu-id="4e379-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

