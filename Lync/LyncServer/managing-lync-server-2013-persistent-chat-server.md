---
title: Управление Lync Server 2013 и сервером сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing Lync Server 2013, Persistent Chat Server
ms:assetid: 82befdc6-5d32-45f1-bfd7-aaedffed1ab8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398657(v=OCS.15)
ms:contentKeyID: 48184672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: de49e9843c5243457d1c4d736d9bfeda246f042e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="69f21-102">Управление Lync Server 2013 и сервером сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="69f21-102">Managing Lync Server 2013, Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="69f21-103">_**Тема последнего изменения:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="69f21-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="69f21-104">Вы можете использовать сервер Lync Server 2013, сохраняемый чат, чтобы позволить нескольким пользователям принимать участие в беседах, в которых они разносится и обращаются к содержимому определенных тем, в том числе к тексту, ссылкам и файлам.</span><span class="sxs-lookup"><span data-stu-id="69f21-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="69f21-105">Несмотря на то, что пользователи могут общаться в реальном времени во время сеанса, содержимое каждого сеанса сохраняется, а это значит, что после завершения сеанса оно продолжает быть доступным.</span><span class="sxs-lookup"><span data-stu-id="69f21-105">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="69f21-106">Содержимое сохраняемых комнат чатов обычно состоит из коротких текстовых сообщений, хотя оно может включать более длинные сообщения, которые называются *материалами*, а также гиперссылки, смайлики и загруженные документы.</span><span class="sxs-lookup"><span data-stu-id="69f21-106">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="69f21-107">Загрузка и скачивание файлов в клиенте Lync 2013 не поддерживается. Однако он по-прежнему поддерживается Lync Server 2013, сервером сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="69f21-107">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="69f21-108">Старый клиент группового чата может публиковать и просматривать файлы, но если доступ к одной комнате чата осуществляется через клиент Lync 2013, доступ к этим файлам будет невозможен.</span><span class="sxs-lookup"><span data-stu-id="69f21-108">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="69f21-109">Доступ к комнате чата осуществляется с помощью списка участников.</span><span class="sxs-lookup"><span data-stu-id="69f21-109">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="69f21-110">Вся история комнаты чата доступна любому участнику для хронологической проверки или полнотекстового поиска.</span><span class="sxs-lookup"><span data-stu-id="69f21-110">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="69f21-111">Подробнее об использовании клиента сохраняемого чата можно узнать в разделе [Планирование клиентов в Lync server 2013](lync-server-2013-planning-for-clients.md) в документации по планированию, а также [развертывание клиентов и устройств в Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="69f21-111">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="69f21-112">При настройке постоянного сервера чата для организации вы указываете начальную конфигурацию во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="69f21-112">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="69f21-113">Тем не менее иногда требуется изменить способ реализации поддержки сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="69f21-113">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="69f21-114">Например, может потребоваться настройка поддержки сервера сохраняемого чата и элементов управления для определенной группы или группы в Организации.</span><span class="sxs-lookup"><span data-stu-id="69f21-114">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="69f21-115">В этом разделе приводятся сведения и процедуры, которые помогут вам настроить развертывание сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="69f21-115">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="69f21-116">Дополнительные сведения о функциях и функциях, которые можно настроить для работы с сохраняемым сервером чата, приведены в разделе [Определение требований Организации к постоянному серверу чата в Lync server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) в документации по планированию и [о том, как вести сохраняемый чат. Сервер работает в Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="69f21-116">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="69f21-117">Дополнительные сведения о развертывании сервера сохраняемого чата для Lync Server 2013 можно найти в разделе [развертывание сервера сохраняемого чата в Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="69f21-117">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="69f21-118">Содержание</span><span class="sxs-lookup"><span data-stu-id="69f21-118">In This Section</span></span>

  - [<span data-ttu-id="69f21-119">Как работает сервер сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69f21-119">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="69f21-120">Использование категорий для администрирования сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="69f21-120">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="69f21-121">Сведения о членстве в постоянном чате</span><span class="sxs-lookup"><span data-stu-id="69f21-121">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="69f21-122">Рекомендации по работе с сервером сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="69f21-122">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="69f21-123">Управление категориями, чатами и надстройками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69f21-123">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="69f21-124">Управление доступом пользователей к сохраняемому чату в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69f21-124">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="69f21-125">Эксплуатация и обслуживание системы сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="69f21-125">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

