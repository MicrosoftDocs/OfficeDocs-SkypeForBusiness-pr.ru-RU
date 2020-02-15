---
title: 'Lync Server 2013: планирование для сервера сохраняемого чата'
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
ms.openlocfilehash: cf28684443b93dbd6d3d1d769ca545177f6cfa0f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049981"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="0c4e5-102">Планирование сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c4e5-102">Planning for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c4e5-103">_**Последнее изменение темы:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="0c4e5-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="0c4e5-104">Вы можете использовать Lync Server 2013, сервер сохраняемого чата, чтобы разрешить нескольким пользователям принимать участие в беседах, в которых они разноски и получать доступ к содержимому определенных разделов, в том числе текста, ссылок и файлов.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="0c4e5-105">Хотя пользователи в течение сеанса могут взаимодействовать в режиме реального времени, контент каждого сеанса является постоянным, и доступен после окончания сеанса.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-105">Although users can communicate in real time during a session, the content of each session is persistent, which means it continues to be available after a session ends.</span></span>

<span data-ttu-id="0c4e5-106">В этом разделе описываются вопросы планирования развертывания сервера сохраняемого чата в Lync Server 2013, в том числе определение требований, определение компонентов и поддерживаемых топологий, а также рекомендации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0c4e5-106">This section describes planning considerations in a Lync Server 2013, Persistent Chat Server deployment, including defining requirements, identifying components and supported topologies, and deployment recommendations.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0c4e5-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="0c4e5-107">In This Section</span></span>

  - [<span data-ttu-id="0c4e5-108">Обзор сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c4e5-108">Overview of Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-overview-of-persistent-chat-server.md)

  - [<span data-ttu-id="0c4e5-109">Принцип работы сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c4e5-109">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="0c4e5-110">Определение требований Организации для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c4e5-110">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="0c4e5-111">Компоненты и топологии для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c4e5-111">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-persistent-chat-server.md)

  - [<span data-ttu-id="0c4e5-112">Технические требования для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c4e5-112">Technical requirements for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-persistent-chat-server.md)

  - [<span data-ttu-id="0c4e5-113">Настройка систем и инфраструктуры для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c4e5-113">Setting up systems and infrastructure for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-setting-up-systems-and-infrastructure-for-persistent-chat-server.md)

  - [<span data-ttu-id="0c4e5-114">Контрольный список развертывания для сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c4e5-114">Deployment checklist for Persistent Chat Server in Lync Server 2013</span></span>](lync-server-2013-deployment-checklist-for-persistent-chat-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

