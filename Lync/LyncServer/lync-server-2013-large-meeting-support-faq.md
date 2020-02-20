---
title: 'Lync Server 2013: вопросы и ответы по поддержке больших собраний'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b00c7d2713bed543dd42812d0d7c31bf75cd1d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a><span data-ttu-id="1a17b-102">Вопросы и ответы по поддержке больших собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1a17b-102">Large meeting support FAQ for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1a17b-103">_**Последнее изменение темы:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1a17b-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1a17b-104">В следующих разделах даются ответы на часто задаваемые вопросы по созданию и осуществлению больших собраний.</span><span class="sxs-lookup"><span data-stu-id="1a17b-104">The following sections provide answers to common questions for creating and running large meetings.</span></span>

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a><span data-ttu-id="1a17b-105">Вопрос. Сколько пользователей могут участвовать в большом собрании?</span><span class="sxs-lookup"><span data-stu-id="1a17b-105">Q: How many users can participate in a large meeting?</span></span>

<span data-ttu-id="1a17b-106">Пользовательская модель Lync Server определяет пределы 250 пользователей в общем пуле или 1000 пользователей в пуле, предназначенном для больших собраний, но эти числа представляют только количество проверенных пользователей и только для определенного набора оборудования, используемого в ходе тестирования.</span><span class="sxs-lookup"><span data-stu-id="1a17b-106">The Lync Server user model specifies limits of 250 users in a shared pool or 1000 users in a pool dedicated to large meetings, but these numbers only represent the number of users we tested and only for the specific set of hardware that we used in our testing.</span></span> <span data-ttu-id="1a17b-107">В зависимости от тестирования мы рекомендуем использовать эти ограничения для максимальных размеров.</span><span class="sxs-lookup"><span data-stu-id="1a17b-107">Based on our testing, we recommend those limits for maximum sizes.</span></span> <span data-ttu-id="1a17b-108">Однако вы можете контролировать фактическое количество участников, разрешенных в собраниях в Организации, настраивая одну или несколько политик конференц-связи (которые вы настраиваете с помощью командлетов Windows PowerShell в командной консоли Lync Server или с помощью Lync Server). Панель управления).</span><span class="sxs-lookup"><span data-stu-id="1a17b-108">However, you control the actual number of participants allowed in meetings in your organization by configuring one or more conferencing policies (which you configure using Windows PowerShell cmdlets in the Lync Server Management Shell or using the Lync Server Control Panel).</span></span> <span data-ttu-id="1a17b-109">Число, заданное в политике конференц-связи, может быть любым 32-битным целым числом от 1 до 4 294 967 295, но рекомендуемый размер — от 2 до 250 участников, включительно; значение по умолчанию — 250.</span><span class="sxs-lookup"><span data-stu-id="1a17b-109">The number that you specify in a conferencing policy can be any 32-bit whole number between 1 and 4,294,967,295, but the recommended size is between 2 and 250 participants, inclusive; and the default value is 250.</span></span>

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a><span data-ttu-id="1a17b-110">Вопрос. Сколько собраний или других рабочих нагрузок можно разместить в пуле, выделенном для больших собраний?</span><span class="sxs-lookup"><span data-stu-id="1a17b-110">Q: How many meetings or other workloads can I have in a pool that is dedicated to large meetings?</span></span>

<span data-ttu-id="1a17b-p102">Чтобы обеспечить оптимальную работу пользователей в процессе проведения больших собраний с числом участников до 1000, мы рекомендуем размещать одновременно только одно большое собрание в выделенном пуле. Мы также рекомендуем не использовать этот пул для выполнения других рабочих нагрузок во время проведения большого собрания.</span><span class="sxs-lookup"><span data-stu-id="1a17b-p102">To ensure the best user experience in large meetings of up to 1000 participants, we recommend hosting only a single large meeting at a time on a pool that is dedicated to large meetings. We also recommend not allowing any other workloads to run on that pool when the large meeting is in progress.</span></span>

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a><span data-ttu-id="1a17b-113">Вопрос. Должны ли организаторы большого собрания размещаться в выделенном пуле?</span><span class="sxs-lookup"><span data-stu-id="1a17b-113">Q: Should the organizers of large meeting be homed on the dedicated pool?</span></span>

<span data-ttu-id="1a17b-p103">Нет. Мы рекомендуем размещать в выделенном пуле только тех сотрудников, которые отвечают за планирование больших собраний. При проведении больших собраний это предотвратит проблемы, вызванные передачей постороннего трафика в режиме реального времени. Для планирования больших собраний в выделенном пуле используйте учетную запись сотрудника, ответственного за планирование больших собраний. Учетную запись организатора собрания (пользователя, запрашивающего проведение большого собрания) следует добавить в список выступающих.</span><span class="sxs-lookup"><span data-stu-id="1a17b-p103">No. We recommend not homing any users other than the dedicated staff that manages scheduling of large meetings on the dedicated pool. This prevents other real-time communications traffic from causing problems with large meetings that are hosted in the pool. You should schedule large meetings on the dedicated pool using a user account of the large meeting scheduling staff. You should add the user account of the meeting organizer (the user who requests a large meeting) as a presenter for the large meeting.</span></span>

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a><span data-ttu-id="1a17b-119">Вопрос. Какие режимы передачи данных можно использовать в рамках большого собрания?</span><span class="sxs-lookup"><span data-stu-id="1a17b-119">Q: What media modalities can I use in a large meeting?</span></span>

<span data-ttu-id="1a17b-120">Большие собрания с числом участников до 1000 могут включать передачу звука, видео, совместное использование презентаций PowerPoint, доски и опрос присутствия.</span><span class="sxs-lookup"><span data-stu-id="1a17b-120">Large meetings with up to 1000 users can include audio, video, PowerPoint sharing, whiteboards, and presence polling.</span></span>

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a><span data-ttu-id="1a17b-121">Вопрос. Можно ли использовать групповые мгновенные сообщения во время больших собраний?</span><span class="sxs-lookup"><span data-stu-id="1a17b-121">Q: Can I use group instant messaging (IM) in large meetings?</span></span>

<span data-ttu-id="1a17b-122">Да.</span><span class="sxs-lookup"><span data-stu-id="1a17b-122">Yes.</span></span> <span data-ttu-id="1a17b-123">Однако отправка множества мгновенных сообщений большим числом участников собрания может повлиять на качество работы пользователей вследствие проблем с прокруткой текста в окне мгновенных сообщений.</span><span class="sxs-lookup"><span data-stu-id="1a17b-123">However, large numbers of instant messages, especially when sent by a large number of meeting participants, can affect the user experience due to problems with fast text scrolling in the IM window.</span></span> <span data-ttu-id="1a17b-124">Доставка большого числа мгновенных сообщений 1000 пользователей может также создавать существенную нагрузку на серверы и снижать производительность.</span><span class="sxs-lookup"><span data-stu-id="1a17b-124">Delivering a large amount of instant messages to up to 1000 users can also introduce significant server loads, which can affect performance.</span></span> <span data-ttu-id="1a17b-125">Как правило, Обмен мгновенными сообщениями необходим только для вопросов\&и ответов (Q как).</span><span class="sxs-lookup"><span data-stu-id="1a17b-125">Generally, IM is only required for questions and answers (Q\&As).</span></span>

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a><span data-ttu-id="1a17b-126">Могут ли пользователи присоединяться к большим собраниям, набирая номер с телефона?</span><span class="sxs-lookup"><span data-stu-id="1a17b-126">Can users join large meetings by dialing in from a phone?</span></span>

<span data-ttu-id="1a17b-127">Да.</span><span class="sxs-lookup"><span data-stu-id="1a17b-127">Yes.</span></span> <span data-ttu-id="1a17b-128">Если пул Lync Server 2013 правильно развернут и включен для конференц-связи с телефонным подключением, пользователи смогут присоединиться к большим собраниям с помощью набора номера.</span><span class="sxs-lookup"><span data-stu-id="1a17b-128">If the Lync Server 2013 pool is properly deployed and enabled for dial-in conferencing, users will be able to join the large meetings by dialing in.</span></span> <span data-ttu-id="1a17b-129">Тестирование показало, что около 15 % из 1000 пользователей могут присоединиться к большому собранию за 10 минут.</span><span class="sxs-lookup"><span data-stu-id="1a17b-129">Our testing has shown that up to 15% of the 1000 users can join the large meeting over a 10 minute period.</span></span>

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a><span data-ttu-id="1a17b-130">Вопрос. Можно ли проводить большие собрания в виртуальной топологии?</span><span class="sxs-lookup"><span data-stu-id="1a17b-130">Q: Can I host large meetings in a virtual topology?</span></span>

<span data-ttu-id="1a17b-131">Мы не тестировали большие собрания в виртуальной топологии, поэтому размещение выделенного пула для больших собраний в виртуальных машинах не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="1a17b-131">We have not tested large meetings in a virtual topology, so we do not support the use of virtual machines to host a dedicated pool for large meetings.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

