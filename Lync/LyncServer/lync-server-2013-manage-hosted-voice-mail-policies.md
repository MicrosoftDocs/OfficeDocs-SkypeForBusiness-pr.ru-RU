---
title: 'Lync Server 2013: управление политиками размещенной голосовой почты'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Manage hosted voice mail policies
ms:assetid: 50ff22e3-9c8b-4a33-a72f-d149892acf53
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398332(v=OCS.15)
ms:contentKeyID: 48184139
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 434cc1eb721635f4a56be33f48802da3bc6db0e3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="manage-hosted-voice-mail-policies-in-lync-server-2013"></a><span data-ttu-id="89a47-102">Управление политиками размещенной голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89a47-102">Manage hosted voice mail policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89a47-103">_**Тема последнего изменения:** 2012-09-20_</span><span class="sxs-lookup"><span data-stu-id="89a47-103">_**Topic Last Modified:** 2012-09-20_</span></span>

<span data-ttu-id="89a47-104">*Политика размещенной голосовой почты* предоставляет информацию в приложение Lync Server 2013 ексум о том, где следует перенаправлять звонки для пользователей, чьи почтовые ящики находятся на размещенной службе Exchange.</span><span class="sxs-lookup"><span data-stu-id="89a47-104">A *hosted voice mail policy* provides information to the Lync Server 2013 ExUM Routing application about where to route calls for users whose mailboxes are located on a hosted Exchange service.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="89a47-105">Как правило, требуется только одна политика размещенной голосовой почты.</span><span class="sxs-lookup"><span data-stu-id="89a47-105">Typically, only one hosted voice mail policy is required.</span></span> <span data-ttu-id="89a47-106">Во многих случаях вы можете изменить глобальную политику в соответствии с вашими потребностями.</span><span class="sxs-lookup"><span data-stu-id="89a47-106">In many cases, you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="89a47-107">Если вы создаете политику с областью сайта, она автоматически назначается всем пользователям, расположенным на указанном сайте.</span><span class="sxs-lookup"><span data-stu-id="89a47-107">If you create a policy with site scope, it is assigned automatically to all users homed at the specified site.</span></span> <span data-ttu-id="89a47-108">Если вы создаете политику с областью "на пользователя", необходимо явным образом назначать ее пользователям, группам и контактным объектам.</span><span class="sxs-lookup"><span data-stu-id="89a47-108">If you create a policy with per-user scope, you must explicitly assign it to users, groups, and contact objects.</span></span> <span data-ttu-id="89a47-109">Вы можете развернуть несколько политик размещенной голосовой почты, но в таком случае политики должны быть назначены для каждого пользователя отдельно.</span><span class="sxs-lookup"><span data-stu-id="89a47-109">It is possible to deploy multiple hosted voice mail policies, but in that case the policies must be assigned on a per-user basis.</span></span>



</div>

<span data-ttu-id="89a47-110">Дополнительные сведения о планировании политик размещенной голосовой почты можно найти [в разделе политики размещенной голосовой почты в Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="89a47-110">For details about planning hosted voice mail policies, see [Hosted voice mail policies in Lync Server 2013](lync-server-2013-hosted-voice-mail-policies.md) in the Planning documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="89a47-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="89a47-111">In This Section</span></span>

  - [<span data-ttu-id="89a47-112">Изменение политики глобальной размещенной голосовой почты в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89a47-112">Modify the global hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-modify-the-global-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="89a47-113">Создание политики размещенной голосовой почты на уровне сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89a47-113">Create a site-level hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-site-level-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="89a47-114">Создание политики размещенной голосовой почты для каждого пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89a47-114">Create a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-create-a-per-user-hosted-voice-mail-policy.md)

  - [<span data-ttu-id="89a47-115">Назначение политики размещенной голосовой почты для отдельных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="89a47-115">Assign a per-user hosted voice mail policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-hosted-voice-mail-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

