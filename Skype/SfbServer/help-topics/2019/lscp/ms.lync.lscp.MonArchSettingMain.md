---
title: Конфигурация архивирования
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: 'С помощью конфигураций архивации можно управлять параметрами архивации для развертывания в Skype для бизнеса Server, в том числе включать и отключать следующие параметры:'
ms.openlocfilehash: 8c585d2a5816f2d29b3f468fd48fa82c36254d5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34291938"
---
# <a name="archiving-configuration"></a><span data-ttu-id="7fd9f-103">Конфигурация архивирования</span><span class="sxs-lookup"><span data-stu-id="7fd9f-103">Archiving Configuration</span></span>
 
<span data-ttu-id="7fd9f-104">С помощью конфигураций архивации можно управлять параметрами архивации для развертывания в Skype для бизнеса Server, в том числе включать и отключать следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="7fd9f-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="7fd9f-105">Блокирование сеансов обмена мгновенными сообщениями или конференц-связи, если возникает сбой архивирования</span><span class="sxs-lookup"><span data-stu-id="7fd9f-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="7fd9f-106">Интеграция с хранилищем Exchange для пользователей, размещенных на Exchange</span><span class="sxs-lookup"><span data-stu-id="7fd9f-106">Integration with Exchange storage, for users homed on Exchange</span></span>
    
- <span data-ttu-id="7fd9f-107">Удаление архивных данных</span><span class="sxs-lookup"><span data-stu-id="7fd9f-107">Purging of archived data</span></span>
    
<span data-ttu-id="7fd9f-108">Конфигурации архивирования включают глобальную конфигурацию и, возможно, одну или несколько конфигураций архивирования сайта или пула:</span><span class="sxs-lookup"><span data-stu-id="7fd9f-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="7fd9f-109">**Глобальная конфигурация** Глобальная конфигурация создается по умолчанию во всех развертываниях Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="7fd9f-110">Глобальную конфигурацию можно отредактировать, но удалить эту конфигурацию архивирования невозможно.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="7fd9f-111">Если попытаться удалить ее, все параметры сбрасываются до значений по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="7fd9f-112">**Настройка сайта (необязательно)** Вы можете указать одну или несколько конфигураций архивации сайта, каждый из которых можно настроить для управления параметрами архивирования для определенного сайта.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="7fd9f-113">Конфигурация сайта переопределяет глобальную конфигурацию, но только для тех сайтов, которые указаны в конфигурациях архивирования сайтов.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="7fd9f-114">Конфигурации сайта можно редактировать или удалять.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="7fd9f-115">**Настройка пула (необязательно)** Вы можете указать одну или несколько конфигураций архивации пула, чтобы управлять параметрами архивации для определенного пула.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="7fd9f-116">Конфигурация пула переопределяет глобальную конфигурацию и конфигурацию сайта, но только для тех пулов, которые указаны в конфигурациях архивирования пулов.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="7fd9f-117">Конфигурации пула можно редактировать или удалять.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="7fd9f-118">Конфигурации архивации применяются к пользователям, находящуюся в Skype для бизнеса Server, и, если вы используете Exchange для хранения данных архивации в Microsoft Exchange, для пользователей, использующих Exchange, но они немного отличаются для пользователей, использующих Exchange.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange but are implemented slightly differently for users homed on Exchange.</span></span> <span data-ttu-id="7fd9f-119">Различия описаны в следующем разделе.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="7fd9f-p105">На странице **Конфигурация архивирования** перечислены все политики архивирования, которые настроены для развертывания. Здесь также показано имя политики, область действия (глобальная, сайта или пула) и то, какие параметры архивирования включены для конфигурации архивирования. На странице **Конфигурация архивирования** предоставлены следующие варианты действий:</span><span class="sxs-lookup"><span data-stu-id="7fd9f-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="7fd9f-123">**Новые** Вы можете добавить одну или несколько из следующих необязательных конфигураций архивации.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="7fd9f-124">Конфигурация сайта</span><span class="sxs-lookup"><span data-stu-id="7fd9f-124">Site configuration</span></span>
    
  - <span data-ttu-id="7fd9f-125">Конфигурация пула</span><span class="sxs-lookup"><span data-stu-id="7fd9f-125">Pool configuration</span></span>
    
- <span data-ttu-id="7fd9f-126">**Изменить** Вы можете изменить параметры любой из конфигураций архивации, указанных на странице.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="7fd9f-127">С помощью этого параметра можно выполнить следующее:</span><span class="sxs-lookup"><span data-stu-id="7fd9f-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="7fd9f-128">**Показать подробности** Этот параметр позволяет открыть диалоговое окно, в котором можно изменить параметры архивации для выбранной конфигурации архивирования.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="7fd9f-129">Одновременно можно отображать подробности только для одной конфигурации архивирования.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="7fd9f-130">**Выделить все** Этот параметр позволяет выбрать все конфигурации архивации в списке.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="7fd9f-131">**Delete (удалить** ) Этот параметр удаляет все выбранные конфигурации архивирования.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="7fd9f-132">**Действие** Этот параметр можно использовать для быстрого включения и отключения архивации сеансов обмена мгновенными сообщениями и сеансов веб-конференций в какой-либо конфигурации, указанной на странице, вместо редактирования конфигурации.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="7fd9f-133">Параметры, доступные в разделе **Действие**, зависят от того, какой параметр выбран в текущий момент в конфигурации архивирования.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="7fd9f-134">Доступны все параметры, кроме тех, которые включены в конфигурации архивирования в текущий момент.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="7fd9f-135">Параметры включают следующие:</span><span class="sxs-lookup"><span data-stu-id="7fd9f-135">Options include the following:</span></span>
    
  - <span data-ttu-id="7fd9f-136">**Архивировать сеансы обмена мгновенными сообщениями**</span><span class="sxs-lookup"><span data-stu-id="7fd9f-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="7fd9f-137">**Архивировать сеансы обмена мгновенными сообщениями и веб-конференций**</span><span class="sxs-lookup"><span data-stu-id="7fd9f-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="7fd9f-138">**Отключить архивацию**</span><span class="sxs-lookup"><span data-stu-id="7fd9f-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="7fd9f-139">**Обновить** Вы можете обновить страницу **конфигурации архивации** , чтобы проверить состояние параметров всех конфигураций архивации.</span><span class="sxs-lookup"><span data-stu-id="7fd9f-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="7fd9f-140">Подробные сведения о функциях и возможностях архивации, включая интеграцию с Exchange, приведены [в разделе Планирование архивации в Skype для бизнеса](../../../plan-your-deployment/archiving/archiving.md)Server, [развертывание архивации в Skype для бизнеса Server](../../../deploy/deploy-archiving/deploy-archiving.md)и [Управление архивацией в Skype для бизнеса Server (сервер](../../../manage/archiving/archiving.md)).</span><span class="sxs-lookup"><span data-stu-id="7fd9f-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

