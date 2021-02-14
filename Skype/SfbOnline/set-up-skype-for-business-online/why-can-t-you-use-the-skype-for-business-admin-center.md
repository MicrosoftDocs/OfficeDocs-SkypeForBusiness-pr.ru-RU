---
title: Почему в настоящее время нельзя использовать Центр администрирования Skype для бизнеса Online?
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
description: 'Узнайте, что можно и нельзя использовать в Центре администрирования Skype для бизнеса, а также о других особенностях переноса службы в другой центр обработки данных Майкрософт. '
ms.openlocfilehash: 7258467929663c42bfb6088202511a04613db383
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164498"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="7c16b-103">Почему в настоящее время нельзя использовать Центр администрирования Skype для бизнеса Online?</span><span class="sxs-lookup"><span data-stu-id="7c16b-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="7c16b-104">Мы знаем, что у вас не получается сделать свою работу, поэтому мы объяснить, что происходит и почему стоит немного подождать.</span><span class="sxs-lookup"><span data-stu-id="7c16b-104">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="7c16b-105">Во-первых, это техническое объяснение.</span><span class="sxs-lookup"><span data-stu-id="7c16b-105">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="7c16b-106">Мы переносим вашу службу Skype для бизнеса Online (т. е. пользователей и настройки организации) в другой центр обработки данных Майкрософт, который ближе к вам.</span><span class="sxs-lookup"><span data-stu-id="7c16b-106">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="7c16b-107">Это повысит качество работы службы и сократит задержки.</span><span class="sxs-lookup"><span data-stu-id="7c16b-107">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="7c16b-108">Дополнительные технические сведения см. [в ходе и после перемещения данных.]( https://go.microsoft.com/fwlink/?LinkId=526418)</span><span class="sxs-lookup"><span data-stu-id="7c16b-108">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="7c16b-109">Итак, что это означает?</span><span class="sxs-lookup"><span data-stu-id="7c16b-109">OK, so what does that mean?</span></span>

<span data-ttu-id="7c16b-110">Сначала рассмотрим несколько терминов.</span><span class="sxs-lookup"><span data-stu-id="7c16b-110">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="7c16b-111">**Центр обработки данных** Это физическое расположение, где хранится информация из Microsoft 365 или Office 365, например файлы и сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="7c16b-111">**Data center** This is the physical location where the information from your Microsoft 365 or Office 365 is stored, such as your files and email messages.</span></span> <span data-ttu-id="7c16b-112">Если вы хотите подробнее узнать о центрах обработки данных Microsoft 365 и Office 365, ознакомьтесь с[этой статьей.](https://www.microsoft.com/online/legal/v2/?docid=25)</span><span class="sxs-lookup"><span data-stu-id="7c16b-112">If you really want to dig in to what Microsoft 365 and Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="7c16b-113">**Перенос** Это в значительной степени то же, что и перемещение.</span><span class="sxs-lookup"><span data-stu-id="7c16b-113">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="7c16b-114">В этом случае это означает, что мы переносим пользователей и параметры Skype для бизнеса Online из одного центра обработки данных в другой, который ближе к вам, чтобы улучшить обслуживание.</span><span class="sxs-lookup"><span data-stu-id="7c16b-114">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="7c16b-115">**Задержка** Это время, необходимое для доступа к Центру администрирования Microsoft 365, изменения параметров и сохранения изменений.</span><span class="sxs-lookup"><span data-stu-id="7c16b-115">**Latency** This is amount of time it takes you to access the Microsoft 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="7c16b-116">**Correlation ID (ИД корреляции)** Возможно, вы видели это в сообщении, которое вы только что увидели.</span><span class="sxs-lookup"><span data-stu-id="7c16b-116">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="7c16b-117">Эти сведения используются инженерами службы поддержки Майкрософт для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="7c16b-117">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="7c16b-118">Если вы обратитесь в службу поддержки Майкрософт, вам может потребоваться в этом случае у вас будет запрос.</span><span class="sxs-lookup"><span data-stu-id="7c16b-118">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="7c16b-119">Все это означает, что мы сейчас переносим всех ваших пользователей и параметры службы Skype для бизнеса Online в другое расположение, которое находится ближе к вам.</span><span class="sxs-lookup"><span data-stu-id="7c16b-119">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="7c16b-120">Чем ближе, тем лучше.</span><span class="sxs-lookup"><span data-stu-id="7c16b-120">The closer the better.</span></span> <span data-ttu-id="7c16b-121">Хорошая новость заключается в том, что по и после этого короткого периода времени ваша служба Skype для бизнеса Online улучшится.</span><span class="sxs-lookup"><span data-stu-id="7c16b-121">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Миграция служб в Microsoft 365 или Office 365](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="7c16b-123">Какие функции Skype для бизнеса Online будут по-прежнему работать?</span><span class="sxs-lookup"><span data-stu-id="7c16b-123">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="7c16b-124">Хотя вы не сможете получить доступ к Центру администрирования Skype для бизнеса Online, во время миграции будут по-прежнему работать следующие функции Skype для бизнеса Online:</span><span class="sxs-lookup"><span data-stu-id="7c16b-124">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="7c16b-125">Собрания по сети</span><span class="sxs-lookup"><span data-stu-id="7c16b-125">Online meetings</span></span>
    
- <span data-ttu-id="7c16b-126">Сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="7c16b-126">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="7c16b-127">Можно ли еще поработать над этой работой?</span><span class="sxs-lookup"><span data-stu-id="7c16b-127">Can I get other work done?</span></span>

<span data-ttu-id="7c16b-128">Конечно.</span><span class="sxs-lookup"><span data-stu-id="7c16b-128">Sure.</span></span> <span data-ttu-id="7c16b-129">Пока мы переносим вашу службу Skype для бизнеса Online, вы можете использовать другие центры администрирования в Microsoft 365 (например, Центры администрирования Microsoft 365 и Exchange).</span><span class="sxs-lookup"><span data-stu-id="7c16b-129">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Microsoft 365 (for example, the Microsoft 365 and Exchange admin centers).</span></span> <span data-ttu-id="7c16b-130">Однако вы не сможете использовать при миграции не только Центр администрирования Skype для бизнеса Online, но и удаленный powerShell Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="7c16b-130">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="7c16b-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="7c16b-131">Related topics</span></span>
[<span data-ttu-id="7c16b-132">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="7c16b-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="7c16b-133">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7c16b-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
