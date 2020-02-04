---
title: 'Lync Server 2013: планирование сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Persistent Chat Server
ms:assetid: 57b2f574-234e-4a5a-bb78-8823369ba79e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398381(v=OCS.15)
ms:contentKeyID: 48184190
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 363008c910c53f5b1b951bf57ba8663b4d4d970d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41750509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="4e9da-102">Планирование сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e9da-102">Planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4e9da-103">_**Тема последнего изменения:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="4e9da-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="4e9da-104">Вы можете использовать сервер Lync Server 2013, сохраняемый чат, чтобы позволить нескольким пользователям принимать участие в беседах, в которых они разносится и обращаются к содержимому определенных тем, в том числе к тексту, ссылкам и файлам.</span><span class="sxs-lookup"><span data-stu-id="4e9da-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="4e9da-105">Хотя пользователи в течение сеанса могут взаимодействовать в режиме реального времени, контент каждого сеанса сохраняется и остается доступным после окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="4e9da-105">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

<span data-ttu-id="4e9da-106">В этом разделе описаны вопросы планирования в среде Lync Server 2013, а также о том, как определять требования, идентифицировать компоненты и поддерживаемые топологии и рекомендации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="4e9da-106">This section describes planning considerations in a Lync Server 2013, Persistent Chat Server deployment, including defining requirements, identifying components and supported topologies, and deployment recommendations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4e9da-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="4e9da-107">In This Section</span></span>

  - [<span data-ttu-id="4e9da-108">Обзор сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e9da-108">Overview of Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-overview-of-persistent-chat-server.md)

  - [<span data-ttu-id="4e9da-109">Как работает сервер сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e9da-109">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="4e9da-110">Определение требований организации для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e9da-110">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="4e9da-111">Компоненты и топологии для постоянного сервера чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e9da-111">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-persistent-chat-server.md)

  - [<span data-ttu-id="4e9da-112">Технические требования для постоянного сервера чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e9da-112">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="4e9da-113">Настройка систем и инфраструктуры для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e9da-113">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="4e9da-114">Контрольный список развертывания для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4e9da-114">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

