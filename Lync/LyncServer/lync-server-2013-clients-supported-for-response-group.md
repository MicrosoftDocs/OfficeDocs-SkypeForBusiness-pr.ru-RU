---
title: 'Lync Server 2013: клиенты, поддерживаемые для группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Clients supported for Response Group
ms:assetid: 84911025-e754-41a8-ba48-e31c058fc557
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398674(v=OCS.15)
ms:contentKeyID: 48184705
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2082f3d41f3907f4b2a1d541b2c2000becd91c89
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="clients-supported-for-response-group-in-lync-server-2013"></a><span data-ttu-id="c0ade-102">Клиенты, поддерживаемые для группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0ade-102">Clients supported for Response Group in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0ade-103">_**Последнее изменение темы:** 2014-03-28_</span><span class="sxs-lookup"><span data-stu-id="c0ade-103">_**Topic Last Modified:** 2014-03-28_</span></span>

<span data-ttu-id="c0ade-104">Приложение группы ответа поддерживает следующие клиенты:</span><span class="sxs-lookup"><span data-stu-id="c0ade-104">The Response Group application supports the following clients:</span></span>

  - <span data-ttu-id="c0ade-105">Клиент Lync 2013 для настольных ПК</span><span class="sxs-lookup"><span data-stu-id="c0ade-105">Lync 2013 desktop client</span></span>

  - <span data-ttu-id="c0ade-106">Клиент Lync 2010 для настольных ПК</span><span class="sxs-lookup"><span data-stu-id="c0ade-106">Lync 2010 desktop client</span></span>

  - <span data-ttu-id="c0ade-107">Lync 2010 Attendant</span><span class="sxs-lookup"><span data-stu-id="c0ade-107">Lync 2010 Attendant</span></span>

  - <span data-ttu-id="c0ade-108">Помощник Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="c0ade-108">Office Communications Server 2007 R2 Attendant</span></span>

  - <span data-ttu-id="c0ade-109">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="c0ade-109">Lync Phone Edition</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c0ade-110">Приложение группы ответа не поддерживается в клиентах Lync Mobile.</span><span class="sxs-lookup"><span data-stu-id="c0ade-110">The Response Group application is not supported on Lync mobile clients.</span></span>



</div>

<span data-ttu-id="c0ade-111">Для получения дополнительных сведений о новых возможностях обратитесь к разделу [новые функции приложения группы ответа в Lync Server 2013](lync-server-2013-new-response-group-application-features.md) в документации "Приступая к работе".</span><span class="sxs-lookup"><span data-stu-id="c0ade-111">For details about new features, see [New Response Group application features in Lync Server 2013](lync-server-2013-new-response-group-application-features.md) in the Getting Started documentation.</span></span>

<span data-ttu-id="c0ade-112">Используемый клиент зависит от типа пользователя группы ответа, который вы используете:</span><span class="sxs-lookup"><span data-stu-id="c0ade-112">The specific client that you can use depends on the type of Response Group user that you are:</span></span>

  - <span data-ttu-id="c0ade-113">**Вызывающие** могут вызывать группу ответа с помощью любого вышеуказанного клиента или обычного телефона ТСОП.</span><span class="sxs-lookup"><span data-stu-id="c0ade-113">**Callers** can call a response group by using any of the clients listed previously, and by using a standard telephone over the public switched telephone network (PSTN).</span></span>

  - <span data-ttu-id="c0ade-114">**Неформальные агенты** (агенты, которые не входят в свои группы для принятия вызовов) могут принимать звонки с помощью помощника, Lync или Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="c0ade-114">**Informal agents** (agents who do not sign into and out of their groups to accept calls) can accept calls by using Attendant, Lync, or Lync Phone Edition.</span></span> <span data-ttu-id="c0ade-115">Неформальные агенты автоматически подписываются в свои группы при входе в Lync Server 2013 с помощью одного из этих клиентов.</span><span class="sxs-lookup"><span data-stu-id="c0ade-115">Informal agents are automatically signed into their groups when they sign in to Lync Server 2013 by using one of these clients.</span></span>

  - <span data-ttu-id="c0ade-116">**Формальные агенты** (агенты, которые должны входить в свои группы и принимать звонки) могут принимать звонки с помощью Lync 2013 и доступа к консоли агента из элемента меню, а также с помощью помощника и доступа к консоли агента непосредственно из Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="c0ade-116">**Formal agents** (agents who must sign into and out of their groups to accept calls) can accept calls by using Lync 2013 and accessing the agent console from the menu item, or by using Attendant and accessing the agent console directly from Internet Explorer.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

