---
title: 'Lync Server 2013: настройка автоматического входа клиента для использования директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63e885080879b2b7ce3cf87557b21822fe9cd26f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="7d45c-102">Настройка автоматического входа клиента для использования директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d45c-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d45c-103">_**Тема последнего изменения:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="7d45c-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="7d45c-104">При развертывании Lync Server 2013, Director или пула директоров рекомендуется использовать автоматический вход в службу.</span><span class="sxs-lookup"><span data-stu-id="7d45c-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="7d45c-105">Дополнительные сведения о том, как настроить DNS-серверы для автоматического входа в клиент, приведены в разделе [требования к DNS для автоматического входа в службу в Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="7d45c-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="7d45c-106">Если вы уже развернули функцию автоматического входа в систему, ознакомьтесь со следующими разделами, чтобы настроить ее для вашего режиссера (-ов).</span><span class="sxs-lookup"><span data-stu-id="7d45c-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="7d45c-107">Один экземпляр режиссера</span><span class="sxs-lookup"><span data-stu-id="7d45c-107">Single Director Instance</span></span>

<span data-ttu-id="7d45c-108">Если вы уже развернули автоматический вход на клиент и указываете на сервер переднего плана или пул переднего плана, вам нужно изменить DNS SRV-запись, чтобы она указывала на режиссер.</span><span class="sxs-lookup"><span data-stu-id="7d45c-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="7d45c-109">Пул режиссеров</span><span class="sxs-lookup"><span data-stu-id="7d45c-109">Director Pool</span></span>

<span data-ttu-id="7d45c-110">Если вы уже развернули автоматический вход на клиент и указываете на сервер переднего плана или пул переднего плана, вам нужно изменить DNS SRV-запись, чтобы она указывала на пул каталогов.</span><span class="sxs-lookup"><span data-stu-id="7d45c-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

