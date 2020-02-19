---
title: 'Lync Server 2013: прямые подключения SIP'
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
ms.openlocfilehash: 4e7491193d60aad3676400c91e9044b214237df3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135125"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="direct-sip-connections-in-lync-server-2013"></a><span data-ttu-id="7ce6a-102">Прямые подключения SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ce6a-102">Direct SIP connections in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7ce6a-103">_**Последнее изменение темы:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="7ce6a-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="7ce6a-104">Можно использовать *прямые подключения SIP* для подключения Lync Server к одному из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="7ce6a-104">You can use *direct SIP connections* to connect Lync Server to either of the following:</span></span>

  - <span data-ttu-id="7ce6a-105">IP-УАТС (Дополнительные сведения см. [в статье Параметры прямого развертывания SIP в Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="7ce6a-105">An IP-PBX (for details, see [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span></span>

  - <span data-ttu-id="7ce6a-106">Шлюз PSTN (Дополнительные сведения см. [в статье варианты развертывания шлюза PSTN в Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="7ce6a-106">A PSTN gateway (for details, see [PSTN gateway deployment options in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span></span>

<span data-ttu-id="7ce6a-107">Чтобы реализовать прямое подключение SIP, необходимо выполнить, по существу, те же действия по развертыванию, что и при реализации магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="7ce6a-107">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="7ce6a-108">В обоих случаях подключение реализуется с помощью внешнего интерфейса сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="7ce6a-108">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="7ce6a-109">Единственное отличие заключается в том, что магистрали SIP подключаются к внешнему объекту, такому как шлюз поставщика услуг Интернет-телефонии, и устанавливаются прямые подключения SIP к внутреннему объекту внутри локальной сети, например к шлюзу телефонной сети общего пользования (ТСОП) или УАТС на базе протокола IP.</span><span class="sxs-lookup"><span data-stu-id="7ce6a-109">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="7ce6a-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="7ce6a-110">In This Section</span></span>

  - [<span data-ttu-id="7ce6a-111">Параметры прямого развертывания SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ce6a-111">Direct SIP deployment options in Lync Server 2013</span></span>](lync-server-2013-direct-sip-deployment-options.md)

  - [<span data-ttu-id="7ce6a-112">Варианты развертывания шлюза PSTN в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7ce6a-112">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

