---
title: Почему я не могу использовать Центр администрирования Skype для бизнеса Online?
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c182d564-1674-4491-b1d9-3e0cb657d4cc
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- CSH
ms.custom:
- Setup
- ms.lync.lac.TenantInMigration
description: 'Узнайте, что можно и нельзя использовать в Skype для бизнеса администрирования и других функций при переносе службы в другой центр обработки данных Майкрософт. '
ms.openlocfilehash: 725a60be96a2d61bcec6367e1a0a33f2bc5dcee6
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238920"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="8da59-103">Почему я не могу использовать Центр администрирования Skype для бизнеса Online?</span><span class="sxs-lookup"><span data-stu-id="8da59-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="8da59-104">[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]?</span><span class="sxs-lookup"><span data-stu-id="8da59-104">[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]?</span></span>

<span data-ttu-id="8da59-105">Мы знаем, что вам не получается ничего сделать, поэтому мы объявим, что происходит и почему стоит немного подождать.</span><span class="sxs-lookup"><span data-stu-id="8da59-105">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="8da59-106">Во-первых, это техническое объяснение:</span><span class="sxs-lookup"><span data-stu-id="8da59-106">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="8da59-107">Мы переносим вашу службу Skype для бизнеса Online (т. е. пользователей и параметры организации) в другой центр обработки данных Майкрософт, который ближе к вам.</span><span class="sxs-lookup"><span data-stu-id="8da59-107">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="8da59-108">Это повысит качество обслуживания и сократит задержки.</span><span class="sxs-lookup"><span data-stu-id="8da59-108">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="8da59-109">Дополнительные технические сведения см. в сведениях О ходе [и после перемещения данных.]( https://go.microsoft.com/fwlink/?LinkId=526418)</span><span class="sxs-lookup"><span data-stu-id="8da59-109">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="8da59-110">Итак, что это означает?</span><span class="sxs-lookup"><span data-stu-id="8da59-110">OK, so what does that mean?</span></span>

<span data-ttu-id="8da59-111">Во-первых, давайте разопустим несколько терминов.</span><span class="sxs-lookup"><span data-stu-id="8da59-111">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="8da59-112">**Центр обработки данных** Это физическое расположение, в котором хранятся Microsoft 365 или Office 365, например файлы и сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="8da59-112">**Data center** This is the physical location where the information from your Microsoft 365 or Office 365 is stored, such as your files and email messages.</span></span> <span data-ttu-id="8da59-113">Если вы действительно хотите узнать, что Microsoft 365 и Office 365 центрах обработки данных, ознакомьтесь с[этой статьей.](https://www.microsoft.com/online/legal/v2/?docid=25)</span><span class="sxs-lookup"><span data-stu-id="8da59-113">If you really want to dig in to what Microsoft 365 and Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="8da59-114">**Миграция** Это почти то же самое, что и перемещение.</span><span class="sxs-lookup"><span data-stu-id="8da59-114">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="8da59-115">В этом случае это означает, что мы перемещаем пользователей Skype для бизнеса Online и параметры из одного центра обработки данных в другой, который ближе к вам, чтобы улучшить службу.</span><span class="sxs-lookup"><span data-stu-id="8da59-115">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="8da59-116">**Задержка** Это время, необходимое для доступа к центру Microsoft 365 администрирования, внесения изменений в параметры и сохранения этих изменений.</span><span class="sxs-lookup"><span data-stu-id="8da59-116">**Latency** This is amount of time it takes you to access the Microsoft 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="8da59-117">**ИД корреляции** Возможно, вы видели это в сообщении, которое вы только что прибыли.</span><span class="sxs-lookup"><span data-stu-id="8da59-117">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="8da59-118">Эти сведения используются инженерами службы поддержки Майкрософт для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="8da59-118">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="8da59-119">Если вы обратитесь в службу поддержки Майкрософт, вам может потребоваться у вас получить ид корреляции.</span><span class="sxs-lookup"><span data-stu-id="8da59-119">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="8da59-120">Все это означает, что мы сейчас перемещаем всех ваших пользователей Skype для бизнеса Online и параметры службы в другое расположение, которое находится ближе к вам.</span><span class="sxs-lookup"><span data-stu-id="8da59-120">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="8da59-121">Чем ближе, тем лучше.</span><span class="sxs-lookup"><span data-stu-id="8da59-121">The closer the better.</span></span> <span data-ttu-id="8da59-122">Хорошая новость заключается в том, что по иным коротким периодам ваша Skype для бизнеса online-служба улучшится.</span><span class="sxs-lookup"><span data-stu-id="8da59-122">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Миграция служб в Microsoft 365 или Office 365](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="8da59-124">Какие Skype для бизнеса по-прежнему будут работать?</span><span class="sxs-lookup"><span data-stu-id="8da59-124">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="8da59-125">Хотя вы не сможете получить доступ к Центру администрирования Skype для бизнеса Online, во время миграции по-прежнему будут работать следующие Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="8da59-125">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="8da59-126">Собрания по сети</span><span class="sxs-lookup"><span data-stu-id="8da59-126">Online meetings</span></span>
    
- <span data-ttu-id="8da59-127">Сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="8da59-127">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="8da59-128">Можно ли еще поработать над этой работой?</span><span class="sxs-lookup"><span data-stu-id="8da59-128">Can I get other work done?</span></span>

<span data-ttu-id="8da59-129">Уверен.</span><span class="sxs-lookup"><span data-stu-id="8da59-129">Sure.</span></span> <span data-ttu-id="8da59-130">Пока мы переносим вашу службу Skype для бизнеса Online, вы по-прежнему можете использовать другие центры администрирования Microsoft 365 (например, Microsoft 365 и Exchange администрирования).</span><span class="sxs-lookup"><span data-stu-id="8da59-130">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Microsoft 365 (for example, the Microsoft 365 and Exchange admin centers).</span></span> <span data-ttu-id="8da59-131">Однако наряду с центром Skype для бизнеса Online вы не сможете использовать Skype для бизнеса Online Remote PowerShell во время миграции.</span><span class="sxs-lookup"><span data-stu-id="8da59-131">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="8da59-132">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8da59-132">Related topics</span></span>
[<span data-ttu-id="8da59-133">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="8da59-133">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="8da59-134">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="8da59-134">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
