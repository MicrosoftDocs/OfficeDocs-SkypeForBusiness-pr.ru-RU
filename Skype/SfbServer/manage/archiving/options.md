---
title: Управление параметров архивации в Скайп для Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Сводка: Сведения о настройке параметров архивации для Скайп для Business Server.'
ms.openlocfilehash: 235a0170a4301e48caeae17b7315a174ca2c8aee
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20993569"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="687d5-103">Управление параметров архивации в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="687d5-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="687d5-104">**Сводка:** Сведения о настройке параметров архивации для Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="687d5-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="687d5-105">Исходно архивация настраивается во время развертывания, однако конфигурации можно изменять, добавлять и удалять и после развертывания.</span><span class="sxs-lookup"><span data-stu-id="687d5-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="687d5-106">Параметры архивации определяют:</span><span class="sxs-lookup"><span data-stu-id="687d5-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="687d5-107">включение или отключение архивации;</span><span class="sxs-lookup"><span data-stu-id="687d5-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="687d5-108">архивацию сеансов обмена мгновенными сообщениями;</span><span class="sxs-lookup"><span data-stu-id="687d5-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="687d5-109">архивацию сеансов веб-конференций;</span><span class="sxs-lookup"><span data-stu-id="687d5-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="687d5-110">блокировку действий, если архивация не включена;</span><span class="sxs-lookup"><span data-stu-id="687d5-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="687d5-111">использование интеграции Exchange;</span><span class="sxs-lookup"><span data-stu-id="687d5-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="687d5-112">настройку удаления и экспорта данных.</span><span class="sxs-lookup"><span data-stu-id="687d5-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="687d5-113">Параметры конфигурации можно указывать на следующих уровнях:</span><span class="sxs-lookup"><span data-stu-id="687d5-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="687d5-114">Настройки глобального уровня, которая создается по умолчанию при развертывании Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="687d5-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="687d5-115">необязательные конфигурации на уровне сайтов, которые указывают, как архивация реализована для конкретных сайтов;</span><span class="sxs-lookup"><span data-stu-id="687d5-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="687d5-116">Дополнительные конфигурации на уровне пула, которые определяют, как архивация реализуется для конкретного пула</span><span class="sxs-lookup"><span data-stu-id="687d5-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="687d5-117">Конфигурацию сайта или пула можно удалить, но удаление глобальной конфигурации невозможно.</span><span class="sxs-lookup"><span data-stu-id="687d5-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="687d5-118">При удалении глобальной конфигурации она автоматически восстанавливает значения по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="687d5-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="687d5-119">Для получения дополнительных сведений о реализации архивации конфигураций и иерархии конфигураций, архивации Просмотр [Планирование архивации в Скайп для Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="687d5-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="687d5-120">Настройка параметров архивации с помощью панели управления</span><span class="sxs-lookup"><span data-stu-id="687d5-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="687d5-121">Параметры архивации можно настроить с помощью панели управления.</span><span class="sxs-lookup"><span data-stu-id="687d5-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="687d5-122">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="687d5-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="687d5-123">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="687d5-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="687d5-124">В левой области навигации щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="687d5-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="687d5-125">Настройка параметров архивации с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="687d5-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="687d5-126">Параметры архивации также можно настроить с помощью командлетов Windows PowerShell, перечисленных в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="687d5-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="687d5-127">Для получения дополнительных сведений о синтаксисе, включая все доступные параметры видеть [Скайп для консоли Business Server](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="687d5-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="687d5-128">**Командлет**</span><span class="sxs-lookup"><span data-stu-id="687d5-128">**Cmdlet**</span></span>|<span data-ttu-id="687d5-129">**Описание**</span><span class="sxs-lookup"><span data-stu-id="687d5-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="687d5-130">Командлет Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="687d5-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="687d5-131">Возвращает сведения о параметрах конфигурации архивации для организации.</span><span class="sxs-lookup"><span data-stu-id="687d5-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="687d5-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="687d5-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="687d5-133">Создает новый набор параметров обмена мгновенными сообщениями (IM), которые можно использовать для включения или выключения автоматического сохранения сеансов обмена мгновенными сообщениями и блокировки любых мгновенных сообщений, архивирование которых невозможно.</span><span class="sxs-lookup"><span data-stu-id="687d5-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="687d5-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="687d5-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="687d5-135">Удаляет указанную коллекцию параметров архивации, которые используются для включения или отключения автоматического сохранения сеансов обмена мгновенными сообщениями, а также для блокирования мгновенных сообщений, архивирование которых невозможно.</span><span class="sxs-lookup"><span data-stu-id="687d5-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="687d5-136">SET-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="687d5-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="687d5-137">Изменяет существующую коллекцию параметров конфигурации архивации обмена мгновенными сообщениями (IM).</span><span class="sxs-lookup"><span data-stu-id="687d5-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |