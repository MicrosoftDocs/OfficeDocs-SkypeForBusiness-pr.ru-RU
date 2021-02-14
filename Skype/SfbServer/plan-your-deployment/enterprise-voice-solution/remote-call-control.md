---
title: Планирование удаленного управления звонками в Skype для бизнеса
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
description: В предыдущих версиях Lync Server функция удаленного управления звонками позволяла пользователям управлять телефонами УАЦ с помощью Lync Server. В Skype для бизнеса Server эта функция заменена функцией "Позвонить с работы". In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.
ms.openlocfilehash: b48eeed656f5889d08fe892da7d7a6896f8a11c3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813519"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="55168-105">Планирование удаленного управления звонками в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="55168-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="55168-106">В предыдущих версиях Lync Server функция удаленного управления звонками позволяла пользователям управлять телефонами УАЦ с помощью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="55168-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="55168-107">В Skype для бизнеса Server эта функция заменена функцией "Позвонить с работы".</span><span class="sxs-lookup"><span data-stu-id="55168-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="55168-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span><span class="sxs-lookup"><span data-stu-id="55168-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="55168-109">Пользователи удаленного управления звонками в организации, которые находятся на серверах переднего сервера с Lync Server, могут продолжать использовать удаленное управление звонками, даже если они используют клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="55168-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="55168-110">Однако для всех пользователей, которые были в Skype для бизнеса Server, удаленное управление звонками не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="55168-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="55168-111">См. следующую таблицу для комбинаций серверов и клиентов, а также о том, могут ли они поддерживать удаленное управление вызовами или вызов с помощью работы.</span><span class="sxs-lookup"><span data-stu-id="55168-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="55168-112">**Клиент Skype для бизнеса с включенным пользовательским интерфейсом Skype**</span><span class="sxs-lookup"><span data-stu-id="55168-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="55168-113">**Клиент Skype для бизнеса с включенным пользовательским интерфейсом Lync**</span><span class="sxs-lookup"><span data-stu-id="55168-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="55168-114">**Клиент Skype для бизнеса 2016**</span><span class="sxs-lookup"><span data-stu-id="55168-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="55168-115">**Клиент Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="55168-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="55168-116">**Клиент Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="55168-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="55168-117">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="55168-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="55168-118">Вызов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="55168-118">Call via Work</span></span>  <br/> |<span data-ttu-id="55168-119">1 </span><span class="sxs-lookup"><span data-stu-id="55168-119">1</span></span> <br/> |<span data-ttu-id="55168-120">Вызов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="55168-120">Call via Work</span></span>  <br/> |<span data-ttu-id="55168-121">1 </span><span class="sxs-lookup"><span data-stu-id="55168-121">1</span></span> <br/> |<span data-ttu-id="55168-122">1 </span><span class="sxs-lookup"><span data-stu-id="55168-122">1</span></span> <br/> |
| <span data-ttu-id="55168-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55168-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="55168-124">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="55168-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="55168-125">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="55168-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="55168-126">1 </span><span class="sxs-lookup"><span data-stu-id="55168-126">1</span></span> <br/> |<span data-ttu-id="55168-127">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="55168-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="55168-128">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="55168-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="55168-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="55168-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="55168-130">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="55168-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="55168-131">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="55168-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="55168-132">1 </span><span class="sxs-lookup"><span data-stu-id="55168-132">1</span></span> <br/> |<span data-ttu-id="55168-133">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="55168-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="55168-134">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="55168-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="55168-135">Ни одна из функций не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="55168-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="55168-136">Дополнительные сведения [см.](https://go.microsoft.com/fwlink/p/?LinkId=530208) в документации по удаленному контролю вызовов в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55168-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="55168-137">См. также</span><span class="sxs-lookup"><span data-stu-id="55168-137">See also</span></span>

[<span data-ttu-id="55168-138">Планирование звонков с помощью работы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="55168-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="55168-139">Сравнение функций классических клиентов в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="55168-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="55168-140">Сделайте звонок в Skype для бизнеса, но используйте настольный телефон УАКСИ для звука</span><span class="sxs-lookup"><span data-stu-id="55168-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

