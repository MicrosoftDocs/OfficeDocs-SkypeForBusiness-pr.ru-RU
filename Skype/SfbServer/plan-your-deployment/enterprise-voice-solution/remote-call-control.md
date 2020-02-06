---
title: Планирование удаленного управления звонками в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Удаленное управление звонками — это функция в предыдущих версиях Lync Server, на которой пользователи смогут управлять телефонным АТС с помощью Lync Server. В Skype для бизнеса Server эта функция заменена на "звонок через Work". В клиентских версиях Skype для бизнеса Server 2015 и переходе к следующему элементу управления удаленным звонком больше нельзя настроить в клиенте и он был удален для использования.
ms.openlocfilehash: 67010a0bc74ef46dcf204e3b2a905be87c182daf
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802509"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="7a7ab-105">Планирование удаленного управления звонками в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7a7ab-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="7a7ab-106">Удаленное управление звонками — это функция в предыдущих версиях Lync Server, на которой пользователи смогут управлять телефонным АТС с помощью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7a7ab-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="7a7ab-107">В Skype для бизнеса Server эта функция заменена на "звонок через Work".</span><span class="sxs-lookup"><span data-stu-id="7a7ab-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="7a7ab-108">*В клиентских версиях Skype для бизнеса Server 2015 и переходе к следующему элементу управления удаленным звонком больше нельзя настроить в клиенте и он был удален для использования.*</span><span class="sxs-lookup"><span data-stu-id="7a7ab-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="7a7ab-109">Пользователи удаленного управления звонками в вашей организации, которые размещаются на серверах переднего плана с Lync Server, могут продолжать использовать удаленное управление звонками даже в том случае, если они используют клиента Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7a7ab-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="7a7ab-110">Тем не менее, для всех пользователей, которые подключены к Skype для бизнеса Server, не поддерживается управление удаленными звонками.</span><span class="sxs-lookup"><span data-stu-id="7a7ab-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="7a7ab-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span><span class="sxs-lookup"><span data-stu-id="7a7ab-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="7a7ab-112">**Клиент Skype для бизнеса с включенным ИНТЕРФЕЙСом Skype**</span><span class="sxs-lookup"><span data-stu-id="7a7ab-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="7a7ab-113">**Клиент Skype для бизнеса с включенным ИНТЕРФЕЙСом Lync**</span><span class="sxs-lookup"><span data-stu-id="7a7ab-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="7a7ab-114">**Клиент Skype для бизнеса 2016**</span><span class="sxs-lookup"><span data-stu-id="7a7ab-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="7a7ab-115">**Клиент Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="7a7ab-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="7a7ab-116">**Клиент Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="7a7ab-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="7a7ab-117">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7a7ab-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="7a7ab-118">Вызов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="7a7ab-118">Call via Work</span></span>  <br/> |<span data-ttu-id="7a7ab-119">1</span><span class="sxs-lookup"><span data-stu-id="7a7ab-119">1</span></span> <br/> |<span data-ttu-id="7a7ab-120">Вызов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="7a7ab-120">Call via Work</span></span>  <br/> |<span data-ttu-id="7a7ab-121">1</span><span class="sxs-lookup"><span data-stu-id="7a7ab-121">1</span></span> <br/> |<span data-ttu-id="7a7ab-122">1</span><span class="sxs-lookup"><span data-stu-id="7a7ab-122">1</span></span> <br/> |
| <span data-ttu-id="7a7ab-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a7ab-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="7a7ab-124">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="7a7ab-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="7a7ab-125">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="7a7ab-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="7a7ab-126">1,1</span><span class="sxs-lookup"><span data-stu-id="7a7ab-126">1</span></span> <br/> |<span data-ttu-id="7a7ab-127">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="7a7ab-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="7a7ab-128">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="7a7ab-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="7a7ab-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="7a7ab-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="7a7ab-130">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="7a7ab-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="7a7ab-131">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="7a7ab-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="7a7ab-132">1,1</span><span class="sxs-lookup"><span data-stu-id="7a7ab-132">1</span></span> <br/> |<span data-ttu-id="7a7ab-133">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="7a7ab-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="7a7ab-134">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="7a7ab-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="7a7ab-135">Ни одна из функций не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="7a7ab-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="7a7ab-136">Дополнительные сведения можно найти в разделе [Управление удаленными звонками](https://go.microsoft.com/fwlink/p/?LinkId=530208) в документации по Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7a7ab-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7a7ab-137">См. также</span><span class="sxs-lookup"><span data-stu-id="7a7ab-137">See also</span></span>

[<span data-ttu-id="7a7ab-138">Планирование звонков с помощью Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7a7ab-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="7a7ab-139">Сравнение возможностей настольного клиента в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="7a7ab-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="7a7ab-140">Совершение звонков в Skype для бизнеса с помощью телефона в стационарном устройстве УАТС для звука</span><span class="sxs-lookup"><span data-stu-id="7a7ab-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/en-us/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

