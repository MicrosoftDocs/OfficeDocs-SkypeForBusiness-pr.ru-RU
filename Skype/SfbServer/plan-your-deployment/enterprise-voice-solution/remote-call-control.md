---
title: Планирование удаленного управления вызовами в Skype для бизнеса
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
description: Удаленное управление вызовами было функцией в предыдущих версиях Lync Server, которая позволяла пользователям управлять своими PBX-телефонами с помощью Lync Server. В Skype для бизнеса Server эта функция была заменена на Call Via Work. В клиентских версиях Для Skype для бизнеса Server 2015 и в будущем удаленный контроль вызовов больше не доступен для настройки в клиенте и удален для использования.
ms.openlocfilehash: 1ec6bb59b34505f17451be72baa44cdcc466c0d3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114615"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="ba1c9-105">Планирование удаленного управления вызовами в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ba1c9-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="ba1c9-106">Удаленное управление вызовами было функцией в предыдущих версиях Lync Server, которая позволяла пользователям управлять своими PBX-телефонами с помощью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="ba1c9-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="ba1c9-107">В Skype для бизнеса Server эта функция была заменена на Call Via Work.</span><span class="sxs-lookup"><span data-stu-id="ba1c9-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="ba1c9-108">*В клиентских версиях Для Skype для бизнеса Server 2015 и в будущем удаленный контроль вызовов больше не доступен для настройки в клиенте и удален для использования.*</span><span class="sxs-lookup"><span data-stu-id="ba1c9-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="ba1c9-109">Пользователи удаленного управления вызовами в организации, которые находятся на серверах переднего входа под управлением Lync Server, могут продолжать использовать удаленное управление вызовами, даже если они используют клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="ba1c9-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="ba1c9-110">Однако для всех пользователей, уехав в Skype для бизнеса Server, удаленное управление вызовами не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ba1c9-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="ba1c9-111">См. следующую таблицу для комбинаций серверов и клиентов, а также, могут ли они поддерживать удаленное управление вызовами или вызовы с помощью work.</span><span class="sxs-lookup"><span data-stu-id="ba1c9-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="ba1c9-112">**Skype для бизнеса-клиента с включенным пользовательским интерфейсом Skype**</span><span class="sxs-lookup"><span data-stu-id="ba1c9-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="ba1c9-113">**Skype для бизнес-клиента с включенным пользовательским интерфейсом Lync**</span><span class="sxs-lookup"><span data-stu-id="ba1c9-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="ba1c9-114">**Клиент Skype для бизнеса 2016**</span><span class="sxs-lookup"><span data-stu-id="ba1c9-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="ba1c9-115">**Клиент Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="ba1c9-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="ba1c9-116">**Клиент Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="ba1c9-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ba1c9-117">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ba1c9-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="ba1c9-118">Вызов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="ba1c9-118">Call via Work</span></span>  <br/> |<span data-ttu-id="ba1c9-119">1</span><span class="sxs-lookup"><span data-stu-id="ba1c9-119">1</span></span> <br/> |<span data-ttu-id="ba1c9-120">Вызов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="ba1c9-120">Call via Work</span></span>  <br/> |<span data-ttu-id="ba1c9-121">1</span><span class="sxs-lookup"><span data-stu-id="ba1c9-121">1</span></span> <br/> |<span data-ttu-id="ba1c9-122">1</span><span class="sxs-lookup"><span data-stu-id="ba1c9-122">1</span></span> <br/> |
| <span data-ttu-id="ba1c9-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ba1c9-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="ba1c9-124">Удаленное управление вызовами</span><span class="sxs-lookup"><span data-stu-id="ba1c9-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="ba1c9-125">Удаленное управление вызовами</span><span class="sxs-lookup"><span data-stu-id="ba1c9-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="ba1c9-126">1</span><span class="sxs-lookup"><span data-stu-id="ba1c9-126">1</span></span> <br/> |<span data-ttu-id="ba1c9-127">Удаленное управление вызовами</span><span class="sxs-lookup"><span data-stu-id="ba1c9-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="ba1c9-128">Удаленное управление вызовами</span><span class="sxs-lookup"><span data-stu-id="ba1c9-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="ba1c9-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="ba1c9-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="ba1c9-130">Удаленное управление вызовами</span><span class="sxs-lookup"><span data-stu-id="ba1c9-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="ba1c9-131">Удаленное управление вызовами</span><span class="sxs-lookup"><span data-stu-id="ba1c9-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="ba1c9-132">1</span><span class="sxs-lookup"><span data-stu-id="ba1c9-132">1</span></span> <br/> |<span data-ttu-id="ba1c9-133">Удаленное управление вызовами</span><span class="sxs-lookup"><span data-stu-id="ba1c9-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="ba1c9-134">Удаленное управление вызовами</span><span class="sxs-lookup"><span data-stu-id="ba1c9-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="ba1c9-135">Ни одна из функций не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="ba1c9-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="ba1c9-136">Дополнительные сведения см. в [документации по](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) удаленному вызову в документации Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ba1c9-136">For more information, see [Remote Call Control](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-remote-call-control) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ba1c9-137">См. также</span><span class="sxs-lookup"><span data-stu-id="ba1c9-137">See also</span></span>

[<span data-ttu-id="ba1c9-138">Планирование звонков с помощью работы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ba1c9-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="ba1c9-139">Сравнение функций клиента настольных компьютеров для Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ba1c9-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="ba1c9-140">Сделайте вызов Skype для бизнеса, но используйте настольный телефон PBX для аудиозаписи</span><span class="sxs-lookup"><span data-stu-id="ba1c9-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)