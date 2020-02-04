---
title: 'Lync Server 2013: обзор отправки группового звонка'
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
ms.openlocfilehash: 0efc85b28a689b43d024d9996211a70dcd91cee0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755553"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-group-call-pickup-in-lync-server-2013"></a><span data-ttu-id="af430-102">Обзор отправки группового звонка в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="af430-102">Overview of Group Call Pickup in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="af430-103">_**Тема последнего изменения:** 2013-02-12_</span><span class="sxs-lookup"><span data-stu-id="af430-103">_**Topic Last Modified:** 2013-02-12_</span></span>

<span data-ttu-id="af430-104">Отправка группового звонка – новая функция в накопительных обновлениях для Lync Server 2013: Февраль 2013, позволяющая пользователям отвечать на входящие звонки своим коллегам со своих телефонов.</span><span class="sxs-lookup"><span data-stu-id="af430-104">Group Call Pickup, a new feature in Cumulative Updates for Lync Server 2013: February 2013, lets users answer incoming calls to their colleagues from their own phones.</span></span> <span data-ttu-id="af430-105">Эта новая функция повышает доступность строки пользователя, позволяя другим пользователям ответить на входящий звонок, набрав номер группы для отправки звонков.</span><span class="sxs-lookup"><span data-stu-id="af430-105">This new feature increases the availability of a user's line by enabling other users to answer an incoming call by dialing a call pickup group number.</span></span> <span data-ttu-id="af430-106">При развертывании отправки группового звонка количество входящих звонков, перенаправляемых на голосовую почту, может быть значительно уменьшено, что особенно полезно для звонков пользователей, которые являются внешними по отношению к вашей организации.</span><span class="sxs-lookup"><span data-stu-id="af430-106">When Group Call Pickup is deployed, the number of incoming calls that are routed to voice mail can be significantly reduced, which is particularly useful for calls from customers who are external to your organization.</span></span>

<span data-ttu-id="af430-107">Функция отправки группового звонка разработана специально для филиалов в открытых средах Office.</span><span class="sxs-lookup"><span data-stu-id="af430-107">The Group Call Pickup feature is designed in particular for business units in open office environments.</span></span> <span data-ttu-id="af430-108">Входящие звонки не отвлекают внимания, так как сигнал подается только по планируемому назначению.</span><span class="sxs-lookup"><span data-stu-id="af430-108">Incoming calls are not disruptive because they ring only at the intended destination.</span></span> <span data-ttu-id="af430-109">При этом другие пользователи, которые слышат сигнал, могут ответить на звонок, просто набрав номер группы.</span><span class="sxs-lookup"><span data-stu-id="af430-109">Other users who hear the ring, however, can still pick up the call simply by dialing the group number.</span></span>

<span data-ttu-id="af430-110">В средах, где размещение всех пользователей в одном офисном помещении не применяется либо где пользователи, обладающие схожими обязанностями, находятся в разных географических местоположениях, оптимальным решением будет групповой звонок.</span><span class="sxs-lookup"><span data-stu-id="af430-110">In environments where users are not located in an open office layout, or where users who share a common responsibility are geographically distributed, team call presents the most suitable solution.</span></span> <span data-ttu-id="af430-111">Основное различие между получением группового звонка и вызовом команды заключается в том, что при отправке звонков по групповым звонкам входящий звонок будет выполняться только в нужном месте, но любой пользователь по-прежнему может ответить на звонок, набрав номер группы.</span><span class="sxs-lookup"><span data-stu-id="af430-111">The primary difference between Group Call Pickup and team call is that, with Group Call Pickup, an incoming call rings only at the intended destination, but anyone can still choose to answer it by dialing a group number.</span></span> <span data-ttu-id="af430-112">При групповом звонке сигнал звучит на телефонах всех членов группы и любой пользователь из этой группы может поднять трубку и ответить на звонок.</span><span class="sxs-lookup"><span data-stu-id="af430-112">With team call, the call rings at all the team members' phones, and any user in the team can pick up the phone to answer the call.</span></span> <span data-ttu-id="af430-113">Дополнительная разница между получением группового звонка и вызовом команды заключается в том, что Управление обработкой групп осуществляется администратором на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af430-113">An additional difference between Group Call Pickup and team call is that Group Call Pickup is managed by an administrator, through Lync Server.</span></span> <span data-ttu-id="af430-114">При вызове команды конечные пользователи управляют этим компонентом с помощью клиента Lync.</span><span class="sxs-lookup"><span data-stu-id="af430-114">With team call, end users manage the feature by using the Lync client.</span></span> <span data-ttu-id="af430-115">Таким образом, при отправке группового звонка этот аспект управления звонками может быть централизованным.</span><span class="sxs-lookup"><span data-stu-id="af430-115">With Group Call Pickup, therefore, this aspect of call management can be centralized.</span></span>

<span data-ttu-id="af430-116">Отправка группового звонка осуществляется на основе приложения для парковки звонков.</span><span class="sxs-lookup"><span data-stu-id="af430-116">Group Call Pickup is built on the Call Park application.</span></span> <span data-ttu-id="af430-117">При развертывании группового приема звонков настраивается таблица «приостановка звонка» с разными диапазонами добавочных номеров, которые обозначаются как номера групп для отправки звонков.</span><span class="sxs-lookup"><span data-stu-id="af430-117">When you deploy Group Call Pickup, you configure the call park orbit table with separate ranges of extension numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="af430-118">Как и номера орбиты парковки вызовов, номера группы ответа на звонки должны быть виртуальными расширениями, которым не назначен пользователь или телефон.</span><span class="sxs-lookup"><span data-stu-id="af430-118">Like call park orbit numbers, call pickup group numbers must be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="af430-119">У каждого пула переднего плана, в котором вы развертываете раскладки группового звонка, может быть один или несколько диапазонов номеров групп для раскладки звонков.</span><span class="sxs-lookup"><span data-stu-id="af430-119">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="af430-120">Диапазоны номеров групп должны быть глобально уникальными в рамках развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af430-120">The group number ranges must be globally unique across the Lync Server deployment.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af430-121">Диапазоны номеров, обозначенные как номера для отправки групповых звонков в таблице "Приостановка звонка", нельзя управлять и просматривать с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="af430-121">Number ranges that are designated as Group Call Pickup numbers in the call park orbit table cannot be managed or viewed by using the Lync Server Control Panel.</span></span> <span data-ttu-id="af430-122">Единственный способ просмотреть все диапазоны номеров в таблице "приостановить Звонок" — это использовать командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="af430-122">The only way to see all the number ranges in the call park orbit table is to use Lync Server Management Shell.</span></span> <span data-ttu-id="af430-123">Аналогичным образом, чтобы добавить, изменить или удалить номера для отправки групповых звонков, используйте командную консоль Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="af430-123">Similarly, the only way to add, modify, or remove Group Call Pickup numbers is to use Lync Server Management Shell.</span></span>



</div>

<span data-ttu-id="af430-p106">После настройки номеров группы ответа на звонки вы назначаете пользователей группе ответа на звонки. На звонки, которые адресованы любому из пользователей, назначенных группе ответа на звонки, могут ответить другие пользователи. При поступлении звонка для пользователя, назначенного группе ответа на звонки, любой заметивший это пользователь может ответить на данный звонок, вручную набрав номер группы ответа на звонки. Отвечающий на звонок пользователь может и не быть членом данной группы. Когда на звонок отвечает другой пользователь, на исходный вызываемый номер отправляется соответствующее уведомление.</span><span class="sxs-lookup"><span data-stu-id="af430-p106">After you configure the call pickup group numbers, you assign users to a call pickup group. Any user who is assigned to a call pickup group can have their calls answered by other users. When a call comes in to a user who is assigned to a call pickup group, any other user who notices the call can answer it by manually dialing the call pickup group number. The user who picks up the call does not need to be a member of the group. When a call is picked up by another user, a notification is sent to the number originally called.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="af430-129">Пользователь может быть членом только одной группы ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="af430-129">A user can be a member of only one call pickup group.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="af430-130">Несмотря на то, что любой пользователь в развертывании Lync Server может ответить на звонок участнику группы отправки звонков, сотруднику, отвечающему за вызов, должен быть известен правильный номер группы для подбора звонков.</span><span class="sxs-lookup"><span data-stu-id="af430-130">Although any user in the Lync Server deployment can answer a call to a call pickup group member, the person answering the call must know the correct call pickup group number to dial.</span></span>



</div>

<span data-ttu-id="af430-131">Если пользователь набирает номер группы ответа на звонки, чтобы ответить на звонок, когда в группе звонят несколько телефонов, он переключается на тот звонок, который дольше всего находится в режиме ожидания.</span><span class="sxs-lookup"><span data-stu-id="af430-131">If a user dials a call pickup group number to answer a call when multiple phones in the group are ringing, the user answers the call that has been ringing the longest.</span></span>

<span data-ttu-id="af430-132">Параметры одновременных звонков будут активны для пользователей, имеющих групповой ответ на звонки.</span><span class="sxs-lookup"><span data-stu-id="af430-132">Simultaneous ringing settings will work for users who have group call pickup.</span></span> <span data-ttu-id="af430-133">Это значит, что звонок, сделанный пользователю, у которого есть Отправка группового звонка, будет звонить всем настроенным получателям, а другой пользователь может ответить на звонок.</span><span class="sxs-lookup"><span data-stu-id="af430-133">That is, a call made to a user who has Group Call Pickup will ring for all the configured destinations, and another user can answer the call.</span></span> <span data-ttu-id="af430-134">Исключением из данного правила является ситуация, когда пользователь настраивает одновременные звонки для вызова всех членов группы.</span><span class="sxs-lookup"><span data-stu-id="af430-134">The exception to this rule is when the user configures simultaneous ringing to call all the team members.</span></span>

<span data-ttu-id="af430-135">Отправка группового звонка не может использоваться для ответа на следующие типы звонков:</span><span class="sxs-lookup"><span data-stu-id="af430-135">Group Call Pickup cannot be used to answer the following types of calls:</span></span>

  - <span data-ttu-id="af430-136">Звонки по частной линии</span><span class="sxs-lookup"><span data-stu-id="af430-136">Calls to a private line</span></span>

  - <span data-ttu-id="af430-137">Звонки от контакта, которому назначен уровень конфиденциальности "Друзья и семья"</span><span class="sxs-lookup"><span data-stu-id="af430-137">Calls from a contact who has been assigned the Friends and Family privacy relationship</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="af430-138">Пользователь, который является членом группы приема звонков, может предотвратить получение определенных звонков посредством группового отправки, помечая контакт как личный контакт в клиенте Lync.</span><span class="sxs-lookup"><span data-stu-id="af430-138">A user who is a member of a call pickup group can prevent certain calls from being retrieved through Group Call Pickup by marking the contact as a personal contact in the Lync client.</span></span> <span data-ttu-id="af430-139">Чтобы сделать это, установите для контакта уровень конфиденциальности "Друзья и семья".</span><span class="sxs-lookup"><span data-stu-id="af430-139">To mark a contact as a personal contact, set the Privacy Relationship for the contact to Friends and Family.</span></span> <span data-ttu-id="af430-140">Любой входящий звонок из контактов с уровнем конфиденциальности "друзья и семья" не может быть получен с помощью группового приема звонков.</span><span class="sxs-lookup"><span data-stu-id="af430-140">Any incoming call from contacts with the Privacy Relationship set to Friends and Family cannot be retrieved by using Group Call Pickup.</span></span>

    
    </div>

  - <span data-ttu-id="af430-141">Видеосоставляющая голосовых звонков и видеозвонков</span><span class="sxs-lookup"><span data-stu-id="af430-141">Video portion of audio/video calls</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="af430-p109">Если пользователь отвечает на голосовой звонок или видеозвонок, то он получает только звук. Любой из собеседников может расширить звонок, чтобы добавить видеосоставляющую.</span><span class="sxs-lookup"><span data-stu-id="af430-p109">If a user answers an audio/video call, the user receives only the audio. Either the person calling or the person answering the call can escalate the call to add video.</span></span>

    
    </div>

  - <span data-ttu-id="af430-144">Одновременные звонки, направляемые членам группы групповых звонков</span><span class="sxs-lookup"><span data-stu-id="af430-144">Simultaneous ringing calls that are routed to team call members</span></span>

  - <span data-ttu-id="af430-145">Звонки, направляемые делегату</span><span class="sxs-lookup"><span data-stu-id="af430-145">Calls routed to a delegate</span></span>

  - <span data-ttu-id="af430-146">Звонки, направляемые в группу ответа</span><span class="sxs-lookup"><span data-stu-id="af430-146">Calls routed to a response group</span></span>

<span data-ttu-id="af430-147">Следующие типы пользователей не могут принимать участие в расправке группового звонка.</span><span class="sxs-lookup"><span data-stu-id="af430-147">The following types of users cannot participate in Group Call Pickup.</span></span> <span data-ttu-id="af430-148">Это значит, что они не должны включаться в группу раскладки группового звонка, и они не смогут принимать звонки для пользователей, для которых включена отправка группового звонка.</span><span class="sxs-lookup"><span data-stu-id="af430-148">That is, they should not be included in a Group Call Pickup group, and they cannot pick up calls for users who have Group Call Pickup enabled.</span></span>

  - <span data-ttu-id="af430-149">Пользователи, размещаемые в сети в гибридном развертывании</span><span class="sxs-lookup"><span data-stu-id="af430-149">Users who are homed online in a hybrid deployment</span></span>

  - <span data-ttu-id="af430-150">Пользователи, не размещенные в пуле Lync Server 2013 с накопительными обновлениями для Lync Server 2013: Февраль 2013 в локальном развертывании</span><span class="sxs-lookup"><span data-stu-id="af430-150">Users who are not homed on a Lync Server 2013 pool with Cumulative Updates for Lync Server 2013: February 2013 in an on-premises deployment</span></span>

<span data-ttu-id="af430-p111">Если никто не отвечает на звонок, адресованный члену группы ответа на звонки, выполняется перенаправление этого звонка в соответствии с параметрами клиента. То есть он попадает в голосовую почту или направляется в другое место, указанное в параметрах клиента.</span><span class="sxs-lookup"><span data-stu-id="af430-p111">If no one answers a call to a member of a call pickup group, the call is routed as specified in the client settings. That is, the call goes to voicemail or is forwarded to a different destination, as specified in the client settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

