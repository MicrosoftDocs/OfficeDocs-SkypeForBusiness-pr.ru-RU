---
title: Узел области применения корня Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.RootScopeNode
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d190f1f0-7741-432a-84ac-9530bb00abef
ROBOTS: NOINDEX, NOFOLLOW
description: Узел Lync Server содержит список центральных сайтов в вашей топологии. Доступны следующие действия.
ms.openlocfilehash: 88d134879e98cf0e17589eb86ede4c88d58a8950
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795280"
---
# <a name="skype-for-business-server-root-scope-node"></a><span data-ttu-id="b0507-104">Узел области применения корня Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="b0507-104">Skype for Business Server Root Scope Node</span></span>
 
<span data-ttu-id="b0507-105">Узел **Lync Server** содержит список центральных сайтов в вашей топологии.</span><span class="sxs-lookup"><span data-stu-id="b0507-105">The **Lync Server** node lists the central sites in your topology.</span></span> <span data-ttu-id="b0507-106">Можно выполнить следующие действия.</span><span class="sxs-lookup"><span data-stu-id="b0507-106">You can perform the following actions:</span></span>
  
- <span data-ttu-id="b0507-p103">**Создать центральный сайт**. Запуск мастера "Определение нового центрального сайта", для добавления к топологии нового центрального сайта.</span><span class="sxs-lookup"><span data-stu-id="b0507-p103">**New Central Site**. Starts the Define New Central Site wizard, which you use to add a new central site to the topology.</span></span>
    
- <span data-ttu-id="b0507-p104">**Изменить свойства**. Изменение свойств, влияющих на топологию в целом, включая поддерживаемые домены SIP и простые URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="b0507-p104">**Edit Properties**. Enables you to edit settings that affect your whole topology, such as supported Session Initiation Protocol (SIP) domains and simple URLs.</span></span>
    
- <span data-ttu-id="b0507-p105">**Создать топологию**. Запуск процедуры создания новой топологии для развертывания. Это действие удобно при планировании развертывания перед установкой серверов. Его не следует выбирать, если текущая топология уже применена при установке развертывания.</span><span class="sxs-lookup"><span data-stu-id="b0507-p105">**New Topology**. Enables you to start creating a new topology for your deployment. This option is useful when you are planning your deployment, before you have installed your servers. Do not click this option if you have already used your current topology to install your deployment.</span></span>
    
- <span data-ttu-id="b0507-p106">**Открыть топологию**. Открытие сохраненного файла топологии.</span><span class="sxs-lookup"><span data-stu-id="b0507-p106">**Open Topology**. Opens a topology file that you have saved.</span></span>
    
- <span data-ttu-id="b0507-p107">**Загрузить топологию**. Загрузка развернутой на данный момент топологии из центрального хранилища управления. Если топология уже определена, а центральное хранилище управления установлено, это действие следует выбирать каждый раз при загрузке топологии.</span><span class="sxs-lookup"><span data-stu-id="b0507-p107">**Download Topology**. Loads your current deployed topology from the Central Management store. If you have already defined a topology and established the Central Management store, you should always choose this option to load your topology.</span></span>
    
- <span data-ttu-id="b0507-120">**Сохранить копию топологии как**.</span><span class="sxs-lookup"><span data-stu-id="b0507-120">**Save a Copy of Topology As**.</span></span> <span data-ttu-id="b0507-121">Сохраняет текущую топологию в файл, который можно позже загрузить в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="b0507-121">Saves the current topology to a file that you can load again later in Topology Builder.</span></span>
    
- <span data-ttu-id="b0507-p109">**Опубликовать топологию**. Публикация топологии в центральном хранилище управления, позволяющая приступить к развертыванию серверов.</span><span class="sxs-lookup"><span data-stu-id="b0507-p109">**Publish Topology**. Use this option to publish this topology to the Central Management store, so that you can begin deploying your servers.</span></span>
    
- <span data-ttu-id="b0507-p110">**Установить базу данных**. Создание баз данных, необходимых для развертывания.</span><span class="sxs-lookup"><span data-stu-id="b0507-p110">**Install Database**. Enables you to create the databases necessary for your deployment.</span></span>
    
- <span data-ttu-id="b0507-126">**Объединить топологию Office Communications Server 2007 R2**.</span><span class="sxs-lookup"><span data-stu-id="b0507-126">**Merge Office Communications Server 2007 R2 Topology**.</span></span> <span data-ttu-id="b0507-127">Запуск мастер объединения в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="b0507-127">Starts the Topology Builder Merge wizard.</span></span> <span data-ttu-id="b0507-128">Это средство собирает данные о предыдущей среде Office Communications Server, в том числе сведения о пограничном сервере, и публикует эти данные в общей базе данных.</span><span class="sxs-lookup"><span data-stu-id="b0507-128">This tool collects information about your previous Office Communications Server environment, including Edge Server information, and publishes that information to a shared database.</span></span> 
    
- <span data-ttu-id="b0507-p112">**Удалить развертывание**. Запуск мастера удаления развертывания, позволяющего удалить развертывание целиком.</span><span class="sxs-lookup"><span data-stu-id="b0507-p112">**Remove Deployment**. Starts the Remove Deployment wizard, which enables you to start removing your whole deployment.</span></span>
    
<span data-ttu-id="b0507-131">Кроме работы с этими параметрами, вы можете выполнять следующие задачи общего характера:</span><span class="sxs-lookup"><span data-stu-id="b0507-131">In addition to these options, you can perform the following general tasks:</span></span>
  
- <span data-ttu-id="b0507-p113">**Вид**. Эта команда позволяет настроить представление построителя топологий путем выбора элементов для отображения и скрытия в представлениях дерева консоли.</span><span class="sxs-lookup"><span data-stu-id="b0507-p113">**View**. You can use this option to customize the view of Topology Builder by selecting the items to show and hide in the console tree views.</span></span>
    
- <span data-ttu-id="b0507-p114">**Справка**. Эта команда обеспечивает доступ к справке по активному узлу.</span><span class="sxs-lookup"><span data-stu-id="b0507-p114">**Help**. You can use this option to access Help for the active node.</span></span>
    

