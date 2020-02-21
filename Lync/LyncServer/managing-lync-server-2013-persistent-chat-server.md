---
title: Управление Lync Server 2013 и сервером сохраняемого чата
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server 2013, Persistent Chat Server
ms:assetid: 82befdc6-5d32-45f1-bfd7-aaedffed1ab8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398657(v=OCS.15)
ms:contentKeyID: 48184672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76f7f901d7616bce7481c7bfb654c1b34396d6e1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210165"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-persistent-chat-server"></a><span data-ttu-id="abd78-102">Управление Lync Server 2013 и сервером сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="abd78-102">Managing Lync Server 2013, Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abd78-103">_**Последнее изменение темы:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="abd78-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="abd78-104">Вы можете использовать Lync Server 2013, сервер сохраняемого чата, чтобы разрешить нескольким пользователям принимать участие в беседах, в которых они разноски и получать доступ к содержимому определенных разделов, в том числе текста, ссылок и файлов.</span><span class="sxs-lookup"><span data-stu-id="abd78-104">You can use Lync Server 2013, Persistent Chat Server to enable multiple users to participate in conversations in which they post and access content about specific topics, including text, links, and files.</span></span> <span data-ttu-id="abd78-105">Хотя в рамках сеанса пользователи могут общаться в режиме реального времени, содержимое каждого сеанса сохраняется, то есть остается доступным по завершении сеанса.</span><span class="sxs-lookup"><span data-stu-id="abd78-105">Although users can communicate in real time during a session, the content of each session is persistent, which means that it continues to be available after a session ends.</span></span>

<span data-ttu-id="abd78-106">Содержимое комнат сохраняемого чата в основном состоит из коротких текстовых сообщений, хотя оно может содержать более длинные сообщения, называемые *описаниями функциональности*, а также гиперссылки, значки настроения и отправленные документы.</span><span class="sxs-lookup"><span data-stu-id="abd78-106">The content of Persistent Chat rooms consists primarily of short text messages, although it can include longer messages, referred to as *stories*, and also hyperlinks, emoticons, and uploaded documents.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="abd78-107">Загрузка и скачивание файлов не поддерживаются клиентом Lync 2013; Однако он по-прежнему поддерживается Lync Server 2013 и сервером сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="abd78-107">File upload and download is not supported by the Lync 2013 client; however, it is still supported by Lync Server 2013, Persistent Chat Server.</span></span> <span data-ttu-id="abd78-108">Клиент группового чата прежних версий может выполнять запись и просмотр файлов, но если доступ к одной комнате чата через клиент Lync 2013, он не сможет получить доступ к этим файлам.</span><span class="sxs-lookup"><span data-stu-id="abd78-108">The legacy Group Chat client can post and view files, but if the same chat room is accessed via the Lync 2013 client, it will not be able to access the files.</span></span>



</div>

<span data-ttu-id="abd78-109">Доступ к комнате чата контролируется с помощью списка участников.</span><span class="sxs-lookup"><span data-stu-id="abd78-109">Access to a chat room is controlled by a membership list.</span></span> <span data-ttu-id="abd78-110">Журнал комнаты чата доступен любому участнику для просмотра в хронологическом порядке или полнотекстового поиска.</span><span class="sxs-lookup"><span data-stu-id="abd78-110">The entire chat room history is available to any member for chronological review or full-text search.</span></span> <span data-ttu-id="abd78-111">Сведения об использовании клиента сохраняемого чата приведены в статье [Планирование клиентов в Lync server 2013](lync-server-2013-planning-for-clients.md) в документации по планированию и [развертыванию клиентов и устройств в Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="abd78-111">For details about using the Persistent Chat client, see [Planning for clients in Lync Server 2013](lync-server-2013-planning-for-clients.md) in the Planning documentation, and [Deploying clients and devices in Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md) in the Deployment documentation.</span></span>

<span data-ttu-id="abd78-112">При настройке сервера сохраняемого чата для Организации необходимо указать начальную конфигурацию во время развертывания.</span><span class="sxs-lookup"><span data-stu-id="abd78-112">When you set up Persistent Chat Server for your organization, you specify the initial configuration during deployment.</span></span> <span data-ttu-id="abd78-113">Однако иногда может потребоваться изменить способ реализации поддержки сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="abd78-113">However, there may be times when you want to change how you implement Persistent Chat Server support.</span></span> <span data-ttu-id="abd78-114">Например, может потребоваться настроить поддержку сервера сохраняемого чата и управлять по-разному для определенной группы или группы в Организации.</span><span class="sxs-lookup"><span data-stu-id="abd78-114">For example, you may need to set up Persistent Chat Server support and controls differently for a specific team or group within your organization.</span></span> <span data-ttu-id="abd78-115">В этом разделе представлены сведения и процедуры, которые помогут вам настроить развертывание сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="abd78-115">This section provides information and procedures to help you customize your Persistent Chat Server deployment.</span></span> <span data-ttu-id="abd78-116">Дополнительные сведения о функциях и функциях, которые можно настроить для сервера сохраняемого чата, приведены в статье [Определение требований Организации для сервера сохраняемого чата в Lync server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) в документации по планированию, а [также о том, как сервер сохраняемого чата работает в Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="abd78-116">For details about the features and functionality that you can configure for Persistent Chat Server, see [Defining your organization's requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-defining-your-requirements-for-persistent-chat-server.md) in the Planning documentation, and [How Persistent Chat Server works in Lync Server 2013](lync-server-2013-how-persistent-chat-server-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="abd78-117">Сведения о развертывании сервера сохраняемого чата для Lync Server 2013 приведены в документации по развертыванию [сервера сохраняемого чата в Lync server 2013](lync-server-2013-deploying-persistent-chat-server.md) .</span><span class="sxs-lookup"><span data-stu-id="abd78-117">For details about deploying Persistent Chat Server for Lync Server 2013, see [Deploying Persistent Chat Server in Lync Server 2013](lync-server-2013-deploying-persistent-chat-server.md) in the Deployment documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="abd78-118">Содержание</span><span class="sxs-lookup"><span data-stu-id="abd78-118">In This Section</span></span>

  - [<span data-ttu-id="abd78-119">Принцип работы сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abd78-119">How Persistent Chat Server works in Lync Server 2013</span></span>](lync-server-2013-how-persistent-chat-server-works.md)

  - [<span data-ttu-id="abd78-120">Использование категорий для администрирования сервера сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="abd78-120">Using categories to administer Persistent Chat Server</span></span>](using-categories-to-administer-persistent-chat-server.md)

  - [<span data-ttu-id="abd78-121">Общие сведения о членстве в сохраняемом чате</span><span class="sxs-lookup"><span data-stu-id="abd78-121">Understanding Persistent Chat membership</span></span>](understanding-persistent-chat-membership.md)

  - [<span data-ttu-id="abd78-122">Рекомендации по работе с сервером сохраняемого чата</span><span class="sxs-lookup"><span data-stu-id="abd78-122">Persistent Chat Server best practices</span></span>](persistent-chat-server-best-practices.md)

  - [<span data-ttu-id="abd78-123">Управление категориями, комнатами и надстройками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abd78-123">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)

  - [<span data-ttu-id="abd78-124">Управление доступом пользователей сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abd78-124">Managing Persistent Chat user access in Lync Server 2013</span></span>](lync-server-2013-managing-persistent-chat-user-access.md)

  - [<span data-ttu-id="abd78-125">Эксплуатация и обслуживание системы сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="abd78-125">Operating and maintaining the Persistent Chat system in Lync Server 2013</span></span>](lync-server-2013-operating-and-maintaining-the-persistent-chat-system.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

