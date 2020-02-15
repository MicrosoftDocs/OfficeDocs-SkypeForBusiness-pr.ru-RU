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
description: Удаленное управление звонками было компонентом предыдущих версий Lync Server, который позволяет пользователям управлять телефонами УАТС с помощью Lync Server. В Skype для бизнеса Server эта функция заменена на Call с помощью функции "позвонить с рабочего". В клиентских версиях для Skype для бизнеса Server 2015 и при переходе вперед удаленное управление звонками больше не доступно для настройки в клиенте и удалено для использования.
ms.openlocfilehash: 788939c392b1d86d14590232c19979e664fa0c09
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41982804"
---
# <a name="plan-for-remote-call-control-in-skype-for-business"></a><span data-ttu-id="3e365-105">Планирование удаленного управления звонками в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3e365-105">Plan for remote call control in Skype for Business</span></span>
 
<span data-ttu-id="3e365-106">Удаленное управление звонками было компонентом предыдущих версий Lync Server, который позволяет пользователям управлять телефонами УАТС с помощью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3e365-106">Remote call control was a feature in previous versions of Lync Server which enabled users to control their PBX phones with Lync Server.</span></span> <span data-ttu-id="3e365-107">В Skype для бизнеса Server эта функция заменена на Call с помощью функции "позвонить с рабочего".</span><span class="sxs-lookup"><span data-stu-id="3e365-107">In Skype for Business Server, this feature has been replaced with Call Via Work.</span></span>  <span data-ttu-id="3e365-108">*В клиентских версиях для Skype для бизнеса Server 2015 и при переходе вперед удаленное управление звонками больше не доступно для настройки в клиенте и удалено для использования.*</span><span class="sxs-lookup"><span data-stu-id="3e365-108">*In the client versions for Skype for Business Server 2015 and going forward, remote call control is no longer available to configure in the client and has been removed for use.*</span></span> 
  
 <span data-ttu-id="3e365-109">Пользователи удаленного управления звонками в вашей организации, размещенные на серверах переднего плана с Lync Server, могут продолжать использовать удаленное управление звонками, даже если они используют клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="3e365-109">Remote call control users in your organization who are homed on Front End Servers running Lync Server can continue to use remote call control, even if they are using a Skype for Business client.</span></span> <span data-ttu-id="3e365-110">Однако для всех пользователей, размещенных в Skype для бизнеса Server, Управление удаленными звонками не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3e365-110">However, for any users homed on Skype for Business Server, remote call control is not supported.</span></span> <span data-ttu-id="3e365-111">В следующей таблице приведены сочетания серверов и клиентов, а также возможность поддержки удаленного управления звонками или вызовов с помощью work.</span><span class="sxs-lookup"><span data-stu-id="3e365-111">See the following table for server/client combinations and whether they can support remote call control or Call via Work.</span></span>
  
||<span data-ttu-id="3e365-112">**Клиент Skype для бизнеса с включенным ИНТЕРФЕЙСом Skype**</span><span class="sxs-lookup"><span data-stu-id="3e365-112">**Skype for Business Client With Skype UI enabled**</span></span>|<span data-ttu-id="3e365-113">**Клиент Skype для бизнеса с включенным ИНТЕРФЕЙСом Lync**</span><span class="sxs-lookup"><span data-stu-id="3e365-113">**Skype for Business Client With Lync UI enabled**</span></span>|<span data-ttu-id="3e365-114">**Клиент Skype для бизнеса 2016**</span><span class="sxs-lookup"><span data-stu-id="3e365-114">**Skype for Business 2016 Client**</span></span>|<span data-ttu-id="3e365-115">**Клиент Lync 2013**</span><span class="sxs-lookup"><span data-stu-id="3e365-115">**Lync 2013 Client**</span></span>|<span data-ttu-id="3e365-116">**Клиент Lync 2010**</span><span class="sxs-lookup"><span data-stu-id="3e365-116">**Lync 2010 Client**</span></span>|
|:-----|:-----|:-----|:-----|:-----|:-----|
| <span data-ttu-id="3e365-117">Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3e365-117">Skype for Business Server</span></span> <br/> |<span data-ttu-id="3e365-118">Вызов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="3e365-118">Call via Work</span></span>  <br/> |<span data-ttu-id="3e365-119">1 </span><span class="sxs-lookup"><span data-stu-id="3e365-119">1</span></span> <br/> |<span data-ttu-id="3e365-120">Вызов с рабочего телефона</span><span class="sxs-lookup"><span data-stu-id="3e365-120">Call via Work</span></span>  <br/> |<span data-ttu-id="3e365-121">1 </span><span class="sxs-lookup"><span data-stu-id="3e365-121">1</span></span> <br/> |<span data-ttu-id="3e365-122">1 </span><span class="sxs-lookup"><span data-stu-id="3e365-122">1</span></span> <br/> |
| <span data-ttu-id="3e365-123">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3e365-123">Lync Server 2013</span></span> <br/> |<span data-ttu-id="3e365-124">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="3e365-124">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3e365-125">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="3e365-125">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3e365-126">1 </span><span class="sxs-lookup"><span data-stu-id="3e365-126">1</span></span> <br/> |<span data-ttu-id="3e365-127">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="3e365-127">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3e365-128">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="3e365-128">Remote Call Control</span></span>  <br/> |
| <span data-ttu-id="3e365-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="3e365-129">Lync Server 2010</span></span> <br/> |<span data-ttu-id="3e365-130">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="3e365-130">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3e365-131">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="3e365-131">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3e365-132">1 </span><span class="sxs-lookup"><span data-stu-id="3e365-132">1</span></span> <br/> |<span data-ttu-id="3e365-133">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="3e365-133">Remote Call Control</span></span>  <br/> |<span data-ttu-id="3e365-134">Удаленное управление звонками</span><span class="sxs-lookup"><span data-stu-id="3e365-134">Remote Call Control</span></span>  <br/> |
   
1. <span data-ttu-id="3e365-135">Ни одна из этих функций не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="3e365-135">Neither feature is supported.</span></span>
  
<span data-ttu-id="3e365-136">Дополнительные сведения см в документации по [удаленному управлению звонками](https://go.microsoft.com/fwlink/p/?LinkId=530208) в документации по Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3e365-136">For more information, see [Remote Call Control](https://go.microsoft.com/fwlink/p/?LinkId=530208) in the Lync Server 2013 documentation.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3e365-137">См. также</span><span class="sxs-lookup"><span data-stu-id="3e365-137">See also</span></span>

[<span data-ttu-id="3e365-138">Планирование вызовов с помощью Works в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3e365-138">Plan for Call Via Work in Skype for Business Server</span></span>](call-via-work.md)
  
[<span data-ttu-id="3e365-139">Сравнение функций клиента для настольных ПК в Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="3e365-139">Desktop client feature comparison for Skype for Business</span></span>](../../plan-your-deployment/clients-and-devices/desktop-feature-comparison.md)

[<span data-ttu-id="3e365-140">Совершение звонка в Skype для бизнеса, но использование телефона в стационарном телефоне для аудио</span><span class="sxs-lookup"><span data-stu-id="3e365-140">Make a Skype for Business call but use your PBX desk phone for audio</span></span>](https://support.office.com/article/Make-a-Skype-for-Business-call-but-use-your-PBX-desk-phone-for-audio-6a316c11-a05e-460c-b969-32ff0ad848e6)

