---
title: Конфигурация архивирования
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: 'Использование конфигураций архивирования для управления параметрами для вашей Скайп для развертывания Business Server, среди которых включение и отключение следующих параметров архивирования:'
ms.openlocfilehash: 4d618e8fe31b0bdef85c4ef2cbd606818850cadc
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874097"
---
# <a name="archiving-configuration"></a><span data-ttu-id="a78bf-103">Конфигурация архивирования</span><span class="sxs-lookup"><span data-stu-id="a78bf-103">Archiving Configuration</span></span>
 
<span data-ttu-id="a78bf-104">Использование конфигураций архивирования для управления параметрами для вашей Скайп для развертывания Business Server, среди которых включение и отключение следующих параметров архивирования:</span><span class="sxs-lookup"><span data-stu-id="a78bf-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="a78bf-105">Блокирование сеансов обмена мгновенными сообщениями или конференц-связи, если возникает сбой архивирования</span><span class="sxs-lookup"><span data-stu-id="a78bf-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="a78bf-106">Интеграция с хранилищем Exchange 2013, для пользователей, размещенных на сервере Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="a78bf-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="a78bf-107">Удаление архивных данных</span><span class="sxs-lookup"><span data-stu-id="a78bf-107">Purging of archived data</span></span>
    
<span data-ttu-id="a78bf-108">Конфигурации архивирования включают глобальную конфигурацию и, возможно, одну или несколько конфигураций архивирования сайта или пула:</span><span class="sxs-lookup"><span data-stu-id="a78bf-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="a78bf-109">**Глобальная конфигурация** Глобальная конфигурация создается по умолчанию в все Скайп для развертываний Business Server.</span><span class="sxs-lookup"><span data-stu-id="a78bf-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="a78bf-110">Глобальную конфигурацию можно отредактировать, но удалить эту конфигурацию архивирования невозможно.</span><span class="sxs-lookup"><span data-stu-id="a78bf-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="a78bf-111">Если попытаться удалить ее, все параметры сбрасываются до значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a78bf-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="a78bf-112">**Настройка сайта (необязательно)** Можно указать один или несколько сайтов конфигураций архивирования, каждая из которых можно настроить для управления параметрами для определенного сайта архивирования.</span><span class="sxs-lookup"><span data-stu-id="a78bf-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="a78bf-113">Конфигурация сайта переопределяет глобальную конфигурацию, но только для тех сайтов, которые указаны в конфигурациях архивирования сайтов.</span><span class="sxs-lookup"><span data-stu-id="a78bf-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="a78bf-114">Конфигурации сайта можно редактировать или удалять.</span><span class="sxs-lookup"><span data-stu-id="a78bf-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="a78bf-115">**Конфигурация пула (необязательно)** Можно указать один или несколько пула конфигурации архивации, для управления параметрами для конкретного пула архивирования.</span><span class="sxs-lookup"><span data-stu-id="a78bf-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="a78bf-116">Конфигурация пула переопределяет глобальную конфигурацию и конфигурацию сайта, но только для тех пулов, которые указаны в конфигурациях архивирования пулов.</span><span class="sxs-lookup"><span data-stu-id="a78bf-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="a78bf-117">Конфигурации пула можно редактировать или удалять.</span><span class="sxs-lookup"><span data-stu-id="a78bf-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="a78bf-118">Архивации конфигурации относятся к пользователям, размещенных на Скайп для Business Server и, при использовании Exchange для хранения архивных данных в Microsoft Exchange для пользователей, размещенных на сервере Exchange 2013, но немного по-разному реализованы для пользователей, размещенных на сервере Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="a78bf-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="a78bf-119">Различия описаны в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="a78bf-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="a78bf-p105">На странице **Конфигурация архивирования** перечислены все политики архивирования, которые настроены для развертывания. Здесь также показано имя политики, область действия (глобальная, сайта или пула) и то, какие параметры архивирования включены для конфигурации архивирования. На странице **Конфигурация архивирования** предоставлены следующие варианты действий:</span><span class="sxs-lookup"><span data-stu-id="a78bf-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="a78bf-123">**Новые** Можно добавить одну или несколько следующих дополнительных конфигураций архивирования.</span><span class="sxs-lookup"><span data-stu-id="a78bf-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="a78bf-124">Конфигурация сайта</span><span class="sxs-lookup"><span data-stu-id="a78bf-124">Site configuration</span></span>
    
  - <span data-ttu-id="a78bf-125">Конфигурация пула</span><span class="sxs-lookup"><span data-stu-id="a78bf-125">Pool configuration</span></span>
    
- <span data-ttu-id="a78bf-126">**Изменение** Можно изменить параметры всех конфигураций архивирования, перечисленных на странице.</span><span class="sxs-lookup"><span data-stu-id="a78bf-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="a78bf-127">С помощью этого параметра можно выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="a78bf-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="a78bf-128">**Показать подробности** Этот параметр открывает диалоговое окно, в котором можно изменить параметры архивирования для выбранной конфигурации архивации.</span><span class="sxs-lookup"><span data-stu-id="a78bf-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="a78bf-129">Одновременно можно отображать подробности только для одной конфигурации архивирования.</span><span class="sxs-lookup"><span data-stu-id="a78bf-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="a78bf-130">**Выделить все** Этот параметр выбирает все конфигурации архивирования в списке.</span><span class="sxs-lookup"><span data-stu-id="a78bf-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="a78bf-131">**Удаление** Этот параметр удаляет все выбранные конфигурации архивирования.</span><span class="sxs-lookup"><span data-stu-id="a78bf-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="a78bf-132">**Действие** Этот параметр можно использовать для быстрого включения или отключения архивации сеансов обмена мгновенными Сообщениями или сеансы веб-конференции в любой конфигурации, перечисленных на странице, а не для изменения конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a78bf-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="a78bf-133">Параметры, доступные в разделе **Действие**, зависят от того, какой параметр выбран в текущий момент в конфигурации архивирования.</span><span class="sxs-lookup"><span data-stu-id="a78bf-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="a78bf-134">Доступны все параметры, кроме тех, которые включены в конфигурации архивирования в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="a78bf-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="a78bf-135">Параметры включают следующие:</span><span class="sxs-lookup"><span data-stu-id="a78bf-135">Options include the following:</span></span>
    
  - <span data-ttu-id="a78bf-136">**Архивировать сеансы обмена мгновенными сообщениями**</span><span class="sxs-lookup"><span data-stu-id="a78bf-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="a78bf-137">**Архивировать сеансы обмена мгновенными сообщениями и веб-конференций**</span><span class="sxs-lookup"><span data-stu-id="a78bf-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="a78bf-138">**Отключить архивацию**</span><span class="sxs-lookup"><span data-stu-id="a78bf-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="a78bf-139">**Обновление** Можно обновить страницу **Конфигурация архивирования** , чтобы проверить состояние параметров всех конфигураций архивирования.</span><span class="sxs-lookup"><span data-stu-id="a78bf-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="a78bf-140">Подробные сведения о функции архивации и возможностей, включая интеграцию с Exchange в разделе [Планирование архивации в Скайп для Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Развертывание архивации для Скайп для Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)и [Управление архивации в Скайп для Бизнес-2015 сервера](../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="a78bf-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

