---
title: Управление политиками конференц-связи в Скайп для Business Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 34ec5e41-6fe6-450b-81b0-0d17b9989839
description: 'Сводка: Узнайте, как управлять политиками конференц-связи в Скайп для Business Server.'
ms.openlocfilehash: 96b2f5e27aa65931f5cd76499e1a3f66b817baa5
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898146"
---
# <a name="manage-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="d954a-103">Управление политиками конференц-связи в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="d954a-103">Manage conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="d954a-104">**Сводка:** Узнайте, как управлять политиками конференц-связи в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="d954a-104">**Summary:** Learn how to manage conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="d954a-105">В этом разделе описывается, каким образом можно управлять политиками конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="d954a-105">This topic describes how to manage conferencing policies.</span></span> <span data-ttu-id="d954a-106">Дополнительные сведения о планировании и развертывании конференц-связи видеть [план для конференц-связи в Скайп для Business Server](../../plan-your-deployment/conferencing/conferencing.md) и [Развертывание конференц-связи в Скайп для Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="d954a-106">For more information about how to plan and deploy conferencing, see [Plan for conferencing in Skype for Business Server](../../plan-your-deployment/conferencing/conferencing.md) and [Deploy conferencing in Skype for Business Server](../../deploy/deploy-conferencing/deploy-conferencing.md).</span></span>
  
<span data-ttu-id="d954a-p102">Политика конференц-связи позволяет определить широкий спектр параметров расписания и участия, от возможности включения в собрание IP-аудио и видео, до максимального количества участников. Политики конференц-связи можно использовать для управления безопасностью, пропускной способностью и правовыми аспектами собраний.</span><span class="sxs-lookup"><span data-stu-id="d954a-p102">Conferencing policies allow you to define a wide variety of scheduling and participation options, ranging from whether a meeting can include IP audio and video to the maximum number of people who can attend. You can use conferencing policies to manage security, bandwidth, and legal aspects of meetings.</span></span>
  
<span data-ttu-id="d954a-109">Политику конференц-связи можно определить на трех уровнях: в глобальной области действия, на уровне сайта и на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="d954a-109">You can define conferencing policy on three levels: global scope, site scope, and user scope.</span></span> <span data-ttu-id="d954a-110">Параметры применяются к конкретному пользователю от самой узкой до самой широкой области.</span><span class="sxs-lookup"><span data-stu-id="d954a-110">Settings apply to a specific user from the narrowest scope to the widest scope.</span></span> <span data-ttu-id="d954a-111">Политика уровня пользователя имеет наивысший приоритет.</span><span class="sxs-lookup"><span data-stu-id="d954a-111">If you assign a policy to a user, those settings take precedence.</span></span> <span data-ttu-id="d954a-112">Если политика не назначена, применяется политика уровня сайта.</span><span class="sxs-lookup"><span data-stu-id="d954a-112">If you do not assign a user policy, site settings apply.</span></span> <span data-ttu-id="d954a-113">Если не применяется ни политика уровня пользователя, ни политика уровня сайта, то используется глобальная политика, которая определяет настройки по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d954a-113">If no user or site policies apply, global policy provides the default settings.</span></span>
  
<span data-ttu-id="d954a-114">Глобальная политика существует по умолчанию, поэтому ее невозможно создать.</span><span class="sxs-lookup"><span data-stu-id="d954a-114">A global policy exists by default, so you cannot create a new global policy.</span></span> <span data-ttu-id="d954a-115">Существующую глобальную политику также нельзя удалить, однако ее можно изменить, чтобы настроить параметры по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d954a-115">You also cannot delete the existing global policy, but you can change the existing global policy to customize your default settings.</span></span>
  
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="d954a-116">Управление политиками конференц-связи с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="d954a-116">Manage conferencing policies by using Skype for Business Server Control Panel</span></span>

<span data-ttu-id="d954a-117">Управление политик конференц-связи с помощью Скайп для панели управления Business Server:</span><span class="sxs-lookup"><span data-stu-id="d954a-117">To manage conferencing policies by using Skype for Business Server Control Panel:</span></span>
  
1. <span data-ttu-id="d954a-118">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d954a-118">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="d954a-119">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="d954a-119">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="d954a-120">На левой панели навигации щелкните **Конференция**, а затем — **Политика конференц-связи**.</span><span class="sxs-lookup"><span data-stu-id="d954a-120">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
## <a name="manage-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="d954a-121">Управление политиками конференц-связи с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="d954a-121">Manage conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="d954a-122">Для управления встречами с помощью Скайп для консоли Business Server, используйте следующие командлеты:</span><span class="sxs-lookup"><span data-stu-id="d954a-122">To manage meetings by using Skype for Business Server Management Shell, use the following cmdlets:</span></span>
  
<span data-ttu-id="d954a-123">**Параметры политики конференц-связи**</span><span class="sxs-lookup"><span data-stu-id="d954a-123">**Conferencing policy settings**</span></span>

|<span data-ttu-id="d954a-124">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="d954a-124">**Cmdlet**</span></span>|<span data-ttu-id="d954a-125">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d954a-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="d954a-126">Get-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="d954a-126">Get-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="d954a-127">Возвращает сведения о политиках проведения конференций, используемых в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d954a-127">Returns information about the conferencing policies that have been configured for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="d954a-128">Grant-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="d954a-128">Grant-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="d954a-129">Назначает политику конференций на уровне пользователей.</span><span class="sxs-lookup"><span data-stu-id="d954a-129">Assigns a conferencing policy at the per-user scope.</span></span>  <br/> |
|[<span data-ttu-id="d954a-130">New-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="d954a-130">New-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="d954a-131">Создает новую политику конференций в организации.</span><span class="sxs-lookup"><span data-stu-id="d954a-131">Creates a new conferencing policy for use in your organization.</span></span>  <br/> |
|[<span data-ttu-id="d954a-132">Remove-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="d954a-132">Remove-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="d954a-133">Удаляет выбранную политику конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="d954a-133">Removes the specified conferencing policy.</span></span>  <br/> |
|[<span data-ttu-id="d954a-134">Set-CsConferencingPolicy</span><span class="sxs-lookup"><span data-stu-id="d954a-134">Set-CsConferencingPolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps) <br/> |<span data-ttu-id="d954a-135">Изменяет существующую политику конференц-связи.</span><span class="sxs-lookup"><span data-stu-id="d954a-135">Modifies an existing conferencing policy.</span></span>  <br/> |
   

