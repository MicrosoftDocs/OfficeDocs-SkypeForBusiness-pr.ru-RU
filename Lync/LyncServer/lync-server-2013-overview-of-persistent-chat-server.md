---
title: 'Lync Server 2013: обзор сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of Persistent Chat Server
ms:assetid: 23f7c886-304d-495a-ae70-3cbb44241acd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425717(v=OCS.15)
ms:contentKeyID: 48183622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a744f4eb251bbbacc8b1b5f4c2a5978a9689f225
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825333"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="d9813-102">Обзор сервера сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d9813-102">Overview of Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d9813-103">_**Тема последнего изменения:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="d9813-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="d9813-104">Lync Server 2013, сервер сохраняемого чата позволяет пользователям принимать участие в многокомпонентных беседах, которые сохраняются с течением времени.</span><span class="sxs-lookup"><span data-stu-id="d9813-104">Lync Server 2013, Persistent Chat Server enables users to participate in multiparty, topic-based conversations that persist over time.</span></span> <span data-ttu-id="d9813-105">Сервер сохраняемого чата может помочь вашей организации выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d9813-105">Persistent Chat Server can help your organization do the following:</span></span>

  - <span data-ttu-id="d9813-106">Улучшите связь между географически распределенными и функциональными группами.</span><span class="sxs-lookup"><span data-stu-id="d9813-106">Improve communication between geographically dispersed and cross-functional teams.</span></span> <span data-ttu-id="d9813-107">С помощью сохраняемого чата команды могут эффективно обмениваться информацией, идеями и решениями друг с другом.</span><span class="sxs-lookup"><span data-stu-id="d9813-107">By using Persistent Chat, teams can efficiently share information, ideas, and decisions with one another.</span></span> <span data-ttu-id="d9813-108">Сообщения, опубликованные в помещениях чата (дискуссионные форумы), могут оставаться на связи (они могут быть доступны во времени), чтобы люди из разных расположений и отделов могли участвовать в работе, даже если они не подключены к Интернету одновременно.</span><span class="sxs-lookup"><span data-stu-id="d9813-108">The messages posted to chat rooms (discussion forums) can persist (that is, can be available over time), so that people from different locations and departments can participate, even when they are not simultaneously online.</span></span> <span data-ttu-id="d9813-109">Когда пользователь подключается к комнате чата, в комнате чата автоматически загружается запись в чате (настроенное количество сообщений), чтобы предоставить пользователю контекст для беседы.</span><span class="sxs-lookup"><span data-stu-id="d9813-109">When a user connects to a chat room, backchat (a configurable number of chat-history messages) is automatically loaded in the chat room to give the user a context for the conversation.</span></span>

  - <span data-ttu-id="d9813-110">Улучшена поддержка информации.</span><span class="sxs-lookup"><span data-stu-id="d9813-110">Improve information awareness.</span></span> <span data-ttu-id="d9813-111">Используя клиентские фильтры, пользователи могут определять условия (например, ключевые слова в содержимом сообщения) или значение поля "от" в сообщении, чтобы получать уведомления о том, что эти условия выполняются в сохраненных мгновенных сообщениях чата или в сообщениях комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="d9813-111">By using client-side filters, users can define conditions—such as keywords in message content, or the value of the "from" field in a message—to receive notification when those conditions are met in Persistent Chat instant messages or chat room messages.</span></span> <span data-ttu-id="d9813-112">Таким образом, пользователи могут оставаться на связи с содержимым, которое их больше всего интересует.</span><span class="sxs-lookup"><span data-stu-id="d9813-112">This way, users can stay up-to-date with the content that interests them most.</span></span>

  - <span data-ttu-id="d9813-113">Улучшите общение с помощью расширенной организации.</span><span class="sxs-lookup"><span data-stu-id="d9813-113">Improve communication with their extended organization.</span></span> <span data-ttu-id="d9813-114">Благодаря простоте совместной работы над долго запущенными разделами с другими пользователями в Организации и предоставлением постоянного места для обмена информацией с помощью сохраняемого чата вы можете улучшить общение.</span><span class="sxs-lookup"><span data-stu-id="d9813-114">By making it easy to collaborate over long-running topics with others in the organization, and by providing a persistent place to share information, Persistent Chat helps improve communication.</span></span>

  - <span data-ttu-id="d9813-115">Уменьшить перегрузку данных.</span><span class="sxs-lookup"><span data-stu-id="d9813-115">Reduce information overload.</span></span> <span data-ttu-id="d9813-116">Пользователи могут подписаться на комнаты чата и сообщения наиболее интересны с помощью клиентских фильтров, а также добавлять комнаты чатов, на которые они хотят подписаться, в список контактов.</span><span class="sxs-lookup"><span data-stu-id="d9813-116">Users can follow chat rooms and messages of most interest by using client-side filters, and can add chat rooms they want to follow to their contact list.</span></span>

  - <span data-ttu-id="d9813-117">Повышайте разброса важных знаний и информации.</span><span class="sxs-lookup"><span data-stu-id="d9813-117">Increase dispersion of important knowledge and information.</span></span> <span data-ttu-id="d9813-118">Документы и ссылки могут быть включены в беседы для доступа всех участников группы.</span><span class="sxs-lookup"><span data-stu-id="d9813-118">Documents and links can be included within conversations for access by all the team.</span></span> <span data-ttu-id="d9813-119">Замещая вопросы в группу более широкой тематики, пользователи могут получить от них ответы, полученные от экспертов.</span><span class="sxs-lookup"><span data-stu-id="d9813-119">By posting questions to a broader team, users can benefit from responses by subject matter experts.</span></span> <span data-ttu-id="d9813-120">Интеграция с другими информационными системами обеспечивает простое взаимодействие важных организационных данных с большим количеством групп.</span><span class="sxs-lookup"><span data-stu-id="d9813-120">Integration with other information systems enables important organizational data to be easily communicated to large groups.</span></span>

<span data-ttu-id="d9813-121">Чтобы включить комнаты чата в Lync Server 2013, разверните сохраняемый чат для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d9813-121">To enable chat rooms in Lync Server 2013, deploy Lync Server 2013 Persistent Chat.</span></span> <span data-ttu-id="d9813-122">Сведения о том, как включить комнаты чата, можно найти в <http://go.microsoft.com/fwlink/p/?linkid=270945>справке по сохранению чата.</span><span class="sxs-lookup"><span data-stu-id="d9813-122">For information about enabling chat rooms, see the Persistent Chat Help at <http://go.microsoft.com/fwlink/p/?linkid=270945>.</span></span> <span data-ttu-id="d9813-123">Если пользователям разрешено использование Lync Server, а поддержка Lync Server развернута, пользователи смогут установить и использовать в Lync 2013 сохраняемый чат, чтобы обеспечить поддержку комнаты чата.</span><span class="sxs-lookup"><span data-stu-id="d9813-123">If users are enabled for Lync Server, and Lync Server support is deployed, users can install and use Lync 2013 Persistent Chat to provide chat room support.</span></span>

<span data-ttu-id="d9813-124">Если Организация обязана подписаться на соответствие нормативным требованиям, вы можете дополнительно развернуть службу соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d9813-124">If your organization is required to follow compliance regulations, you can optionally deploy Persistent Chat Compliance service.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

