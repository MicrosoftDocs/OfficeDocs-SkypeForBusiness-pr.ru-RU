---
title: 'Lync Server 2013: планирование для сервера сохраняемого чата'
description: 'Lync Server 2013: планирование для сервера сохраняемого чата.'
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
ms.openlocfilehash: 6944437492a1eee718a614369201c3548c95864a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549305"
---
# <a name="planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="bdd84-103">Планирование сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd84-103">Planning for Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bdd84-104">_**Последнее изменение темы:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="bdd84-104">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="bdd84-105">Вы можете использовать Lync Server 2013, сервер сохраняемого чата, чтобы разрешить нескольким пользователям принимать участие в беседах, в которых они разноски и получать доступ к содержимому определенных разделов, в том числе текста, ссылок и файлов.</span><span class="sxs-lookup"><span data-stu-id="bdd84-105">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="bdd84-106">Хотя пользователи в течение сеанса могут взаимодействовать в режиме реального времени, контент каждого сеанса является постоянным, и доступен после окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="bdd84-106">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

<span data-ttu-id="bdd84-107">В этом разделе описываются вопросы планирования развертывания сервера сохраняемого чата в Lync Server 2013, в том числе определение требований, определение компонентов и поддерживаемых топологий, а также рекомендации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="bdd84-107">This section describes planning considerations in a Lync Server 2013, Persistent Chat Server deployment, including defining requirements, identifying components and supported topologies, and deployment recommendations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bdd84-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="bdd84-108">In This Section</span></span>

  - [<span data-ttu-id="bdd84-109">Обзор сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd84-109">Overview of Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-overview-of-persistent-chat-server.md)

  - [<span data-ttu-id="bdd84-110">Принцип работы сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd84-110">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="bdd84-111">Определение требований Организации для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd84-111">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="bdd84-112">Компоненты и топологии для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd84-112">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-persistent-chat-server.md)

  - [<span data-ttu-id="bdd84-113">Технические требования для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd84-113">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="bdd84-114">Настройка систем и инфраструктуры для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd84-114">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="bdd84-115">Контрольный список развертывания для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bdd84-115">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

