---
title: Вопросы миграции системы комнат Skype
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: В этом разделе вы узнаете, как развернуть систему комнат Skype в среде с несколькими версиями Skype для бизнеса Server и Lync Server.
ms.openlocfilehash: 30b2a4733ea2e2e42b8a879914a2e0e3c4903c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805789"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="96f12-103">Вопросы миграции системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="96f12-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="96f12-104">В этом разделе вы узнаете, как развернуть систему комнат Skype в среде с несколькими версиями Skype для бизнеса Server и Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96f12-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="96f12-105">Сведения о выполнении миграции</span><span class="sxs-lookup"><span data-stu-id="96f12-105">Migration considerations</span></span>

<span data-ttu-id="96f12-106">В этом разделе содержатся рекомендации по развертыванию системы комнат Skype в среде с несколькими пулами, которая включает различные версии Skype для бизнеса Server или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96f12-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="96f12-107">Компонент репликатора пользовательских данных (UR) в Lync Server получает объекты пользователей из Active Directory и помещает их в серверную SQL Server Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96f12-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="96f12-108">Только URL-адрес в Lync Server 2013 знает об объектах системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="96f12-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="96f12-109">URL-адрес в предыдущих версиях Lync Server и Office Communications Server не обнаруживает атрибуты Active Directory, которые обозначают объекты LRS, и поэтому не знает о них.</span><span class="sxs-lookup"><span data-stu-id="96f12-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="96f12-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span><span class="sxs-lookup"><span data-stu-id="96f12-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="96f12-111">Устаревший пул не сможет перенаправлять систему комнат Skype в домашний пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96f12-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="96f12-112">Эту проблему можно решить с помощью следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="96f12-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="96f12-113">Указать запись SRV автообнаружена (_sipinternaltls._tcp.contoso.com) на пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96f12-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="96f12-114">Если первый вариант невозможен, необходимо вручную настроить LRS и предоставить адрес пула Lync Server 2013, непосредственно настроив его в консольном приложении системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="96f12-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="96f12-115">Если система комнат Skype развернута за пределами корпоративной сети, а Lync Edge Server развернут и настроен так, чтобы он указывает на устаревший пул или директор, требуется дополнительный сайт edge Server, который указывает на пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96f12-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="96f12-116">Дополнительные сведения о развертывании дополнительного сервера можно найти в документации по развертыванию edge Server.</span><span class="sxs-lookup"><span data-stu-id="96f12-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="96f12-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span><span class="sxs-lookup"><span data-stu-id="96f12-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="96f12-118">Если во время миграции пользователь, который находится в пуле Lync Server 2010, запланировать собрание и пригласить учетную запись системы комнат Skype, клиент системы комнат Skype будет иметь ограниченную функциональность при посещении собрания.</span><span class="sxs-lookup"><span data-stu-id="96f12-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="96f12-119">Когда клиент системы комнат Skype присоединяется к запланированному конференц-вызову, организованному пользователем, который работает в Lync Server 2010, система комнат Skype имеет следующие ограничения в собрании:</span><span class="sxs-lookup"><span data-stu-id="96f12-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="96f12-120">Система комнат Skype не может показывать видеогалерею с несколькими представлениями.</span><span class="sxs-lookup"><span data-stu-id="96f12-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="96f12-121">Если клиент системы комнат Skype является presenter, он не может применить блокировку видео к участникам.</span><span class="sxs-lookup"><span data-stu-id="96f12-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="96f12-122">Система комнат Skype не может показывать разрешение видео 1080p (входящие и исходящие), даже если это разрешает политика Lync Server 2013, так как это возможно из-за следующих проблем:</span><span class="sxs-lookup"><span data-stu-id="96f12-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="96f12-123">Lync Server 2010 не поддерживает разрешение 1080p.</span><span class="sxs-lookup"><span data-stu-id="96f12-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="96f12-124">Система комнат Skype всегда ограничена политикой конференций организатора для разрешения видео.</span><span class="sxs-lookup"><span data-stu-id="96f12-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="96f12-125">Поэтому даже если пул Lync 2010 поддерживает разрешение 720p, система комнат Skype не сможет использовать разрешение 720p, если политика организатора не поддерживает его.</span><span class="sxs-lookup"><span data-stu-id="96f12-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="96f12-126">Клиенты Lync 2013 обнаруживают присутствие LRS в комнате для собраний и автоматически от звука, чтобы избежать эха в физической комнате для собраний.</span><span class="sxs-lookup"><span data-stu-id="96f12-126">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room.</span></span> <span data-ttu-id="96f12-127">Эта функция не работает на собраниях, размещенных в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="96f12-127">This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="96f12-128">Существуют ограничения на производительность общего доступа к рабочему столу для собраний, которые находятся в Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="96f12-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="96f12-129">Пользователи не смогут присоединяться к частным (ограниченным) собраниям, которые будут проводиться в Lync 2010 с помощью системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="96f12-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

