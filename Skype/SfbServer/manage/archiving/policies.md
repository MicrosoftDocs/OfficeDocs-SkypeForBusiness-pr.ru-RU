---
title: Управление политиками архивации в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Сводка: Управление политиками пользователей для архивации в Skype для бизнеса Server.'
ms.openlocfilehash: f6918907f73ffe1b098ed96e1997d8ab8ffe4f9f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278428"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="7d44d-103">Управление политиками архивации в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7d44d-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="7d44d-104">**Сводка:** Сведения об управлении политиками пользователей для архивации в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7d44d-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="7d44d-105">Изначально политики архивации были настроены при развертывании архивации, но вы можете изменить, добавить и удалить настройки после развертывания.</span><span class="sxs-lookup"><span data-stu-id="7d44d-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="7d44d-106">Политики архивации определяют, следует ли архивировать:</span><span class="sxs-lookup"><span data-stu-id="7d44d-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="7d44d-107">внутренние коммуникации;</span><span class="sxs-lookup"><span data-stu-id="7d44d-107">Internal communications</span></span>
    
- <span data-ttu-id="7d44d-108">внешние коммуникации.</span><span class="sxs-lookup"><span data-stu-id="7d44d-108">External communications</span></span>
    
<span data-ttu-id="7d44d-109">Политики архивации можно настроить на уровне Global, site или User.</span><span class="sxs-lookup"><span data-stu-id="7d44d-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7d44d-110">Если вы включили интеграцию Microsoft Exchange для развертывания, политики Exchange определяют, разрешено ли архивирование для пользователей, использующих Exchange, и почтовые ящики, которые помещаются на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="7d44d-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="7d44d-111">Подробности можно найти [в разделе Планирование архивации в Skype для бизнеса Server](../../plan-your-deployment/archiving/archiving.md) и [Настройка интеграции с хранилищем Exchange для Skype для бизнеса Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="7d44d-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="7d44d-112">Управление политиками архивации с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="7d44d-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="7d44d-113">Управлять политиками архивации можно с помощью панели управления. Для этого:</span><span class="sxs-lookup"><span data-stu-id="7d44d-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="7d44d-114">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7d44d-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="7d44d-115">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7d44d-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="7d44d-116">В левой области навигации щелкните **Политика архивации**</span><span class="sxs-lookup"><span data-stu-id="7d44d-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="7d44d-117">Управление политиками архивации с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7d44d-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="7d44d-118">Управлять политиками архивации можно также с помощью командлетов Windows PowerShell, приведенных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="7d44d-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="7d44d-119">Подробные сведения о синтаксисе, включая все доступные параметры, можно найти в [командной консоли Skype для бизнеса Server](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="7d44d-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="7d44d-120">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="7d44d-120">**Cmdlet**</span></span>|<span data-ttu-id="7d44d-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="7d44d-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7d44d-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="7d44d-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="7d44d-123">Возвращает сведения о политиках архивации для сеансов обмена мгновенными сообщениями (IM) в организации.</span><span class="sxs-lookup"><span data-stu-id="7d44d-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="7d44d-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="7d44d-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="7d44d-125">Назначает политики архивации для сеанса обмена мгновенными сообщениями для пользователей или групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="7d44d-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="7d44d-126">Эти политики позволяют архивировать все сеансы обмена мгновенными сообщениями между внутренними пользователями и между внутренними и внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="7d44d-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="7d44d-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="7d44d-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="7d44d-128">Создает новые политики архивации сеансов обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="7d44d-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="7d44d-129">Эти политики позволяют архивировать все сеансы обмена мгновенными сообщениями между внутренними пользователями, а также все сеансы обмена мгновенными сообщениями между внутренними пользователями и внешними партнерами.</span><span class="sxs-lookup"><span data-stu-id="7d44d-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="7d44d-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="7d44d-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="7d44d-131">Удаление политики архивации сообщений, которая определяет, будет ли Skype для бизнеса Server автоматически сохранять все сеансы обмена мгновенными сообщениями между внутренними пользователями и (или) всеми сеансами обмена мгновенными сообщениями между внутренними пользователями и федеративными партнерами.</span><span class="sxs-lookup"><span data-stu-id="7d44d-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="7d44d-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="7d44d-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="7d44d-133">Изменение существующей политики архивации мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="7d44d-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="7d44d-134">Политика архивации позволяет архивировать все сеансы обмена мгновенными сообщениями и конференции, выполняемые между внутренними пользователями; Вы также можете архивировать сеансы, выполняемые между внутренними пользователями и федеративными партнерами.</span><span class="sxs-lookup"><span data-stu-id="7d44d-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

