---
title: 'Lync Server 2013: Планирование устойчивости голосовой связи для сайта филиала'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for branch-site voice resiliency
ms:assetid: 67713f57-3ded-4127-ac37-57d8099bf384
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398477(v=OCS.15)
ms:contentKeyID: 48184351
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56d340fbc45287dba232e19f7ba2d0ee74c847fc
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-branch-site-voice-resiliency-in-lync-server-2013"></a><span data-ttu-id="bc5ce-102">Планирование устойчивости голосовой связи для сайта филиала в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc5ce-102">Planning for branch-site voice resiliency in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc5ce-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="bc5ce-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="bc5ce-104">Если вы хотите обеспечить устойчивость сайта филиала, то есть у вас есть три варианта для этого:</span><span class="sxs-lookup"><span data-stu-id="bc5ce-104">If you want to provide branch-site resiliency, that is, high-availability Enterprise Voice service, you have three options for doing so:</span></span>

  - <span data-ttu-id="bc5ce-105">Устройство для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="bc5ce-105">Survivable Branch Appliance</span></span>

  - <span data-ttu-id="bc5ce-106">сервер для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="bc5ce-106">Survivable Branch Server</span></span>

  - <span data-ttu-id="bc5ce-107">Полное развертывание Lync Server на сайте филиала</span><span class="sxs-lookup"><span data-stu-id="bc5ce-107">A full Lync Server deployment at the branch site</span></span>

<span data-ttu-id="bc5ce-p101">Это руководство поможет вам определить, какое решение обеспечения устойчивости лучше всего подходит для вашей организации, и в зависимости от принятого решения выбрать вариант ТСОП-связи, подходящий для использования. Руководство также поможет вам лучше подготовиться к развертыванию выбранного решения с учетом предварительных требований и других факторов, которые необходимо принять во внимание при планировании.</span><span class="sxs-lookup"><span data-stu-id="bc5ce-p101">This guide will help you evaluate which resiliency solution is best for your organization and, based on your resiliency solution, which PSTN-connectivity solution to use. It will also help you prepare to deploy the solution that you choose by describing prerequisites and other planning considerations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bc5ce-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="bc5ce-110">In This Section</span></span>

  - [<span data-ttu-id="bc5ce-111">Функции устойчивости сайтов филиалов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc5ce-111">Branch-site resiliency features in Lync Server 2013</span></span>](lync-server-2013-branch-site-resiliency-features.md)

  - [<span data-ttu-id="bc5ce-112">Решения для обеспечения устойчивости сайтов филиалов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc5ce-112">Branch-site resiliency solutions in Lync Server 2013</span></span>](lync-server-2013-branch-site-resiliency-solutions.md)

  - [<span data-ttu-id="bc5ce-113">Требования к устойчивости сайтов филиалов для Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc5ce-113">Branch-site resiliency requirements for Lync Server 2013</span></span>](lync-server-2013-branch-site-resiliency-requirements.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

