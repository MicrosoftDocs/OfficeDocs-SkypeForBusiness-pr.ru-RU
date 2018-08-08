---
title: Планирование удаленного управления звонками в Скайп для бизнеса
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Удаленное управление звонками была компонента в предыдущих версиях Lync Server, который позволяет пользователям управлять телефонах УАТС с Lync Server. В Скайп Business Server этот компонент был заменен звонок с помощью рабочих. В версии клиента для Скайп Business Server 2015 и переход вперед, удаленного вызова элемента управления больше не доступен для настройки в клиенте и была удалена для использования.
ms.openlocfilehash: d2203840672bfc73cf478254b9d115fd0375c902
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "21014545"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="160eb-105">Планирование удаленного управления звонками в Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="160eb-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="160eb-106">Удаленное управление звонками была компонента в предыдущих версиях Lync Server, который позволяет пользователям управлять телефонах УАТС с Lync Server.</span><span class="sxs-lookup"><span data-stu-id="160eb-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="160eb-107">В Скайп Business Server этот компонент был заменен звонок с помощью рабочих.</span><span class="sxs-lookup"><span data-stu-id="160eb-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="160eb-108">*В версии клиента для Скайп Business Server 2015 и переход вперед, удаленного вызова элемента управления больше не доступен для настройки в клиенте и была удалена для использования.*</span><span class="sxs-lookup"><span data-stu-id="160eb-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="160eb-109">Удаленного центра управления пользователи в вашей организации, которые размещаются на интерфейсных серверах под управлением Lync Server по-прежнему для использования удаленного управления звонками, даже в том случае, если они используют Скайп для клиента Business.</span><span class="sxs-lookup"><span data-stu-id="160eb-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="160eb-110">Тем не менее для всех пользователей, размещенных на Скайп для Business Server, удаленное управление звонками не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="160eb-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="160eb-111">В следующей таблице для сочетания клиент сервер и ли они поддерживают удаленное управление звонками или звонок с рабочего.</span><span class="sxs-lookup"><span data-stu-id="160eb-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="160eb-112">**Скайп для бизнеса клиента с Скайп пользовательского интерфейса включен**</span><span class="sxs-lookup"><span data-stu-id="160eb-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="160eb-113">**Скайп для бизнеса клиента с Lync пользовательского интерфейса включен**</span><span class="sxs-lookup"><span data-stu-id="160eb-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="160eb-114">**Скайп для бизнеса 2016 клиента**</span><span class="sxs-lookup"><span data-stu-id="160eb-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="160eb-115">**Клиент Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="160eb-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="160eb-116">**Клиент Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="160eb-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="160eb-117">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="160eb-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="160eb-118">Вызов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="160eb-118">Call via Work</span></span>  <br/> |<span data-ttu-id="160eb-119">1</span><span class="sxs-lookup"><span data-stu-id="160eb-119">1</span></span> <br/> |<span data-ttu-id="160eb-120">Вызов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="160eb-120">Call via Work</span></span>  <br/> |<span data-ttu-id="160eb-121">1</span><span class="sxs-lookup"><span data-stu-id="160eb-121">1</span></span> <br/> |<span data-ttu-id="160eb-122">1</span><span class="sxs-lookup"><span data-stu-id="160eb-122">1</span></span> <br/> |
| <span data-ttu-id="160eb-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="160eb-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="160eb-124">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="160eb-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="160eb-125">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="160eb-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="160eb-126">1</span><span class="sxs-lookup"><span data-stu-id="160eb-126">1</span></span> <br/> |<span data-ttu-id="160eb-127">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="160eb-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="160eb-128">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="160eb-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="160eb-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="160eb-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="160eb-130">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="160eb-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="160eb-131">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="160eb-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="160eb-132">1</span><span class="sxs-lookup"><span data-stu-id="160eb-132">1</span></span> <br/> |<span data-ttu-id="160eb-133">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="160eb-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="160eb-134">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="160eb-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="160eb-135">Не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="160eb-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="160eb-136">Для получения дополнительных сведений см [Удаленный центр управления звонками](https://go.microsoft.com/fwlink/p/?LinkId=530208) в документации по Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="160eb-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="160eb-137">См. также</span><span class="sxs-lookup"><span data-stu-id="160eb-137">See also</span></span>

[<span data-ttu-id="160eb-138">Планирование позвонить с рабочего в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="160eb-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="160eb-139">Сравнение функций для настольных компьютеров для Скайп для бизнеса</span><span class="sxs-lookup"><span data-stu-id="160eb-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="160eb-140">Сделать Скайп для вызова бизнеса, но использовать стационарный телефон УАТС для аудио</span><span class="sxs-lookup"><span data-stu-id="160eb-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

