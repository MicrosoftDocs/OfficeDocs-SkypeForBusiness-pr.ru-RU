---
title: Рекомендации по перемещению системы комнат Skype
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: В этой статье рассказывается, как развернуть систему комнат Skype в среде с несколькими версиями Skype для бизнеса Server и Lync Server.
ms.openlocfilehash: 6524a7312644ec306185b952caf17818d29344af
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774677"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="f527a-103">Рекомендации по перемещению системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="f527a-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="f527a-104">В этой статье рассказывается, как развернуть систему комнат Skype в среде с несколькими версиями Skype для бизнеса Server и Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f527a-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="f527a-105">Рекомендации по перемещению</span><span class="sxs-lookup"><span data-stu-id="f527a-105">Migration considerations</span></span>

<span data-ttu-id="f527a-106">В этом разделе приведены рекомендации по развертыванию системы комнат Skype в среде с несколькими пулами, включающей различные версии Skype для бизнеса Server или Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f527a-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, or Lync Server.</span></span> 
  
<span data-ttu-id="f527a-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span><span class="sxs-lookup"><span data-stu-id="f527a-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="f527a-108">Только UR в Lync Server 2013 знают об объектах системы комнаты Skype.</span><span class="sxs-lookup"><span data-stu-id="f527a-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="f527a-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span><span class="sxs-lookup"><span data-stu-id="f527a-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="f527a-110">Если при попытке входа в приложение Lync с помощью учетной записи в комнате Skype выполняется автоматическое обнаружение на основе записи SRV или DNS A, а если эти учетные записи указывают на предыдущую версию Lync Server или Office Communications Server, ЛРС получит 404  пул устаревших.</span><span class="sxs-lookup"><span data-stu-id="f527a-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="f527a-111">Пул из старого пула не сможет перенаправлять систему комнат Skype на свой пул Lync Server 2013 Home.</span><span class="sxs-lookup"><span data-stu-id="f527a-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="f527a-112">Эту проблему можно решить следующими способами:</span><span class="sxs-lookup"><span data-stu-id="f527a-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="f527a-113">Сделайте так, чтобы запись SRV с автоматическим обнаружением (_sipinternaltls._tcp.contoso.com) указывала на пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f527a-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="f527a-114">Если первый вариант невозможен, вы должны вручную настроить ЛРС и предоставить адрес пула Lync Server 2013, настроив его непосредственно в консольном приложении системы комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="f527a-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="f527a-115">Если система комнат Skype развернута за пределами корпоративной сети, а граничный сервер Lync развернут и настроен на указание устаревшего пула или режиссера, требуется сайт дополнительного пограничного сервера, который указывает на пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f527a-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="f527a-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span><span class="sxs-lookup"><span data-stu-id="f527a-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="f527a-117">Взаимодействие системы комнаты Skype с использованием пула Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f527a-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="f527a-118">Если пользователь, размещенный на сервере Lync Server 2010, планирует собрание и приглашает учетную запись системы комнаты для помещения в Skype, то при участии в собрании клиентская система комнаты Skype будет работать с ограниченными возможностями.</span><span class="sxs-lookup"><span data-stu-id="f527a-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="f527a-119">Когда клиент системы комнаты Skype присоединяется к запланированным звонкам, которые упорядочены пользователем, настроенным на Lync Server 2010, в системе комнат Skype предусмотрены следующие ограничения для собраний.</span><span class="sxs-lookup"><span data-stu-id="f527a-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="f527a-120">Система комнат Skype не может показать коллекцию видео с несколькими представлениями.</span><span class="sxs-lookup"><span data-stu-id="f527a-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="f527a-121">Если в качестве выступающего есть клиент системы комнаты Skype, он не сможет применять блокировку видео для участников.</span><span class="sxs-lookup"><span data-stu-id="f527a-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="f527a-122">Система комнат Skype не может отобразить разрешение 1080p (входящее или исходящее), даже если эта возможность разрешена политикой конференц-связи Lync Server 2013, из-за указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="f527a-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="f527a-123">Lync Server 2010 не поддерживает разрешение 1080p.</span><span class="sxs-lookup"><span data-stu-id="f527a-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="f527a-124">Система комнат Skype всегда ограничивается политикой конференц-связи организатора для разрешения видеосигнала.</span><span class="sxs-lookup"><span data-stu-id="f527a-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="f527a-125">Таким образом, даже если пул Lync 2010 поддерживает разрешение 720p, система комнат Skype не сможет использовать преимущества разрешения 720p, так как она не поддерживается политикой организатора.</span><span class="sxs-lookup"><span data-stu-id="f527a-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="f527a-p105">Клиенты Lync 2013 обнаруживают присутствие LRS в комнате переговоров и автоматически отключают звук для себя, чтобы избежать возникновения эха в физической комнате переговоров. Эта функция не работает в собраниях, размещенных в системе Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="f527a-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="f527a-128">Для собраний, размещенных в системе Lync Server 2010, имеются ограничения по совместному использованию рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="f527a-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="f527a-129">Пользователи не смогут присоединиться к частным (ограниченным) собраниям, размещенным в Lync 2010, в системе комнат Skype.</span><span class="sxs-lookup"><span data-stu-id="f527a-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

