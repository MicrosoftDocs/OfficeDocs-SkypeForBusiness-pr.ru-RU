---
title: 'Lync Server 2013: назначение политик для отдельных пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user policies
ms:assetid: a4ed0120-d9e5-4eb2-acfd-8de2cb503652
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182561(v=OCS.15)
ms:contentKeyID: 48184971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a2b73e5f94bbc2b7ea7deae2359a005fa2291db
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48514926"
---
# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="32c6b-102">Назначение политик для отдельных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c6b-102">Assigning per-user policies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32c6b-103">_**Последнее изменение темы:** 2012-10-14_</span><span class="sxs-lookup"><span data-stu-id="32c6b-103">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="32c6b-p101">Чтобы задать параметры, отличные от параметров, которые заданы с помощью политик и назначены остальным пользователям, например с помощью глобальных политик, вы можете назначить отдельные политики пользователю или группе пользователей. Эти политики называются политиками на уровне пользователя.</span><span class="sxs-lookup"><span data-stu-id="32c6b-p101">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies. These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="32c6b-106">Содержание</span><span class="sxs-lookup"><span data-stu-id="32c6b-106">In This Section</span></span>

  - [<span data-ttu-id="32c6b-107">Назначение политики конференц-связи на уровне пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c6b-107">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="32c6b-108">Назначение политики версий клиентов на уровне пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c6b-108">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="32c6b-109">Назначение политики ПИН-кодов для отдельных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c6b-109">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="32c6b-110">Назначение политики доступа внешних пользователей пользователю, поддерживающему Lync, в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c6b-110">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="32c6b-111">Назначение политики архивации на уровне пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c6b-111">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="32c6b-112">Назначение политики расположения для отдельных пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c6b-112">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="32c6b-113">Назначение индивидуальной политики мобильности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c6b-113">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="32c6b-114">Назначение политики сохраняемого чата на уровне пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c6b-114">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="32c6b-115">Назначение политики абонентской группы на уровне пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c6b-115">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="32c6b-116">Назначение политики голосовой связи на уровне пользователя в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c6b-116">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="32c6b-117">См. также</span><span class="sxs-lookup"><span data-stu-id="32c6b-117">See Also</span></span>


[<span data-ttu-id="32c6b-118">Управление пользователями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32c6b-118">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

