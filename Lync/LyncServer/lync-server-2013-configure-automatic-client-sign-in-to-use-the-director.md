---
title: 'Lync Server 2013: Настройка автоматической Sign-In клиента для использования директора'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Automatic Client Sign-In to use the Director
ms:assetid: 85369ffc-53ae-43be-8a23-84a094faecff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398678(v=OCS.15)
ms:contentKeyID: 48184703
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e174e55a2564dcf60b0405819e2996e4bf3d8f95
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48522966"
---
# <a name="configure-automatic-client-sign-in-to-use-the-director-in-lync-server-2013"></a><span data-ttu-id="3716f-102">Настройка автоматического клиентского Sign-In для использования директора в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3716f-102">Configure Automatic Client Sign-In to use the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3716f-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="3716f-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="3716f-104">При развертывании Lync Server 2013, Director или пул директоров рекомендуется использовать автоматические клиентские Sign-In.</span><span class="sxs-lookup"><span data-stu-id="3716f-104">When you deploy a Lync Server 2013, Director or a pool of Directors, we recommend that you use Automatic Client Sign-In as a best practice.</span></span> <span data-ttu-id="3716f-105">Сведения о настройке DNS-серверов для автоматического входа клиентов приведены в статье [требования к DNS для автоматического входа клиентов в Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="3716f-105">For details about how to configure DNS servers for automatic client sign-in, see [DNS requirements for automatic client sign-in in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md) in the Planning documentation.</span></span>

<span data-ttu-id="3716f-106">Если вы уже развернули функцию автоматического входа клиента, см. следующие разделы для получения инструкций по ее настройки в директорах.</span><span class="sxs-lookup"><span data-stu-id="3716f-106">If you have already deployed Automatic Client Sign-In, see the following sections to configure it on your Director(s).</span></span>

<div>

## <a name="single-director-instance"></a><span data-ttu-id="3716f-107">Один экземпляр директора</span><span class="sxs-lookup"><span data-stu-id="3716f-107">Single Director Instance</span></span>

<span data-ttu-id="3716f-108">Если вы уже развернули автоматические клиентские Sign-In и указываете на сервер переднего плана или интерфейсный пул, необходимо изменить запись SRV DNS, чтобы она указывала на директорию.</span><span class="sxs-lookup"><span data-stu-id="3716f-108">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director.</span></span>

</div>

<div>

## <a name="director-pool"></a><span data-ttu-id="3716f-109">Пул директоров</span><span class="sxs-lookup"><span data-stu-id="3716f-109">Director Pool</span></span>

<span data-ttu-id="3716f-110">Если вы уже развернули автоматические клиентские Sign-In и указываете на сервер переднего плана или интерфейсный пул, необходимо изменить запись SRV DNS, чтобы она указывала на пул директоров.</span><span class="sxs-lookup"><span data-stu-id="3716f-110">If you already have Automatic Client Sign-In deployed and it is pointing to a Front End Server or a Front End pool, you need to change the DNS SRV record to point to the Director pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

