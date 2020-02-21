---
title: 'Lync Server 2013: обзор группового ответа на звонки'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Group Call Pickup
ms:assetid: 3dc0eca8-c773-463c-96bb-9cd6afa2a840
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945623(v=OCS.15)
ms:contentKeyID: 51541466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d9001d3e89e07943915b923ec4bfa8abf2683c78
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216265"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="e2e59-102">Общие сведения о групповой отправке вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e2e59-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e2e59-103">_**Последнее изменение темы:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="e2e59-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="e2e59-104">Групповой ответ на звонки, новый компонент накопительных обновлений для Lync Server 2013: Февраль 2013, позволяет пользователям отвечать на входящие звонки своих коллег с собственных телефонов.</span><span class="sxs-lookup"><span data-stu-id="e2e59-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="e2e59-105">Эта новая функция повышает доступность линии пользователя, позволяя другим пользователям отвечать на входящие звонки с помощью набора номера группы ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="e2e59-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="e2e59-106">При развертывании отправки группового ответа количество входящих вызовов, направляемых на голосовую почту, может быть существенно уменьшено, что особенно полезно для звонков от клиентов, которые являются внешними по отношению к вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e2e59-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="e2e59-107">Функция ответа на групповые звонки разработана в частности для филиалов в открытых средах Office.</span><span class="sxs-lookup"><span data-stu-id="e2e59-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="e2e59-108">Входящие вызовы не являются критическими, так как они поприветствуются только в назначении.</span><span class="sxs-lookup"><span data-stu-id="e2e59-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="e2e59-109">Тем не менее, другие пользователи, которые прослушивают звонок, могут выполнить звонок просто, настраивая номер группы.</span><span class="sxs-lookup"><span data-stu-id="e2e59-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="e2e59-110">В средах, где пользователи не расположены в открытом макете Office, или если пользователи, совместно использующих общую ответственность, распределены по географическим подходящим решениям, командный вызов представляет наиболее подходящее решение.</span><span class="sxs-lookup"><span data-stu-id="e2e59-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="e2e59-111">Основное различие между групповой отправкой вызовов и групповой набираемым звонком состоит в том, что при ответе на вызов групп входящий звонок может осуществляться только в назначенном месте, но любой пользователь по-прежнему может ответить на него, наберите номер группы.</span><span class="sxs-lookup"><span data-stu-id="e2e59-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="e2e59-112">С помощью командного звонка звонки на все телефоны участников группы, а любой пользователь в группе может выбрать телефон для ответа на звонок.</span><span class="sxs-lookup"><span data-stu-id="e2e59-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="e2e59-113">Дополнительное различие между групповой отправкой звонков и вызовом группы заключается в том, что Управление обзвоном звонков осуществляется администратором с помощью Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e2e59-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="e2e59-114">При вызове команды конечные пользователи управляют компонентом с помощью клиента Lync.</span><span class="sxs-lookup"><span data-stu-id="e2e59-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="e2e59-115">Таким образом, при отправке звонков по группам такой аспект управления звонками может быть централизованным.</span><span class="sxs-lookup"><span data-stu-id="e2e59-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="e2e59-116">Групповой ответ на звонки создается на основе приложения парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="e2e59-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="e2e59-117">При развертывании группового ответа на звонки вы настраиваете таблицу орбит парковки вызовов с отдельными диапазонами добавочных номеров, которые определены как номера групп ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="e2e59-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="e2e59-118">Как и номера орбит парковки вызовов, Номера групп ответа на звонки должны быть виртуальными расширениями, которым не назначены пользователи или телефоны.</span><span class="sxs-lookup"><span data-stu-id="e2e59-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="e2e59-119">Каждый пул переднего плана, в котором развернута Групповая отправка звонков, может иметь один или несколько диапазонов номеров групп ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="e2e59-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="e2e59-120">Диапазоны номеров групп должны быть глобально уникальными в рамках развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e2e59-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e2e59-121">С помощью панели управления Lync Server невозможно управлять и просматривать диапазоны номеров, которые определяются как номера ответа групповой связи в таблице орбиты парковки вызовов.</span><span class="sxs-lookup"><span data-stu-id="e2e59-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="e2e59-122">Единственный способ просмотреть все диапазоны номеров в таблице орбит парковки вызовов — использовать командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e2e59-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="e2e59-123">Аналогично, единственный способ добавить, изменить или удалить номера раскладки вызовов групп — использовать командную консоль Lync Server.</span><span class="sxs-lookup"><span data-stu-id="e2e59-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="e2e59-124">После настройки номеров групп ответа на звонки пользователи назначаются группе ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="e2e59-124">After you configure the call pickup group numbers, you assign users to a call pickup group.</span></span> <span data-ttu-id="e2e59-125">Все пользователи, которым назначена группа ответа на звонки, могут отвечать на звонки других пользователей.</span><span class="sxs-lookup"><span data-stu-id="e2e59-125">Any user who is assigned to a call pickup group can have their calls answered by other users.</span></span> <span data-ttu-id="e2e59-126">Когда звонок поступает пользователю, которому назначена группа ответа на звонки, любой другой пользователь, который видит звонок, может ответить на него вручную, наберите номер группы ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="e2e59-126">When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number.</span></span> <span data-ttu-id="e2e59-127">Пользователь, который выбирает вызов, не обязательно должен быть членом группы.</span><span class="sxs-lookup"><span data-stu-id="e2e59-127">The user who picks up the call does not need to be a member of the group.</span></span> <span data-ttu-id="e2e59-128">Когда вызов забирается другим пользователем, ему отправляется уведомление о первоначальном вызове.</span><span class="sxs-lookup"><span data-stu-id="e2e59-128">When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e2e59-129">Пользователь может быть членом только одной группы ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="e2e59-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="e2e59-130">Хотя любой пользователь в развертывании Lync Server может ответить на звонок участнику группы ответа на звонки, пользователь, отвечающий за вызов, должен знать правильный номер группы ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="e2e59-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="e2e59-131">Если пользователь набирает номер группы ответа на звонки, чтобы ответить на вызов при вызове нескольких телефонов в группе, пользователь отвечает на вызов, вызывающий эту самую длинную сеть.</span><span class="sxs-lookup"><span data-stu-id="e2e59-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="e2e59-132">Параметры одновременных звонков будут работать для пользователей, у которых есть Групповая отправка звонков.</span><span class="sxs-lookup"><span data-stu-id="e2e59-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="e2e59-133">То есть вызов, выполненный пользователю, которому назначена групповая связь, будет звонить всем настроенным получателям, а другой пользователь может ответить на звонок.</span><span class="sxs-lookup"><span data-stu-id="e2e59-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="e2e59-134">Исключением из этого правила является, когда пользователь настраивает Одновременный звонок для вызова всех участников группы.</span><span class="sxs-lookup"><span data-stu-id="e2e59-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="e2e59-135">Групповое получение звонков не может использоваться для ответа на следующие типы вызовов:</span><span class="sxs-lookup"><span data-stu-id="e2e59-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="e2e59-136">Звонки в частную линию</span><span class="sxs-lookup"><span data-stu-id="e2e59-136">Calls to a private line</span></span>

  - <span data-ttu-id="e2e59-137">Звонки контакта, которым назначено отношение конфиденциальности "друзья и семья"</span><span class="sxs-lookup"><span data-stu-id="e2e59-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="e2e59-138">Пользователь, являющийся членом группы ответа на звонки, может предотвратить получение определенных вызовов через групповую отметку, помечая контакт как личный контакт в клиенте Lync.</span><span class="sxs-lookup"><span data-stu-id="e2e59-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="e2e59-139">Чтобы пометить контакт как личный, установите отношение конфиденциальности для контакта с друзьями и родственниками.</span><span class="sxs-lookup"><span data-stu-id="e2e59-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="e2e59-140">Любой входящий звонок от контактов с отношением конфиденциальности, установленный для друзей и семьи, не может быть получен с помощью групповой уведомления о звонках.</span><span class="sxs-lookup"><span data-stu-id="e2e59-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="e2e59-141">Видеочасть вызовов аудио-и видеосигнала</span><span class="sxs-lookup"><span data-stu-id="e2e59-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e2e59-142">Если пользователь отвечает на голосовой или видеозвонок, пользователь получает только звук.</span><span class="sxs-lookup"><span data-stu-id="e2e59-142">If a user answers an audio/video call, the user receives only the audio.</span></span> <span data-ttu-id="e2e59-143">Звонок абоненту или абоненту, отвечающему за вызов, может быть расширен для добавления видео.</span><span class="sxs-lookup"><span data-stu-id="e2e59-143">Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="e2e59-144">Одновременные звонки, направляемые участникам командных звонков</span><span class="sxs-lookup"><span data-stu-id="e2e59-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="e2e59-145">Вызовы, направляемые представителю</span><span class="sxs-lookup"><span data-stu-id="e2e59-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="e2e59-146">Звонки, направляемые в группу ответа</span><span class="sxs-lookup"><span data-stu-id="e2e59-146">Calls routed to a response group</span></span>

<span data-ttu-id="e2e59-147">Следующие типы пользователей не могут участвовать в групповой отправке звонков.</span><span class="sxs-lookup"><span data-stu-id="e2e59-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="e2e59-148">То есть их не следует включать в группу ответа на звонки, и они не могут совершать вызовы для пользователей, для которых включена поддержка группового ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="e2e59-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="e2e59-149">Пользователи, размещенные в сети в гибридном развертывании</span><span class="sxs-lookup"><span data-stu-id="e2e59-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="e2e59-150">Пользователи, которые не размещены в пуле Lync Server 2013 с накопительными пакетами обновления для Lync Server 2013: Февраль 2013 в локальном развертывании</span><span class="sxs-lookup"><span data-stu-id="e2e59-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="e2e59-151">Если никто не отвечает на вызов члена группы ответа на звонки, этот вызов направляется в соответствии с параметрами клиента.</span><span class="sxs-lookup"><span data-stu-id="e2e59-151">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings.</span></span> <span data-ttu-id="e2e59-152">То есть вызов отправляется в голосовую почту или перенаправляется в другое назначение, как указано в параметрах клиента.</span><span class="sxs-lookup"><span data-stu-id="e2e59-152">That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

