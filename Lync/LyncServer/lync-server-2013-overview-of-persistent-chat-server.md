---
title: 'Lync Server 2013: Обзор сервера сохраняемого чата'
description: 'Lync Server 2013: Обзор сервера сохраняемого чата.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of Persistent Chat Server
ms:assetid: 23f7c886-304d-495a-ae70-3cbb44241acd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425717(v=OCS.15)
ms:contentKeyID: 48183622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbcb396522611aca52bd2093f2fd49f376341356
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577315"
---
# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="b4bab-103">Обзор сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b4bab-103">Overview of Persistent Chat Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b4bab-104">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="b4bab-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="b4bab-105">Lync Server 2013, сервер сохраняемого чата позволяет пользователям участвовать в многосторонних беседах на основе темы, которые сохраняются со временем.</span><span class="sxs-lookup"><span data-stu-id="b4bab-105">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="b4bab-106">Сервер сохраняемого чата поможет вашей организации выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b4bab-106">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="b4bab-107">Совершенствование обмена данными между участниками географически распределенных многофункциональных рабочих групп.</span><span class="sxs-lookup"><span data-stu-id="b4bab-107">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="b4bab-108">С помощью сохраняемого чата Teams может эффективно обмениваться информацией, идеями и решениями друг с другом.</span><span class="sxs-lookup"><span data-stu-id="b4bab-108">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="b4bab-109">Сообщения, опубликованные в комнатах чата (на форумах) могут сохраняться (то есть оставаться доступными по прошествии времени), что позволяет участвовать в беседах людям, работающим в разных отделах и находящимся в разных местах, даже если они не выходят в сеть одновременно.</span><span class="sxs-lookup"><span data-stu-id="b4bab-109">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="b4bab-110">Когда пользователь подключается к комнате чата, автоматически загружается определенное количество сообщений из истории чата, чтобы помочь пользователю включиться в беседу.</span><span class="sxs-lookup"><span data-stu-id="b4bab-110">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="b4bab-111">Усовершенствованное информирование.</span><span class="sxs-lookup"><span data-stu-id="b4bab-111">Improve information awareness.</span></span> <span data-ttu-id="b4bab-112">С помощью клиентских фильтров пользователи могут определять условия, например ключевые слова в содержимом сообщения, или значение поля "от" в сообщении — для получения уведомлений при выполнении этих условий в мгновенных сообщениях или сообщениях комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="b4bab-112">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="b4bab-113">Таким образом пользователи могут своевременно получать актуальное интересующее их содержимое.</span><span class="sxs-lookup"><span data-stu-id="b4bab-113">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="b4bab-114">Совершенствование обмена данными в рамках расширенной организации.</span><span class="sxs-lookup"><span data-stu-id="b4bab-114">Improve communication with their extended organization.</span></span> <span data-ttu-id="b4bab-115">Благодаря упрощению совместной работы над длинными разделами в Организации и предоставлением надежного места для обмена данными, сохраняемый чат помогает увеличить связь.</span><span class="sxs-lookup"><span data-stu-id="b4bab-115">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="b4bab-p105">Сокращение перегруженности информацией. Пользователи могут следить за интересующими их комнатами чата и сообщениями с помощью клиентских фильтров и добавлять в список контактов нужные комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="b4bab-p105">Reduce information overload. Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="b4bab-p106">Упрощает распространение важных знаний и информации. В беседы можно включать документы и ссылки, делая их доступными для всех членов рабочей группы. Публикуя вопросы, пользователи могут получить ответы от специалистов в соответствующей области. Интеграция с другими информационными системами позволяет легко доносить важные данные до больших групп пользователей.</span><span class="sxs-lookup"><span data-stu-id="b4bab-p106">Increase dispersion of important knowledge and information. Documents and links can be included within conversations for access by all the team. By posting questions to a broader team, users can benefit from responses by subject matter experts. Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="b4bab-122">Чтобы включить комнаты чата в Lync Server 2013, разверните сохраняемый чат Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b4bab-122">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="b4bab-123">Сведения о том, как включать комнаты чата, можно найти в справке по постоянному чат <https://go.microsoft.com/fwlink/p/?linkid=270945> .</span><span class="sxs-lookup"><span data-stu-id="b4bab-123">For information about enabling chat rooms, see the Persistent Chat Help at <https://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="b4bab-124">Если пользователям разрешено использовать Lync Server, а поддержка Lync Server развернута, пользователи могут установить и использовать Lync 2013 сохраняемый чат, чтобы обеспечить поддержку комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="b4bab-124">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="b4bab-125">Если в Организации требуется соблюдение нормативных требований, при необходимости можно развернуть службу соответствия сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="b4bab-125">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

