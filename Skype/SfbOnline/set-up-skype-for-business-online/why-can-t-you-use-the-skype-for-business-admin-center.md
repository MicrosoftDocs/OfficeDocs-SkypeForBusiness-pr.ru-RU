---
title: Почему я не могу использовать центр администрирования Skype для бизнеса Online прямо сейчас?
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
f1keywords:
- ms.lync.lac.TenantInMigration
ms.custom:
- Setup
description: 'Сведения о том, что можно и не может использовать в центре администрирования Skype для бизнеса, а также о других функциях, выполняемых при миграции службы в другой центр обработки данных Майкрософт. '
ms.openlocfilehash: 006caf6542abfeeb38e9563b6866fb119c47b88f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34284880"
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="f1848-103">Почему я не могу использовать центр администрирования Skype для бизнеса Online прямо сейчас?</span><span class="sxs-lookup"><span data-stu-id="f1848-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="f1848-104">Мы знаем, что вы не можете приступить к работе, поэтому мы будем рады объяснить, что происходит здесь, и зачем это стоит ждать.</span><span class="sxs-lookup"><span data-stu-id="f1848-104">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="f1848-105">Для начала сделайте следующее:</span><span class="sxs-lookup"><span data-stu-id="f1848-105">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="f1848-106">Мы переносим службу Skype для бизнеса Online (например, ваши пользователи и организационные параметры) на другой центр обработки данных Майкрософт, который ближе к вам.</span><span class="sxs-lookup"><span data-stu-id="f1848-106">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="f1848-107">Это повысит качество обслуживания и сократит задержку.</span><span class="sxs-lookup"><span data-stu-id="f1848-107">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="f1848-108">Дополнительные технические сведения можно найти в разделе [время и после перемещения данных]( https://go.microsoft.com/fwlink/?LinkId=526418).</span><span class="sxs-lookup"><span data-stu-id="f1848-108">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="f1848-109">Да, так что это означает?</span><span class="sxs-lookup"><span data-stu-id="f1848-109">OK, so what does that mean?</span></span>

<span data-ttu-id="f1848-110">Для начала рассмотрим несколько терминов.</span><span class="sxs-lookup"><span data-stu-id="f1848-110">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="f1848-111">**Центр обработки данных** Это физическое расположение, в котором хранятся сведения из организации Office 365, такие как файлы и сообщения электронной почты.</span><span class="sxs-lookup"><span data-stu-id="f1848-111">**Data center** This is the physical location where the information from your Office 365 organization is stored, such as your files and email messages.</span></span> <span data-ttu-id="f1848-112">Если вы действительно хотите узнать, какие приложения Office 365 являются центрами обработки данных, ознакомьтесь с[этой статьей](https://www.microsoft.com/online/legal/v2/?docid=25).</span><span class="sxs-lookup"><span data-stu-id="f1848-112">If you really want to dig in to what Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="f1848-113">**Миграция** Это так же, как "перемещение".</span><span class="sxs-lookup"><span data-stu-id="f1848-113">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="f1848-114">В этом случае вы перемещаете пользователей и параметры Skype для бизнеса Online из одного центра обработки данных в другое, чтобы улучшить работу службы.</span><span class="sxs-lookup"><span data-stu-id="f1848-114">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="f1848-115">**Задержка** Это время, необходимое для доступа к центру администрирования Office 365, изменения параметров и сохранения этих изменений.</span><span class="sxs-lookup"><span data-stu-id="f1848-115">**Latency** This is amount of time it takes you to access the Office 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="f1848-116">**Идентификатор корреляции** Возможно, вы увидели это в сообщении, которое вы только что отправили.</span><span class="sxs-lookup"><span data-stu-id="f1848-116">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="f1848-117">Эти сведения используются специалистами службы поддержки Майкрософт, чтобы помочь вам устранить ошибки.</span><span class="sxs-lookup"><span data-stu-id="f1848-117">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="f1848-118">При обращении в службу поддержки Майкрософт может потребоваться идентификатор корреляции.</span><span class="sxs-lookup"><span data-stu-id="f1848-118">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="f1848-119">Итак, что это значит! мы перемещая всех пользователей и параметры службы Skype для бизнеса Online в другое расположение, которое находится ближе к вам.</span><span class="sxs-lookup"><span data-stu-id="f1848-119">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="f1848-120">Чем ближе лучше.</span><span class="sxs-lookup"><span data-stu-id="f1848-120">The closer the better.</span></span> <span data-ttu-id="f1848-121">Хорошая новость состоит в том, что по истечении этого короткого промежутка времени служба Skype для бизнеса Online будет улучшена.</span><span class="sxs-lookup"><span data-stu-id="f1848-121">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Миграция служб в Office 365](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="f1848-123">Какие функции Skype для бизнеса Online будут работать?</span><span class="sxs-lookup"><span data-stu-id="f1848-123">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="f1848-124">Несмотря на то, что вы не сможете получить доступ к центру администрирования Skype для бизнеса Online, в процессе миграции будут по-прежнему работать указанные ниже функции Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="f1848-124">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="f1848-125">Собрания по сети</span><span class="sxs-lookup"><span data-stu-id="f1848-125">Online meetings</span></span>
    
- <span data-ttu-id="f1848-126">Сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="f1848-126">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="f1848-127">Можно ли сделать другую работу?</span><span class="sxs-lookup"><span data-stu-id="f1848-127">Can I get other work done?</span></span>

<span data-ttu-id="f1848-128">Гарантировать.</span><span class="sxs-lookup"><span data-stu-id="f1848-128">Sure.</span></span> <span data-ttu-id="f1848-129">Несмотря на то что мы переносим службу Skype для бизнеса Online, вы по-прежнему можете использовать другие центры администрирования в Office 365 (например, центр администрирования Office 365 и Exchange).</span><span class="sxs-lookup"><span data-stu-id="f1848-129">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Office 365 (for example, the Office 365 and Exchange admin centers).</span></span> <span data-ttu-id="f1848-130">Однако вместе с центром администрирования Skype для бизнеса Online вы не сможете использовать удаленные командлеты PowerShell в Skype для бизнеса Online во время миграции.</span><span class="sxs-lookup"><span data-stu-id="f1848-130">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="f1848-131">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f1848-131">Related topics</span></span>
[<span data-ttu-id="f1848-132">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="f1848-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="f1848-133">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f1848-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)

  
 
