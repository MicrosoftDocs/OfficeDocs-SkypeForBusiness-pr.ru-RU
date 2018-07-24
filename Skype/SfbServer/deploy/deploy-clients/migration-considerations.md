---
title: Рекомендации по перемещению системы комнат Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df9f33b6-0360-4354-b651-bd35da533e33
description: Прочтите этот раздел, чтобы узнать о развертывании системы комнаты Скайп в среде, где имеется несколько версий Скайп для Business Server и Lync Server.
ms.openlocfilehash: 24015d85ef82b3a175564f92504d7c0ca46e9d54
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20982750"
---
# <a name="skype-room-system-migration-considerations"></a><span data-ttu-id="8b706-103">Рекомендации по перемещению системы комнат Skype</span><span class="sxs-lookup"><span data-stu-id="8b706-103">Skype Room System migration considerations</span></span>
 
<span data-ttu-id="8b706-104">Прочтите этот раздел, чтобы узнать о развертывании системы комнаты Скайп в среде, где имеется несколько версий Скайп для Business Server и Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b706-104">Read this topic to learn about how to deploy Skype Room System in an environment that has multiple versions of Skype for Business Server and Lync Server.</span></span>
  
## <a name="migration-considerations"></a><span data-ttu-id="8b706-105">Рекомендации по перемещению</span><span class="sxs-lookup"><span data-stu-id="8b706-105">Migration considerations</span></span>

<span data-ttu-id="8b706-106">В этом разделе рекомендации при развертывании системы комнаты Скайп в среде нескольких пула, который включает в себя различными версиями Скайп Business Server, Lync Server или Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="8b706-106">This section provides guidance if you are deploying Skype Room System in a multi-pool environment that includes different versions of Skype for Business Server, Lync Server, or Office Communications Server 2007 R2.</span></span> 
  
<span data-ttu-id="8b706-107">Компонент Репликатор пользователей (UR) в Lync Server получает объектов-пользователей из Active Directory и помещает их в базе данных SQL Server серверной Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b706-107">The User Replicator (UR) component in Lync Server gets user objects from Active Directory and places them into the Lync Server back-end SQL Server database.</span></span> <span data-ttu-id="8b706-108">Объекты системы комнаты Скайп известно только UR в Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b706-108">Only the UR in Lync Server 2013 is aware of Skype Room System objects.</span></span> <span data-ttu-id="8b706-109">UR в предыдущих версиях Lync Server и Office Communications Server не определять атрибуты Active Directory, которые определяют объекты LRS и поэтому не знать о них.</span><span class="sxs-lookup"><span data-stu-id="8b706-109">The UR in previous versions of Lync Server and Office Communications Server do not detect the Active Directory attributes that designate LRS objects, and therefore was not aware of them.</span></span> 
  
<span data-ttu-id="8b706-110">Если Скайп комнаты системной учетной записью попытается войти в Lync и выполняет автоматическое обнаружение на основе SRV-записи или запись DNS A для поиска и выберите пункт этих учетных записей для предыдущей версии Lync Server или Office Communications Server, LRS будет получать 404 не найден ответ от  устаревшем пуле.</span><span class="sxs-lookup"><span data-stu-id="8b706-110">If a Skype Room System account tries to sign in to Lync , and performs auto discovery based on SRV record or DNS A record look up, and if those accounts point to a previous version of Lync Server or Office Communications Server, LRS will receive a 404 Not Found response from the legacy pool.</span></span> <span data-ttu-id="8b706-111">Устаревшего пула не сможет перенаправление системы Скайп помещения его домашнего пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b706-111">The legacy pool will not be able to redirect Skype Room System to its Lync Server 2013 home pool.</span></span> 
  
<span data-ttu-id="8b706-112">Эту проблему можно решить следующими способами:</span><span class="sxs-lookup"><span data-stu-id="8b706-112">You can address this problem with the following options:</span></span> 
  
- <span data-ttu-id="8b706-113">Сделайте так, чтобы запись SRV с автоматическим обнаружением (_sipinternaltls._tcp.contoso.com) указывала на пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b706-113">Point your autodiscover SRV record (_sipinternaltls._tcp.contoso.com) to Lync Server 2013 pool.</span></span>
    
- <span data-ttu-id="8b706-114">Если первый вариант невозможно, необходимо вручную настроить LRS и укажите адрес пула Lync Server 2013, настроив его непосредственно в Скайп комнаты системы консольное приложение.</span><span class="sxs-lookup"><span data-stu-id="8b706-114">If the first option isn't possible, you must manually configure LRS and provide the Lync Server 2013 pool address by directly configuring it in the Skype Room System console application.</span></span> 
    
- <span data-ttu-id="8b706-115">Если развернута система комнаты Скайп за пределами корпоративной сети и пограничного сервера Lync была развернута и настроена для указания на устаревшем пуле или директор, дополнительного пограничный сервер сайта является обязательным, который указывает на пул Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b706-115">If Skype Room System is deployed outside the corporate network, and a Lync Edge Server has been deployed and configured to point to a legacy pool or director, a secondary Edge Server site is required, which points to the Lync Server 2013 pool.</span></span> <span data-ttu-id="8b706-116">Обратитесь к документации по развертыванию пограничного сервера Дополнительные сведения о развертывании пограничного сервера-получателя.</span><span class="sxs-lookup"><span data-stu-id="8b706-116">Refer to the Edge Server deployment documentation for more information about deploying a secondary Edge Server.</span></span> 
    
## <a name="skype-room-system-interoperability-with-a-lync-server-2010-pool"></a><span data-ttu-id="8b706-117">Взаимодействие системы Скайп помещений с пуле Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8b706-117">Skype Room System Interoperability with a Lync Server 2010 Pool</span></span>

<span data-ttu-id="8b706-118">Во время миграции Если пользователь, размещенный в пуле Lync Server 2010 планирует собрание с указанием Скайп комнаты системную учетную запись, клиент Скайп комнаты системы будет иметь ограниченную функциональность во время конференции собрания.</span><span class="sxs-lookup"><span data-stu-id="8b706-118">During migration, if a user who is homed on a Lync Server 2010 pool schedules a meeting and invites the Skype Room System account, the Skype Room System client will have limited functionality while attending the meeting.</span></span> 
  
<span data-ttu-id="8b706-119">При подключении клиента системы комнаты Скайп запланированного конференцию, были организованы пользователь, размещенный в Lync Server 2010, Скайп комнаты системы имеет следующие ограничения во время собрания:</span><span class="sxs-lookup"><span data-stu-id="8b706-119">When the Skype Room System client joins a scheduled conference call that has been organized by a user homed on Lync Server 2010, Skype Room System has the following in-meeting limitations:</span></span> 
  
- <span data-ttu-id="8b706-120">Система комнаты Скайп не удается отобразить видеоколлекция MultiView.</span><span class="sxs-lookup"><span data-stu-id="8b706-120">Skype Room System cannot show the multi-view video gallery.</span></span>
    
- <span data-ttu-id="8b706-121">Если клиент системы комнаты Скайп докладчиком, его нельзя применить видео блокировки на участников.</span><span class="sxs-lookup"><span data-stu-id="8b706-121">If the Skype Room System client is the presenter, it cannot apply video lock on participants.</span></span>
    
- <span data-ttu-id="8b706-122">Система комнаты Скайп не удается отобразить 1080p разрешение видео (входящих или исходящих), даже в том случае, если политика конференц-связи Lync Server 2013 допускает это, по следующим причинам:</span><span class="sxs-lookup"><span data-stu-id="8b706-122">Skype Room System cannot show 1080p video resolution (inbound or outbound), even if the Lync Server 2013 conferencing policy allows it, because of the following:</span></span> 
    
  - <span data-ttu-id="8b706-123">Lync Server 2010 не поддерживает решение 1080p.</span><span class="sxs-lookup"><span data-stu-id="8b706-123">Lync Server 2010 doesn't support 1080p resolution.</span></span>
    
  - <span data-ttu-id="8b706-124">Система комнаты Скайп всегда ограничен организатора политики конференц-связи для разрешения видео.</span><span class="sxs-lookup"><span data-stu-id="8b706-124">Skype Room System is always limited by the organizer's conferencing policy for video resolution.</span></span> <span data-ttu-id="8b706-125">Таким образом даже в том случае, если пул Lync 2010 поддерживает разрешение 720p, Скайп комнаты система не сможет воспользоваться преимуществами 720p решение, до тех пор, пока организатора политики не поддерживает его.</span><span class="sxs-lookup"><span data-stu-id="8b706-125">Therefore, even if the Lync 2010 pool supports 720p resolution, Skype Room System will not be able to take advantage of 720p resolution as long as organizer's policy doesn't support it.</span></span> 
    
- <span data-ttu-id="8b706-p105">Клиенты Lync 2013 обнаруживают присутствие LRS в комнате переговоров и автоматически отключают звук для себя, чтобы избежать возникновения эха в физической комнате переговоров. Эта функция не работает в собраниях, размещенных в системе Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="8b706-p105">Lync 2013 clients detect LRS presence in the meeting room, and they auto-mute themselves to avoid echo in the physical meeting room. This feature does not work in meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="8b706-128">Для собраний, размещенных в системе Lync Server 2010, имеются ограничения по совместному использованию рабочего стола.</span><span class="sxs-lookup"><span data-stu-id="8b706-128">There are limitations on desktop sharing performance for meetings hosted on Lync Server 2010.</span></span>
    
- <span data-ttu-id="8b706-129">Пользователи не смогут присоединиться к частной (ограниченный) собрания, которые размещаются в Lync 2010 с помощью системы Скайп помещений.</span><span class="sxs-lookup"><span data-stu-id="8b706-129">Users won't be able to join private (restricted) meetings that are hosted on Lync 2010 with Skype Room System.</span></span>
    

