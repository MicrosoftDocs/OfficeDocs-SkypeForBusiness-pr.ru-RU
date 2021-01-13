---
title: Управление политиками архива в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: Сводка. Узнайте, как управлять политиками пользователей для архива в Skype для бизнеса Server.
ms.openlocfilehash: 949ac807faea4f563ee078512a3c0a335a517d2c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828555"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="af2f0-103">Управление политиками архива в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="af2f0-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="af2f0-104">**Сводка:** Learn how to manage user policies for archiving for Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="af2f0-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="af2f0-105">Изначально политики архивации устанавливаются при развертывании архивации, но после развертывания можно изменять, добавлять и удалять конфигурации.</span><span class="sxs-lookup"><span data-stu-id="af2f0-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="af2f0-106">Политики архива определяют, следует ли архивировать:</span><span class="sxs-lookup"><span data-stu-id="af2f0-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="af2f0-107">внутренние коммуникации;</span><span class="sxs-lookup"><span data-stu-id="af2f0-107">Internal communications</span></span>
    
- <span data-ttu-id="af2f0-108">внешние коммуникации.</span><span class="sxs-lookup"><span data-stu-id="af2f0-108">External communications</span></span>
    
<span data-ttu-id="af2f0-109">Политики архива можно настроить на глобальном уровне, на уровне сайта или пользователя.</span><span class="sxs-lookup"><span data-stu-id="af2f0-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af2f0-110">Если для развертывания включена интеграция с Microsoft Exchange, политики Exchange контролируют, включена ли архивация для пользователей, которые размещены в Exchange и для их почтовых ящиков включено In-Place удержание.</span><span class="sxs-lookup"><span data-stu-id="af2f0-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="af2f0-111">For details, [see Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server.](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)</span><span class="sxs-lookup"><span data-stu-id="af2f0-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="af2f0-112">Управление политиками архива с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="af2f0-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="af2f0-113">Вы можете управлять политиками архива с помощью панели управления следующим образом:</span><span class="sxs-lookup"><span data-stu-id="af2f0-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="af2f0-114">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="af2f0-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="af2f0-115">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="af2f0-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="af2f0-116">В левой панели навигации щелкните **"Политика архивации"**</span><span class="sxs-lookup"><span data-stu-id="af2f0-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="af2f0-117">Управление политиками архива с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="af2f0-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="af2f0-118">Вы также можете настроить политики архива с помощью Windows PowerShell, перечисленных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="af2f0-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="af2f0-119">Подробные сведения о синтаксис, включая все доступные параметры, см. в руководстве [Skype для бизнеса Server Management Shell.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="af2f0-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="af2f0-120">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="af2f0-120">**Cmdlet**</span></span>|<span data-ttu-id="af2f0-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="af2f0-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="af2f0-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="af2f0-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="af2f0-123">Возвращает сведения о политиках архива сеансов обмена мгновенными сообщениями в организации.</span><span class="sxs-lookup"><span data-stu-id="af2f0-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="af2f0-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="af2f0-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="af2f0-125">Назначает политики архива сеанса обмена мгновенными сообщениями пользователям или наборам пользователей.</span><span class="sxs-lookup"><span data-stu-id="af2f0-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="af2f0-126">Эти политики позволяют архивировать все сеансы обмена мгновенными сообщениями между внутренними пользователями и между внутренними и внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="af2f0-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="af2f0-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="af2f0-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="af2f0-128">Создает новые политики архивации сеансов обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="af2f0-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="af2f0-129">Эти политики позволяют архивировать все сеансы обмена мгновенными сообщениями между внутренними пользователями, а также все сеансы обмена мгновенными сообщениями между внутренними пользователями и внешними партнерами.</span><span class="sxs-lookup"><span data-stu-id="af2f0-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="af2f0-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="af2f0-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="af2f0-131">Удаляет указанную политику архива обмена мгновенными сообщениями, которая определяет, будет ли Skype для бизнеса Server автоматически сохранять все сеансы обмена мгновенными сообщениями между внутренними пользователями и(или) все сеансы обмена мгновенными сообщениями между внутренними пользователями и федеративными партнерами.</span><span class="sxs-lookup"><span data-stu-id="af2f0-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="af2f0-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="af2f0-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="af2f0-133">Изменяет существующую политику архива обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="af2f0-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="af2f0-134">Политика архива позволяет архивировать все сеансы и конференции im, которые проходят между внутренними пользователями; Можно также архивировать сеансы, которые проходят между внутренними пользователями и федератными партнерами.</span><span class="sxs-lookup"><span data-stu-id="af2f0-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

