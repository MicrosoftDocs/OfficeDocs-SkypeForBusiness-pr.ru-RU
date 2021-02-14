---
title: Управление вариантами архива в Skype для бизнеса Server
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
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: Сводка. Узнайте, как настроить параметры архива для Skype для бизнеса Server.
ms.openlocfilehash: ee0145ac0896e1bbb8d18c6a51116f2ddd75ee05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817539"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="be31d-103">Управление вариантами архива в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="be31d-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="be31d-104">**Сводка:** Узнайте, как настроить параметры архива для Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="be31d-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="be31d-105">Изначально архивация настраивается при развертывании, но после развертывания можно изменять, добавлять и удалять конфигурации.</span><span class="sxs-lookup"><span data-stu-id="be31d-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="be31d-106">Параметры архива определяют, следует ли:</span><span class="sxs-lookup"><span data-stu-id="be31d-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="be31d-107">Включение или отключение архивации</span><span class="sxs-lookup"><span data-stu-id="be31d-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="be31d-108">Архивировать сеансы обмена мгновенными сообщениями</span><span class="sxs-lookup"><span data-stu-id="be31d-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="be31d-109">Архивировать сеансы веб-conferencing</span><span class="sxs-lookup"><span data-stu-id="be31d-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="be31d-110">Блокировка действий, когда архивная работа недоступна</span><span class="sxs-lookup"><span data-stu-id="be31d-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="be31d-111">Использование интеграции Exchange</span><span class="sxs-lookup"><span data-stu-id="be31d-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="be31d-112">Настройка и экспорт данных</span><span class="sxs-lookup"><span data-stu-id="be31d-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="be31d-113">Параметры конфигурации можно указать на следующих уровнях:</span><span class="sxs-lookup"><span data-stu-id="be31d-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="be31d-114">Конфигурация глобального уровня, которая создается по умолчанию при развертывании Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="be31d-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="be31d-115">Необязательные конфигурации на уровне сайта, определяющие реализации архивации для определенного сайта</span><span class="sxs-lookup"><span data-stu-id="be31d-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="be31d-116">Необязательные конфигурации уровня пула, определяющие реализации архивации для определенного пула</span><span class="sxs-lookup"><span data-stu-id="be31d-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="be31d-117">Вы можете удалить конфигурацию сайта или пула, но не глобальную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="be31d-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="be31d-118">Если вы все же удалите глобальную конфигурацию, параметрам будут автоматически присвоены значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="be31d-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="be31d-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="be31d-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="be31d-120">Настройка параметров архива с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="be31d-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="be31d-121">С помощью панели управления можно настроить параметры архива следующим образом:</span><span class="sxs-lookup"><span data-stu-id="be31d-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="be31d-122">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="be31d-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="be31d-123">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="be31d-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="be31d-124">В левой панели навигации щелкните **"Конфигурация архивации".**</span><span class="sxs-lookup"><span data-stu-id="be31d-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="be31d-125">Настройка параметров архива с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="be31d-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="be31d-126">Вы также можете настроить параметры архива с помощью Windows PowerShell, перечисленных в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="be31d-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="be31d-127">Подробные сведения о синтаксисе, включая все доступные параметры, см. в руководстве [Skype для бизнеса Server Management Shell.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="be31d-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="be31d-128">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="be31d-128">**Cmdlet**</span></span>|<span data-ttu-id="be31d-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="be31d-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="be31d-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="be31d-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="be31d-131">Возвращает сведения о параметрах конфигурации архивации в организации.</span><span class="sxs-lookup"><span data-stu-id="be31d-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="be31d-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="be31d-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="be31d-133">Создает новый набор параметров обмена мгновенными сообщениями, которые можно использовать для автоматического сохранения сеансов обмена мгновенными сообщениями и блокировки любых мгновенных сообщений, которые невозможно архивировать.</span><span class="sxs-lookup"><span data-stu-id="be31d-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="be31d-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="be31d-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="be31d-135">Удаляет указанную коллекцию параметров архива, используемых для автоматического сохранения сеансов обмена мгновенными сообщениями, а также для блокировки любых мгновенных сообщений, которые невозможно архивировать.</span><span class="sxs-lookup"><span data-stu-id="be31d-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="be31d-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="be31d-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="be31d-137">Изменяет существующую коллекцию параметров конфигурации архивации обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="be31d-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
