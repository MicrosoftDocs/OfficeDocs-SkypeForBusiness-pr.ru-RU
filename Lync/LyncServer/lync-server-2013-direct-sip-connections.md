---
title: 'Lync Server 2013: прямые соединения SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP connections
ms:assetid: 0a37737d-9628-4e36-b27b-c134fa5a3882
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398151(v=OCS.15)
ms:contentKeyID: 48183357
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1decdfd4c755ea1788d088a4b539d8c555987f02
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834397"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-connections-in-lync-server-2013"></a><span data-ttu-id="b7800-102">Прямые подключения по протоколу SIP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7800-102">Direct SIP connections in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7800-103">_**Тема последнего изменения:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="b7800-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="b7800-104">Вы можете использовать *прямые подключения* по протоколу SIP, чтобы подключить сервер Lync Server к одной из указанных ниже учетных данных.</span><span class="sxs-lookup"><span data-stu-id="b7800-104">You can use *direct SIP connections* to connect Lync Server to either of the following:</span></span>

  - <span data-ttu-id="b7800-105">IP-УАТС (Дополнительные сведения можно найти [в разделе Параметры развертывания Direct SIP в Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="b7800-105">An IP-PBX (for details, see [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md)).</span></span>

  - <span data-ttu-id="b7800-106">Шлюз PSTN (Дополнительные сведения можно найти [в разделе Параметры развертывания шлюза PSTN в Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span><span class="sxs-lookup"><span data-stu-id="b7800-106">A PSTN gateway (for details, see [PSTN gateway deployment options in Lync Server 2013](lync-server-2013-pstn-gateway-deployment-options.md)).</span></span>

<span data-ttu-id="b7800-107">Чтобы реализовать прямое соединение по протоколу SIP, вы должны следовать практически тем же инструкциям по развертыванию, как и при реализации магистральной магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="b7800-107">To implement a direct SIP connection, you follow essentially the same deployment steps as you would to implement a SIP trunk.</span></span> <span data-ttu-id="b7800-108">В обоих случаях вы реализуете соединение с помощью внешнего интерфейса сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="b7800-108">In both cases, you implement the connection by using the external interface of a Mediation Server.</span></span> <span data-ttu-id="b7800-109">Единственная разница заключается в том, что вы подключаете магистральные магистрали SIP к внешней сущности, например шлюзу ИТСП, и подключает прямые соединения по протоколу SIP к внутреннему объекту в локальной сети, например в IP-УАТС или коммутируемом коммутируемом шлюзе телефонной сети.</span><span class="sxs-lookup"><span data-stu-id="b7800-109">The only difference is that you connect SIP trunks to an external entity, such as an ITSP gateway, and you connect direct SIP connections to an internal entity within your local network, such as an IP-PBX or a public switched telephone network (PSTN) gateway.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b7800-110">Содержание</span><span class="sxs-lookup"><span data-stu-id="b7800-110">In This Section</span></span>

  - [<span data-ttu-id="b7800-111">Варианты развертывания прямого SIP-подключения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7800-111">Direct SIP deployment options in Lync Server 2013</span></span>](lync-server-2013-direct-sip-deployment-options.md)

  - [<span data-ttu-id="b7800-112">Параметры развертывания шлюза ТСОП в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7800-112">PSTN gateway deployment options in Lync Server 2013</span></span>](lync-server-2013-pstn-gateway-deployment-options.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

