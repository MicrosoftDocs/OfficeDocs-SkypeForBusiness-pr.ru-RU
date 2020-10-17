---
title: 'Lync Server 2013: Включение политики сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 794fe378f9e7d8024f4bc06000d6d7d1cd89481e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528576"
---
# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a><span data-ttu-id="b7d9f-102">Включение политики сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7d9f-102">Enable Persistent Chat Server policy in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7d9f-103">_**Последнее изменение темы:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="b7d9f-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="b7d9f-104">В панели управления Lync Server 2013 вы можете использовать страницу **Политика сохраняемого** чата для группы **сохраняемого чата** для управления политиками на глобальном уровне, уровне пула, сайта или пользователя, включая настройку глобальной политики по умолчанию и создание одной или нескольких дополнительных политик для пользователей и сайтов для развертывания.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-104">In the Lync Server 2013 Control Panel, you can use the **Persistent Chat Policy** page of the **Persistent Chat** group to manage policies at a global, pool, site, or user level, including configuring the default global policy and creating one or more additional user and site policies for your deployment.</span></span> <span data-ttu-id="b7d9f-105">Если для пользователя включена политика для сервера сохраняемого чата, среда сервера сохраняемого чата отображается в своем клиенте Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-105">If a user is enabled for Persistent Chat Server by policy, then the Persistent Chat Server environment appears in their Lync 2013 client.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7d9f-106">В топологии политики сайта сервера сохраняемого чата применяются глобально, на пул пользователей или на сайт пользователя или на каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-106">In the topology, Persistent Chat Server site policies apply globally, per user’s pool, or per user’s site, or per user.</span></span>



</div>

<span data-ttu-id="b7d9f-107">Глобальная политика создается автоматически при развертывании сервера сохраняемого чата и может быть настроена, но не удалена.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-107">The global policy is created automatically when you deploy Persistent Chat Server, and it can be configured, but not deleted.</span></span> <span data-ttu-id="b7d9f-108">Поскольку глобальная политика применяется ко всем пользователям, ее не требуется задавать для отдельных пользователей.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-108">Because the global policy applies to all users, it doesn’t have to be set per user.</span></span>

<span data-ttu-id="b7d9f-109">Вы можете создать и настроить несколько политик сайтов и пользователей, которые вместе с глобальной политикой позволяют пользователям использовать сервер сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-109">You can create and configure multiple site and user policies which, together with the global policy, enable users for Persistent Chat Server.</span></span> <span data-ttu-id="b7d9f-110">Политики сервера сохраняемого чата для пула и сайта переопределяют глобальную политику сервера сохраняемого чата, но только для пользователей этого сайта.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-110">Pool and site Persistent Chat Server policies override the global Persistent Chat Server policy, but only for users of that site.</span></span> <span data-ttu-id="b7d9f-111">Политики пользователей переопределяют как глобальную политику, так и политики пулов и сайтов для тех пользователей, кому назначены такие политики пользователей.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-111">User policies override both global, pool, and site policies for the users to whom the user policy is assigned.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b7d9f-112">Чтобы настроить и использовать сервер сохраняемого чата, сначала необходимо использовать построитель топологий, чтобы добавить в топологию поддержку сервера сохраняемого чата, а затем опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-112">To configure and use Persistent Chat Server, you must first use Topology Builder to add Persistent Chat Server support to the topology, and then publish the topology.</span></span> <span data-ttu-id="b7d9f-113">Дополнительные сведения см. в статье <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Добавление сервера сохраняемого чата в развертывание в Lync Server 2013</A> в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b7d9f-113">For details, see <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Adding Persistent Chat Server to your deployment in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b7d9f-114">Содержание</span><span class="sxs-lookup"><span data-stu-id="b7d9f-114">In This Section</span></span>

  - [<span data-ttu-id="b7d9f-115">Настройка глобальной политики для сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7d9f-115">Configure the global policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [<span data-ttu-id="b7d9f-116">Создание политики сайта для сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7d9f-116">Create a site policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [<span data-ttu-id="b7d9f-117">Создание пользовательской политики для сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7d9f-117">Create a user policy for Persistent Chat in Lync Server 2013</span></span>](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [<span data-ttu-id="b7d9f-118">Применение политики сохраняемого чата к пользователю или группе пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7d9f-118">Apply a Persistent Chat policy to a user or user group in Lync Server 2013</span></span>](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

