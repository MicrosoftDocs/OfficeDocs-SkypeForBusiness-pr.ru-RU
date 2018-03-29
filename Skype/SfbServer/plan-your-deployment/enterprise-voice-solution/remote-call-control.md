---
title: Планирование удаленного управления звонками в Skype для бизнеса 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/16/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Удаленное управление звонками была компонента в предыдущих версиях Lync Server, который позволяет пользователям управлять телефонах УАТС с Lync Server. В Скайп Business Server этот компонент был заменен звонок с помощью рабочих. В версии клиента для Скайп Business Server 2015 и переход вперед, удаленного вызова элемента управления больше не доступен для настройки в клиенте и была удалена для использования.
ms.openlocfilehash: 2db859ad33a697d5bca632ca9b6677a3a67bd103
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-remote-call-control-in-skype-for-business-2015"></a><span data-ttu-id="0b331-105">Планирование удаленного управления звонками в Skype для бизнеса 2015</span><span class="sxs-lookup"><span data-stu-id="0b331-105">Plan for remote call control in Skype for Business 2015</span></span>
 
<span data-ttu-id="0b331-106">Удаленное управление звонками была компонента в предыдущих версиях Lync Server, который позволяет пользователям управлять телефонах УАТС с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0b331-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="0b331-107">В Скайп Business Server этот компонент был заменен звонок с помощью рабочих.</span><span class="sxs-lookup"><span data-stu-id="0b331-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="0b331-108">*В версии клиента для Скайп Business Server 2015 и переход вперед, удаленного вызова элемента управления больше не доступен для настройки в клиенте и была удалена для использования.*</span><span class="sxs-lookup"><span data-stu-id="0b331-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="0b331-109">Удаленного центра управления пользователи в вашей организации, которые размещаются на интерфейсных серверах под управлением Lync Server по-прежнему для использования удаленного управления звонками, даже в том случае, если они используют Скайп для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="0b331-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="0b331-110">Тем не менее для всех пользователей, размещенных на Скайп для Business Server, удаленное управление звонками не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0b331-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="0b331-111">В следующей таблице для сочетания клиент сервер и ли они поддерживают удаленное управление звонками или звонок с рабочего.</span><span class="sxs-lookup"><span data-stu-id="0b331-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="0b331-112">**Скайп для бизнеса 2015 клиента With Скайп пользовательского интерфейса включен**</span><span class="sxs-lookup"><span data-stu-id="0b331-112">**Skype for Business 2015 Client With Skype UI enabled**</span></span>|<span data-ttu-id="0b331-113">**Скайп для бизнеса 2015 клиента With Lync пользовательского интерфейса включен**</span><span class="sxs-lookup"><span data-stu-id="0b331-113">**Skype for Business 2015 Client With Lync UI enabled**</span></span>|<span data-ttu-id="0b331-114">**Скайп для бизнеса 2016 клиента**</span><span class="sxs-lookup"><span data-stu-id="0b331-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="0b331-115">**Клиент Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="0b331-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="0b331-116">**Клиент Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="0b331-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0b331-117">Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="0b331-117">Skype for Business Server 2015</span></span> <br/> |<span data-ttu-id="0b331-118">Вызов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="0b331-118">Call via Work</span></span>  <br/> |<span data-ttu-id="0b331-119">1</span><span class="sxs-lookup"><span data-stu-id="0b331-119">1</span></span> <br/> |<span data-ttu-id="0b331-120">Вызов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="0b331-120">Call via Work</span></span>  <br/> |<span data-ttu-id="0b331-121">1</span><span class="sxs-lookup"><span data-stu-id="0b331-121">1</span></span> <br/> |<span data-ttu-id="0b331-122">1</span><span class="sxs-lookup"><span data-stu-id="0b331-122">1</span></span> <br/> |
| <span data-ttu-id="0b331-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b331-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="0b331-124">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="0b331-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="0b331-125">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="0b331-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="0b331-126">1</span><span class="sxs-lookup"><span data-stu-id="0b331-126">1</span></span> <br/> |<span data-ttu-id="0b331-127">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="0b331-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="0b331-128">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="0b331-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="0b331-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0b331-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="0b331-130">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="0b331-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="0b331-131">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="0b331-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="0b331-132">1</span><span class="sxs-lookup"><span data-stu-id="0b331-132">1</span></span> <br/> |<span data-ttu-id="0b331-133">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="0b331-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="0b331-134">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="0b331-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="0b331-135">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="0b331-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="0b331-136">Для получения дополнительных сведений см [Удаленный центр управления звонками](https://go.microsoft.com/fwlink/p/?LinkId=530208) в документации по Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0b331-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0b331-137">См. также</span><span class="sxs-lookup"><span data-stu-id="0b331-137">See also</span></span>

#### 

[<span data-ttu-id="0b331-138">Планирование позвонить с рабочего в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0b331-138">Plan for Call Via Work in Skype for Business Server 2015</span></span>](call-via-work.md)
  
[<span data-ttu-id="0b331-139">Сравнение функций для настольных компьютеров для Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="0b331-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)
#### 

[<span data-ttu-id="0b331-140">Сделать Скайп для вызова бизнеса, но использовать стационарный телефон УАТС для аудио</span><span class="sxs-lookup"><span data-stu-id="0b331-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

