---
title: 'Lync Server 2013: прямые подключения SIP'
description: 'Lync Server 2013: прямые подключения SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Direct SIP connections
ms:assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398151(v=OCS.15)
ms:contentKeyID: 48183357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebc42cd26472bbb19c7ef886a9449ab453b90680
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559675"
---
# <a name="direct-sip-connections-in-lync-server-2013"></a><span data-ttu-id="e4d4c-103">Прямые подключения SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4d4c-103">Direct SIP connections in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e4d4c-104">_**Последнее изменение темы:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="e4d4c-104">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="e4d4c-105">Можно использовать *прямые подключения SIP* для подключения Lync Server к одному из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="e4d4c-105">You can use *direct SIP connections* to connect Lync Server to either of the following:</span></span>

  - <span data-ttu-id="e4d4c-106">IP-УАТС (Дополнительные сведения см. [в статье Параметры прямого развертывания SIP в Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="e4d4c-106">An IP-PBX (for details, see [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span></span>

  - <span data-ttu-id="e4d4c-107">Шлюз PSTN (Дополнительные сведения см. [в статье варианты развертывания шлюза PSTN в Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="e4d4c-107">A PSTN gateway (for details, see [PSTN gateway deployment options in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span></span>

<span data-ttu-id="e4d4c-108">Чтобы реализовать прямое подключение SIP, необходимо выполнить, по существу, те же действия по развертыванию, что и при реализации магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-108">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="e4d4c-109">В обоих случаях подключение реализуется с помощью внешнего интерфейса сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-109">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="e4d4c-110">Единственное отличие заключается в том, что магистрали SIP подключаются к внешнему объекту, такому как шлюз поставщика услуг Интернет-телефонии, и устанавливаются прямые подключения SIP к внутреннему объекту внутри локальной сети, например к шлюзу телефонной сети общего пользования (ТСОП) или УАТС на базе протокола IP.</span><span class="sxs-lookup"><span data-stu-id="e4d4c-110">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e4d4c-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="e4d4c-111">In This Section</span></span>

  - [<span data-ttu-id="e4d4c-112">Параметры прямого развертывания SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4d4c-112">Direct SIP deployment options in Lync Server 2013</span></span>](lync-server-2013-direct-sip-deployment-options.md)

  - [<span data-ttu-id="e4d4c-113">Варианты развертывания шлюза PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e4d4c-113">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

