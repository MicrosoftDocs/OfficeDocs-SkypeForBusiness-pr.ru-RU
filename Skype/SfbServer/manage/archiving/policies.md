---
title: Управление политики архивации из Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 75ce32ba-eb82-4339-9c02-5df5f2c2ebd2
description: 'Сводка: Узнайте, как управлять политиками пользователя для архивации для Скайп для Business Server.'
ms.openlocfilehash: 289902ded6f1530c74f9c945517a3c853c99d364
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30873242"
---
# <a name="manage-archiving-policies-in-skype-for-business-server"></a><span data-ttu-id="d3b62-103">Управление политики архивации из Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="d3b62-103">Manage archiving policies in Skype for Business Server</span></span>

<span data-ttu-id="d3b62-104">**Сводка:** Узнайте, как управлять политиками пользователя для архивации для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="d3b62-104">**Summary:** Learn how to manage user policies for archiving for Skype for Business Server.</span></span>
  
<span data-ttu-id="d3b62-105">Изначально Настройка политик архивации при развертывании архивации, но можно изменять, добавлять и удалять конфигурации после развертывания.</span><span class="sxs-lookup"><span data-stu-id="d3b62-105">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="d3b62-106">Политики архивации определить, следует ли архивировать:</span><span class="sxs-lookup"><span data-stu-id="d3b62-106">Archiving policies determine whether to archive:</span></span> 
  
- <span data-ttu-id="d3b62-107">внутренние коммуникации;</span><span class="sxs-lookup"><span data-stu-id="d3b62-107">Internal communications</span></span>
    
- <span data-ttu-id="d3b62-108">внешние коммуникации.</span><span class="sxs-lookup"><span data-stu-id="d3b62-108">External communications</span></span>
    
<span data-ttu-id="d3b62-109">Политик архивации может быть набор на глобальном, сайта или на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="d3b62-109">Archiving policies can be set at the global, site, or user level.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d3b62-110">Если включена интеграция с Microsoft Exchange для вашего развертывания, управления политик Exchange ли архивации для пользователей, которые размещаются на сервере Exchange и установить их почтовые ящики на хранение на месте.</span><span class="sxs-lookup"><span data-stu-id="d3b62-110">If you enabled Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="d3b62-111">Дополнительные сведения см [Планирование архивации в Скайп для Business Server](../../plan-your-deployment/archiving/archiving.md) и [Настройка интеграции с хранилищем Exchange для Скайп для Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span><span class="sxs-lookup"><span data-stu-id="d3b62-111">For details, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md) and [Configure integration with Exchange storage for Skype for Business Server](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md).</span></span> 
  
## <a name="manage-archiving-policies-by-using-the-control-panel"></a><span data-ttu-id="d3b62-112">Управление политиками архивации с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="d3b62-112">Manage archiving policies by using the Control Panel</span></span>

<span data-ttu-id="d3b62-113">Управлять политиками архивации можно с помощью панели управления. Для этого:</span><span class="sxs-lookup"><span data-stu-id="d3b62-113">You can manage archiving policies by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="d3b62-114">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d3b62-114">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="d3b62-115">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="d3b62-115">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="d3b62-116">В левой области навигации щелкните **Политика архивации**</span><span class="sxs-lookup"><span data-stu-id="d3b62-116">In the left navigation bar, click **Archiving Policy**</span></span>
    
## <a name="manage-archiving-policies-by-using-windows-powershell"></a><span data-ttu-id="d3b62-117">Управление политиками архивации с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d3b62-117">Manage archiving policies by using Windows PowerShell</span></span>

<span data-ttu-id="d3b62-118">Управлять политиками архивации можно также с помощью командлетов Windows PowerShell, приведенных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="d3b62-118">You can also configure archiving policies by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="d3b62-119">Для получения дополнительных сведений о синтаксисе, включая все доступные параметры видеть [Скайп для консоли Business Server](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="d3b62-119">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="d3b62-120">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="d3b62-120">**Cmdlet**</span></span>|<span data-ttu-id="d3b62-121">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d3b62-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d3b62-122">Get-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="d3b62-122">Get-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="d3b62-123">Возвращает сведения о политиках архивации для сеансов обмена мгновенными сообщениями (IM) в организации.</span><span class="sxs-lookup"><span data-stu-id="d3b62-123">Returns information about your organization's instant messaging (IM) sessions archiving policies.</span></span>  <br/> |
|<span data-ttu-id="d3b62-124">Grant-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="d3b62-124">Grant-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="d3b62-125">Назначает политики архивации для сеанса обмена мгновенными сообщениями для пользователей или групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="d3b62-125">Assigns instant messaging (IM) session archiving policies to users or sets of users.</span></span> <span data-ttu-id="d3b62-126">Эти политики позволяют архивировать все сеансы обмена мгновенными сообщениями между внутренними пользователями и между внутренними и внешними пользователями.</span><span class="sxs-lookup"><span data-stu-id="d3b62-126">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="d3b62-127">New-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="d3b62-127">New-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="d3b62-128">Создает новые политики архивации сеансов обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="d3b62-128">Creates new instant messaging (IM) session archiving policies.</span></span> <span data-ttu-id="d3b62-129">Эти политики позволяют архивировать все сеансы обмена мгновенными сообщениями между внутренними пользователями, а также все сеансы обмена мгновенными сообщениями между внутренними пользователями и внешними партнерами.</span><span class="sxs-lookup"><span data-stu-id="d3b62-129">These policies give you the ability to archive all IM sessions that take place between internal users, and/or to archive all IM sessions that take place between internal users and external partners.</span></span>  <br/> |
|<span data-ttu-id="d3b62-130">Remove-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="d3b62-130">Remove-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="d3b62-131">Удаляет указанный обмена мгновенными сообщениями (IM) архивации политику, которая определяет, будет ли Скайп Business Server для автоматического сохранения всех сеансов обмена мгновенными Сообщениями, которые происходят между внутренними пользователями и/или всех сеансов обмена мгновенными Сообщениями между внутренними пользователями и федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="d3b62-131">Removes the specified instant messaging (IM) archiving policy that determines whether Skype for Business Server will automatically save all IM sessions that take place between internal users, and/or all IM sessions between internal users and federated partners.</span></span>  <br/> |
|<span data-ttu-id="d3b62-132">Set-CsArchivingPolicy</span><span class="sxs-lookup"><span data-stu-id="d3b62-132">Set-CsArchivingPolicy</span></span>  <br/> |<span data-ttu-id="d3b62-133">Изменяет существующий обмена мгновенными сообщениями (IM) политика архивации.</span><span class="sxs-lookup"><span data-stu-id="d3b62-133">Modifies an existing instant messaging (IM) archiving policy.</span></span> <span data-ttu-id="d3b62-134">Политики архивации обеспечивает возможность архивирования всех сеансов обмена мгновенными Сообщениями и конференций, которые происходят между внутренними пользователями; также можно архивировать сеансы, которые происходят между внутренними пользователями и федеративных партнеров.</span><span class="sxs-lookup"><span data-stu-id="d3b62-134">An archiving policy gives you the ability to archive all IM sessions and conferences that take place between internal users; you can also archive sessions that take place between internal users and federated partners.</span></span>  <br/> |
   

