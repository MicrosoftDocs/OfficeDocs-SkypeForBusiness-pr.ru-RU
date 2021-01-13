---
title: Планирование параметров занятости для Skype для бизнеса Server
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Ознакомьтесь с функцией "Параметры занятости" в Skype для бизнеса Server.
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813699"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="410cc-103">Планирование параметров занятости для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="410cc-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="410cc-104">Ознакомьтесь с функцией "Параметры занятости" в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="410cc-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="410cc-105">Параметры занятости — это новая политика голосовой почты, представленная в накопительном обновлении за июль 2016 г., которая позволяет настроить обработку входящих вызовов, когда пользователь уже находится в вызове или конференции или находится на удержании.</span><span class="sxs-lookup"><span data-stu-id="410cc-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="410cc-106">Новые или входящие вызовы можно отклонить с сигналом "занято" или переадлить на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="410cc-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="410cc-107">Политика "Параметры занятости" поддерживается для отсечления и аварийного восстановления на сопряженных пулах переднего сервера и серверах филиалов (SBS).</span><span class="sxs-lookup"><span data-stu-id="410cc-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="410cc-108">В этом разделе описываются функции параметров занятости.</span><span class="sxs-lookup"><span data-stu-id="410cc-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="410cc-109">Сведения об установке и настройке параметров занятости см. в сведениях об установке и настройке параметров занятости [skype для бизнеса Server.](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)</span><span class="sxs-lookup"><span data-stu-id="410cc-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="410cc-110">Параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="410cc-110">Configuration options</span></span>

<span data-ttu-id="410cc-111">Если в организации включены параметры занятости, все пользователи в организации, как Корпоративная голосовая связь, так и пользователи, не Корпоративная голосовая связь, могут использовать следующие функции:</span><span class="sxs-lookup"><span data-stu-id="410cc-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="410cc-112">Занят в "Занят". При этом новые входящие вызовы будут отклониться с сигналом "занято", если пользователь занят.</span><span class="sxs-lookup"><span data-stu-id="410cc-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="410cc-113">Голосовая почта в службе "Занято". В которой новые входящие вызовы будут переадад частью голосовой почты, если пользователь занят.</span><span class="sxs-lookup"><span data-stu-id="410cc-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="410cc-114">Функция "Параметры занятости" предоставляет возможность от сбойа.</span><span class="sxs-lookup"><span data-stu-id="410cc-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="410cc-115">Если возникает проблема и пользователи перенаправят пользователей на другой сервер переднего сервера или в другой пул в Skype для бизнеса Server, параметры занятости будут сохранены.</span><span class="sxs-lookup"><span data-stu-id="410cc-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="410cc-116">Независимо от того, как настроены параметры занятости, пользователям в звонках или конференциях или звонках на удержании не помешает инициировать новые вызовы или конференции.</span><span class="sxs-lookup"><span data-stu-id="410cc-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="410cc-117">После настройки параметр "Параметры занятости" будет действовать для всех устройств и клиентов звонков Skype для бизнеса пользователя.</span><span class="sxs-lookup"><span data-stu-id="410cc-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="410cc-118">Исходя из параметров занятости пользователя, вызов, который отклоняется или отправляется на голосовую почту, не будет звонить на любые устройства вызова пользователя, включая Macintosh, настольные компьютеры с Windows, мобильные клиенты или IP-телефоны, на которых пользователь вошел.</span><span class="sxs-lookup"><span data-stu-id="410cc-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="410cc-119">Пользователи увидят уведомления о пропущенных звонках на своих клиентах и устройствах Skype для бизнеса, а также по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="410cc-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="410cc-120">Вызыватели, звонок которых был отклонен из-за занятости, увидят в клиенте Skype для бизнеса уведомление о том, что пользователь, которого он попытался связаться, занят другим вызовом.</span><span class="sxs-lookup"><span data-stu-id="410cc-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="410cc-121">Вы можете настроить функцию "Параметры занятости", используя для этого с помощью cmdlets Skype для бизнеса PowerShell:</span><span class="sxs-lookup"><span data-stu-id="410cc-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="410cc-122">Включить или отключить политику голосовой почты "Параметры занятости" для предприятия.</span><span class="sxs-lookup"><span data-stu-id="410cc-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="410cc-123">Администрирование "Занято" или "Голосовая почта" для всех пользователей предприятия.</span><span class="sxs-lookup"><span data-stu-id="410cc-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="410cc-124">Администрирование "Занято" или "Голосовая почта" для всех пользователей, которые были в определенном пуле переднего входа.</span><span class="sxs-lookup"><span data-stu-id="410cc-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="410cc-125">Администрирование "Занято" или "Голосовая почта в занятости" для списка пользователей.</span><span class="sxs-lookup"><span data-stu-id="410cc-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="410cc-126">Администрирование "Занято" или "Голосовая почта" для одного пользователя.</span><span class="sxs-lookup"><span data-stu-id="410cc-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="410cc-127">Interoperability with Voice applications</span><span class="sxs-lookup"><span data-stu-id="410cc-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="410cc-128">Параметры занятости обеспечивают возможность связи со следующими приложениями голосовой связи в Skype для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="410cc-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="410cc-129">Группы ответа (RGS)</span><span class="sxs-lookup"><span data-stu-id="410cc-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="410cc-130">Параметры занятости, установленные на номерах группы ответа, будут игнорироваться системой; допускается несколько одновременно звонков.</span><span class="sxs-lookup"><span data-stu-id="410cc-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="410cc-131">Для агентов с настройками занятости текущий параметров маршрутки помощника в группах ответа останется без изменений.</span><span class="sxs-lookup"><span data-stu-id="410cc-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="410cc-132">Вызовы, которые приходят из групп ответа пользователям, которые являются агентами групп ответа, не будут регулирование с помощью параметров занятости, а текущий опыт работы с RGS будет сохранен.</span><span class="sxs-lookup"><span data-stu-id="410cc-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="410cc-133">Вызовы агентов, не связанные с RGS, будут соблюдаться с помощью параметров занятости.</span><span class="sxs-lookup"><span data-stu-id="410cc-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="410cc-134">Командный звонок</span><span class="sxs-lookup"><span data-stu-id="410cc-134">Team Call</span></span>
    
  - <span data-ttu-id="410cc-135">Приоритет входящих звонков пользователей, для которых настроен звонок в группе, будет игнорировать параметры "Занят" и "Голосовая почта" в параметрах "Занято".</span><span class="sxs-lookup"><span data-stu-id="410cc-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="410cc-136">Текущая настройка параметров занятости для пользователей останется неизменной.</span><span class="sxs-lookup"><span data-stu-id="410cc-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="410cc-137">Вызовы, не связанные с вызовами группы, для таких пользователей будут соблюдаться с помощью параметров занятости.</span><span class="sxs-lookup"><span data-stu-id="410cc-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="410cc-138">Делегирования начальника или администратора</span><span class="sxs-lookup"><span data-stu-id="410cc-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="410cc-139">Входящие звонки пользователям, которые настроены для делегирования начальника или администратора, будут иметь приоритет, чтобы игнорировать параметры "Занят" и "Голосовая почта" в параметрах "Занято".</span><span class="sxs-lookup"><span data-stu-id="410cc-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="410cc-140">Текущие возможности делегирования начальника или администратора останутся без изменений с настройками параметров занятости для администраторов или начальников.</span><span class="sxs-lookup"><span data-stu-id="410cc-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="410cc-141">Вызовы, не относящиеся к делегирования начальникам или администраторам для администраторов, будут соблюдаться с помощью параметров занятости.</span><span class="sxs-lookup"><span data-stu-id="410cc-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="410cc-142">Распределенная линия</span><span class="sxs-lookup"><span data-stu-id="410cc-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="410cc-143">Параметры занятости в учетных записях пользователей, которые настроены для общего вида линии, будут игнорироваться.</span><span class="sxs-lookup"><span data-stu-id="410cc-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="410cc-144">Вместо этого будут соблюдаться параметры "Занят" и "Голосовая почта в параметрах занятости" в общих строках.</span><span class="sxs-lookup"><span data-stu-id="410cc-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="410cc-145">Служба парковки вызовов</span><span class="sxs-lookup"><span data-stu-id="410cc-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="410cc-146">Припаркованные вызовы, которые не были извлечены и звонят обратно из-за времени, смогут звонить пользователю, который припарковал вызов с помощью параметров занятости.</span><span class="sxs-lookup"><span data-stu-id="410cc-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="410cc-147">Call Conferencing</span><span class="sxs-lookup"><span data-stu-id="410cc-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="410cc-148">Пользователи в конференц-звонках считаются занятыми, а новые входящие вызовы будут отклоняется с сигналом "занято" или перена пересылаются на голосовую почту в соответствии с их настройками параметров занятости.</span><span class="sxs-lookup"><span data-stu-id="410cc-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="410cc-149">Пользователям в конференциях не помешает инициять новые вызовы или конференции с помощью параметров занятости.</span><span class="sxs-lookup"><span data-stu-id="410cc-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="410cc-150">Пользователи конференций по-прежнему могут получать новые приглашения на конференцию, но новые одноранговых вызовы будут отклониться в соответствии с их настройками параметров занятости.</span><span class="sxs-lookup"><span data-stu-id="410cc-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="410cc-151">Одновременные вызовы и переад вызовы</span><span class="sxs-lookup"><span data-stu-id="410cc-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="410cc-152">Функция "Занят в занятости" не предназначена для работы с одновременными звонками и переад вызовами.</span><span class="sxs-lookup"><span data-stu-id="410cc-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

