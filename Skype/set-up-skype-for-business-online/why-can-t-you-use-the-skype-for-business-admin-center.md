---
title: "Почему не удается использовать Скайп для бизнеса в Интернет центра администрирования на данный момент?"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c182d564-1674-4491-b1d9-3e0cb657d4cc
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
f1keywords:
- ms.lync.lac.TenantInMigration
ms.custom:
- Setup
description: "Сведения, которые можно и нельзя использовать в Скайп для бизнеса центра администрирования и других функций при службы переносится в другом центре обработки данных Майкрософт. "
ms.openlocfilehash: b310bdc431edb890002bebd8d79271c78b841b38
ms.sourcegitcommit: 94e32f776364b0aaefe2d2d72062ec1c249eaef3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
# <a name="why-cant-i-use-the-skype-for-business-online-admin-center-right-now"></a><span data-ttu-id="cae5d-103">Почему не удается использовать Скайп для бизнеса в Интернет центра администрирования на данный момент?</span><span class="sxs-lookup"><span data-stu-id="cae5d-103">Why can't I use the Skype for Business Online admin center right now?</span></span>

<span data-ttu-id="cae5d-104">Мы знаем, что не нравится, когда не удается получить задач, поэтому мы собираемся поясняется, что здесь происходит и почему это будет стоит ожидания.</span><span class="sxs-lookup"><span data-stu-id="cae5d-104">We know it's frustrating when you can't get your work done, so we're going to explain what's happening here and why it'll be worth the wait.</span></span> 
  
<span data-ttu-id="cae5d-105">Ниже приводится общее описание:</span><span class="sxs-lookup"><span data-stu-id="cae5d-105">First, here's the technical explanation:</span></span>
  
<span data-ttu-id="cae5d-106">Мы в случае миграции вашей Скайп для бизнеса веб-службами (то есть пользователи и организации параметров) в другом центре обработки данных Майкрософт, расположенном ближе к вам.</span><span class="sxs-lookup"><span data-stu-id="cae5d-106">We're migrating your Skype for Business Online service (meaning your users and organizational settings) to another Microsoft datacenter that's closer to you.</span></span> <span data-ttu-id="cae5d-107">Это улучшение службы и уменьшения задержки.</span><span class="sxs-lookup"><span data-stu-id="cae5d-107">This will improve your service and reduce latency.</span></span> 
  
<span data-ttu-id="cae5d-108">Более подробные технические сведения см [во время и после перемещения данных]( https://go.microsoft.com/fwlink/?LinkId=526418).</span><span class="sxs-lookup"><span data-stu-id="cae5d-108">For more technical details, see [During and after your data move]( https://go.microsoft.com/fwlink/?LinkId=526418).</span></span>
  
## <a name="ok-so-what-does-that-mean"></a><span data-ttu-id="cae5d-109">Да так что это значит?</span><span class="sxs-lookup"><span data-stu-id="cae5d-109">OK, so what does that mean?</span></span>

<span data-ttu-id="cae5d-110">Во-первых давайте разбить несколько терминов.</span><span class="sxs-lookup"><span data-stu-id="cae5d-110">First, let's break down a few terms.</span></span>
  
- <span data-ttu-id="cae5d-111">**Центр обработки данных** Это физическое расположение, где хранятся сведения из вашей организации Office 365, например файлов и сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cae5d-111">**Data center** This is the physical location where the information from your Office 365 organization is stored, such as your files and email messages.</span></span> <span data-ttu-id="cae5d-112">Если Вы действительно хотите подробно изучить что такое Office 365 центров обработки данных, просмотрите[в этой статье](https://www.microsoft.com/online/legal/v2/?docid=25).</span><span class="sxs-lookup"><span data-stu-id="cae5d-112">If you really want to dig in to what Office 365 datacenters are, check out[this article](https://www.microsoft.com/online/legal/v2/?docid=25).</span></span>
    
- <span data-ttu-id="cae5d-113">**Миграция** Это практически то же, что «перемещение».</span><span class="sxs-lookup"><span data-stu-id="cae5d-113">**Migrating** This is pretty much the same as "moving."</span></span> <span data-ttu-id="cae5d-114">В этом случае это означает, что мы перемещаете вашей Скайп для бизнеса в Интернет пользователей и параметров из одного центра обработки данных в другую, ближе к вам для улучшения службы.</span><span class="sxs-lookup"><span data-stu-id="cae5d-114">In this case, it means we're moving your Skype for Business Online users and settings from one datacenter to another that's closer to you to improve your service.</span></span>
    
- <span data-ttu-id="cae5d-115">**Задержка** Это время, необходимое для доступа к центру администрирования Office 365, параметры изменения, а затем сохраните эти изменения.</span><span class="sxs-lookup"><span data-stu-id="cae5d-115">**Latency** This is amount of time it takes you to access the Office 365 admin center, make a settings change, and then save those changes.</span></span>
    
- <span data-ttu-id="cae5d-116">**Идентификатор корреляции** Может было показано, что это указано в сообщение, которое вы только что пришли.</span><span class="sxs-lookup"><span data-stu-id="cae5d-116">**Correlation ID** You might have seen this listed in the message you just came from.</span></span> <span data-ttu-id="cae5d-117">Эти сведения используется сотрудники службы поддержки Майкрософт, чтобы помочь устранить ошибку.</span><span class="sxs-lookup"><span data-stu-id="cae5d-117">This information is used by Microsoft support engineers to help you troubleshoot an error.</span></span> <span data-ttu-id="cae5d-118">Если вы обратиться в службу поддержки Майкрософт, вам может потребоваться ввод корреляции.</span><span class="sxs-lookup"><span data-stu-id="cae5d-118">If you contact Microsoft support, you might be asked for the Correlation ID.</span></span>
    
<span data-ttu-id="cae5d-119">Это значит, все возможности мы вы в процессе перемещения всех Скайп для бизнеса в Интернет пользователей и параметры в другое расположение, которое ближе к вам службы.</span><span class="sxs-lookup"><span data-stu-id="cae5d-119">So what this all means is we're in the process of moving all your Skype for Business Online users and service settings to another location that's closer to you.</span></span> <span data-ttu-id="cae5d-120">Более подробно лучше.</span><span class="sxs-lookup"><span data-stu-id="cae5d-120">The closer the better.</span></span> <span data-ttu-id="cae5d-121">Хорошо то, что после короткий промежуток времени улучшит вашей Скайп для бизнеса веб-службами.</span><span class="sxs-lookup"><span data-stu-id="cae5d-121">The good news is that after this short period of time, your Skype for Business Online service will improve.</span></span>
  
![Служба миграции в Office 365](../images/77502071-36fe-4833-a5ff-3b9ca7676542.png)
  
## <a name="what-skype-for-business-online-features-will-still-work"></a><span data-ttu-id="cae5d-123">Какие Скайп для бизнеса Интернет-компонентов будет по-прежнему работают?</span><span class="sxs-lookup"><span data-stu-id="cae5d-123">What Skype for Business Online features will still work?</span></span>

<span data-ttu-id="cae5d-124">Несмотря на то, что вы не сможет получить доступ к Скайп для бизнеса в Интернет центра администрирования, следующие Скайп для бизнеса Интернет-компонентов по-прежнему будут работать во время миграции.</span><span class="sxs-lookup"><span data-stu-id="cae5d-124">Although you won't be able to access the Skype for Business Online admin center, the following Skype for Business Online features will still work during the migration:</span></span>
  
- <span data-ttu-id="cae5d-125">Собрания по сети</span><span class="sxs-lookup"><span data-stu-id="cae5d-125">Online meetings</span></span>
    
- <span data-ttu-id="cae5d-126">Сведения о присутствии</span><span class="sxs-lookup"><span data-stu-id="cae5d-126">Presence information</span></span>
    
## <a name="can-i-get-other-work-done"></a><span data-ttu-id="cae5d-127">Как получить другие работы?</span><span class="sxs-lookup"><span data-stu-id="cae5d-127">Can I get other work done?</span></span>

<span data-ttu-id="cae5d-128">Что.</span><span class="sxs-lookup"><span data-stu-id="cae5d-128">Sure.</span></span> <span data-ttu-id="cae5d-129">Хотя мы вы переход к Скайп для бизнеса веб-службами, по-прежнему можно использовать другие центры администрирования Office 365 (например, Office 365 и Exchange центры администрирования).</span><span class="sxs-lookup"><span data-stu-id="cae5d-129">While we're migrating your Skype for Business Online service, you can still use the other admin centers in Office 365 (for example, the Office 365 and Exchange admin centers).</span></span> <span data-ttu-id="cae5d-130">Тем не менее а также Скайп для бизнеса в Интернет центра администрирования, не будут иметь возможность использовать Скайп для командлетов Online удаленной оболочки PowerShell Business во время миграции.</span><span class="sxs-lookup"><span data-stu-id="cae5d-130">However, along with the Skype for Business Online admin center, you won't be able to use the Skype for Business Online Remote PowerShell cmdlets during the migration.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="cae5d-131">See also</span><span class="sxs-lookup"><span data-stu-id="cae5d-131">Related topics</span></span>
[<span data-ttu-id="cae5d-132">Настройка Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="cae5d-132">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="cae5d-133">Разрешение на добавление контактов Skype пользователям Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cae5d-133">Let Skype for Business users add Skype contacts</span></span>](let-skype-for-business-users-add-skype-contacts.md)
