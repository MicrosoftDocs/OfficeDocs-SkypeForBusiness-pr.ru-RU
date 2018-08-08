---
title: Планирование параметров занятости в Skype для бизнеса Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Просмотр сведений о занятости параметры компонента в Скайп для Business Server.
ms.openlocfilehash: 42e970defa9535a8ae51ec52b0f9033009e58258
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20974118"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="2fdf4-103">Планирование параметров занятости в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2fdf4-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="2fdf4-104">Просмотр сведений о занятости параметры компонента в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="2fdf4-105">Параметры занятости были представлены в накопительном пакете обновлений за июль 2016 года и определяют политику голосовой связи, которая задает порядок обработки входящих звонков, поступающих во время обычного, удерживаемого или конференц-звонка.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="2fdf4-106">В зависимости от настроек новые или входящие звонки могут отклоняться с сигналом "занято" или переадресовываться на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="2fdf4-107">Политика параметров занятости поддерживается при отработке отказа и аварийном восстановлении в парных пулах переднего плана и серверах для обеспечения связи в филиалах (SBS).</span><span class="sxs-lookup"><span data-stu-id="2fdf4-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="2fdf4-108">В этой статье описываются функции параметров занятости.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="2fdf4-109">Сведения о том, как установить и настроить параметры «занят» можно [установить и настроить параметры «занят» для Скайп для Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="2fdf4-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="2fdf4-110">Параметры конфигурации</span><span class="sxs-lookup"><span data-stu-id="2fdf4-110">Configuration options</span></span>

<span data-ttu-id="2fdf4-111">Если для организации включены параметры занятости, все ее пользователи, независимо от наличия доступа к корпоративной голосовой связи, могут работать со следующими функциями:</span><span class="sxs-lookup"><span data-stu-id="2fdf4-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="2fdf4-112">Сигнал занятости — если пользователь занят, все входящие звонки отклоняются и подается сигнал "занято".</span><span class="sxs-lookup"><span data-stu-id="2fdf4-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="2fdf4-113">Голосовая почта — если пользователь занят, все входящие звонки переадресуются на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="2fdf4-114">Функция параметров занятости обеспечивает возможность отработки отказа.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="2fdf4-115">При обнаружении проблем и пользователи при сбое на другой сервер переднего плана или в другой пул в Скайп для Business Server, их «занят» параметры будут сохранены.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="2fdf4-116">Независимо от установленных параметров занятости, во время обычного, удерживаемого или конференц-звонка пользователи могут выполнять новые звонки.  </span><span class="sxs-lookup"><span data-stu-id="2fdf4-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="2fdf4-117">После настройки параметра «занят» параметры для действует Скайп пользователя для клиентов и устройств вызовов Business.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="2fdf4-118">В зависимости от заданных параметров, звонок, который отклоняется или переадресуется на голосовую почту, не будет поступать на любые другие зарегистрированные устройства связи пользователя, включая Macintosh, Windows Desktop, мобильные клиенты или IP-телефоны.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="2fdf4-119">Пользователи увидят уведомления о пропущенных вызовах на их Скайп Business клиентов и устройств, и они будут извещены по адресу электронной почты, а также.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="2fdf4-120">Если входящий вызов отклоняется с параметром "Сигнал занятости", в клиенте Skype для бизнеса звонящего отображается уведомление о том, что абонент был занят другим звонком.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="2fdf4-121">Функция «занят» параметров можно настроить с помощью Скайп по командлетам Business PowerShell для:</span><span class="sxs-lookup"><span data-stu-id="2fdf4-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="2fdf4-122">Включение или отключение политики голосовой связи, определяющей параметры занятости для предприятия.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="2fdf4-123">Администрирование параметров "Сигнал занятости" и "Голосовая почта" для всех пользователей предприятия.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="2fdf4-124">Администрирование параметров "Сигнал занятости" и "Голосовая почта" для всех пользователей, размещенных в конкретном пуле переднего плана.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="2fdf4-125">Администрирование параметров "Сигнал занятости" и "Голосовая почта" для списка пользователей.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="2fdf4-126">Администрирование параметров "Сигнал занятости" и "Голосовая почта" для отдельного пользователя.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="2fdf4-127">Взаимодействие с приложениями голосовой связи</span><span class="sxs-lookup"><span data-stu-id="2fdf4-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="2fdf4-128">Параметры «занят» обеспечивает взаимодействие со следующими приложениями голосовой связи в Скайп для бизнеса:</span><span class="sxs-lookup"><span data-stu-id="2fdf4-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="2fdf4-129">Группы ответа (RGS)</span><span class="sxs-lookup"><span data-stu-id="2fdf4-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="2fdf4-130">Параметры занятости, установленные для номеров группы ответа, игнорируются системой, в результате чего допускаются параллельные звонки. </span><span class="sxs-lookup"><span data-stu-id="2fdf4-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="2fdf4-131">Текущие возможности маршрутизации помощника в группах ответа для агентов с настроенными параметрами занятости остаются без изменений.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="2fdf4-132">Звонки из групп ответа, поступающие агентам групп ответа, не ограничиваются параметрами занятости, в связи с чем сохраняются текущие возможности групп ответа.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="2fdf4-133">К звонкам, не связанным с группами ответа, которые поступают агентам, применяются соответствующие параметры занятости.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="2fdf4-134">Групповые звонки</span><span class="sxs-lookup"><span data-stu-id="2fdf4-134">Team Call</span></span>
    
  - <span data-ttu-id="2fdf4-135">Входящие звонки для пользователей, которые настроены для группового звонка будут применяться игнорировать голосовой почты на параметры «занят» и «занят» на «занят».</span><span class="sxs-lookup"><span data-stu-id="2fdf4-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="2fdf4-136">Текущие возможности групповых звонков остаются без изменений независимо от параметров занятости пользователей.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="2fdf4-137">К звонкам, не являющимся групповыми, которые поступают таким пользователям, применяются соответствующие параметры занятости.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="2fdf4-138">Делегирование начальнику или администратору </span><span class="sxs-lookup"><span data-stu-id="2fdf4-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="2fdf4-139">Входящие звонки для пользователей, которые настроены для делегирования начальника/Admin либо как начальника или администратор приоритетов игнорировать голосовой почты на параметры «занят» и «занят» на «занят».</span><span class="sxs-lookup"><span data-stu-id="2fdf4-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="2fdf4-140">Текущие возможности делегирования начальнику или администратору остаются без изменений независимо от параметров занятости соответствующих пользователей.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="2fdf4-141">К звонкам, не связанным с делегированием начальнику или администратору, которые поступают администраторам, применяются соответствующие параметры занятости.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="2fdf4-142">Распределенная линия   </span><span class="sxs-lookup"><span data-stu-id="2fdf4-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="2fdf4-143">Параметры занятости для учетных записей пользователей с настроенной распределенной линией игнорируются. </span><span class="sxs-lookup"><span data-stu-id="2fdf4-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="2fdf4-144">Общий вид линии собственная «занят» на «занят» и голосовой почты на «занят» параметры будут соблюдаться вместо этого.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="2fdf4-145">Служба парковки вызовов </span><span class="sxs-lookup"><span data-stu-id="2fdf4-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="2fdf4-146">Приостановленные звонки, которые не были восстановлены и поступают повторно из-за истечения времени ожидания, будут приняты, даже если у приостановившего их пользователя настроены параметра занятости. </span><span class="sxs-lookup"><span data-stu-id="2fdf4-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="2fdf4-147">Конференц-звонки</span><span class="sxs-lookup"><span data-stu-id="2fdf4-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="2fdf4-148">Пользователи, выполняющие конференц-звонки, считаются занятыми, и поступающие им звонки отклоняются или переадресуются на голосовую почту в зависимости от заданных параметров занятости.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="2fdf4-149">Пользователи, выполняющие конференц-звонки, могут выполнять новые обычные или конференц-звонки, несмотря на значения параметров занятости.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="2fdf4-150">Пользователи, выполняющие конференц-звонки, по-прежнему могут получать новые приглашения на конференцию, однако новые одноранговые звонки отклоняются в соответствии с заданными параметрами занятости.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="2fdf4-151">Одновременные звонки и переадресация звонков</span><span class="sxs-lookup"><span data-stu-id="2fdf4-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="2fdf4-152">Функция переадресации звонка при занятости не может работать с одновременными звонками и переадресацией звонков.</span><span class="sxs-lookup"><span data-stu-id="2fdf4-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

