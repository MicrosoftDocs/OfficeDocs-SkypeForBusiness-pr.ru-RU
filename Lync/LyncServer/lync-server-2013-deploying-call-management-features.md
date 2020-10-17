---
title: 'Lync Server 2013: развертывание функций управления звонками'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying call management features
ms:assetid: 1667cfe4-76fa-4e10-91bb-b3efbedbf759
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204706(v=OCS.15)
ms:contentKeyID: 48183504
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 278bbc82d0952cbc0eda81eb2a85febd16446a8f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48531276"
---
# <a name="deploying-call-management-features-in-lync-server-2013"></a><span data-ttu-id="bfdc6-102">Развертывание функций управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfdc6-102">Deploying call management features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bfdc6-103">_**Последнее изменение темы:** 2012-12-18_</span><span class="sxs-lookup"><span data-stu-id="bfdc6-103">_**Topic Last Modified:** 2012-12-18_</span></span>

<span data-ttu-id="bfdc6-104">Функции управления вызовами в корпоративной голосовой связи управляют тем, каким образом происходит маршрутизация входящих вызовов и ответ на них.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-104">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="bfdc6-105">Lync Server 2013 предоставляет следующие функции управления звонками:</span><span class="sxs-lookup"><span data-stu-id="bfdc6-105">Lync Server 2013 provides the following call management features:</span></span>

  - <span data-ttu-id="bfdc6-106">**Парковки вызовов:** Позволяет голосовым пользователям временно приостановить вызов, а затем выбрать его на том же телефоне или на другом телефоне.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-106">**Call Park:** Enables voice users to temporarily park a call and then pick it up from the same phone or another phone.</span></span>

  - <span data-ttu-id="bfdc6-107">**Подбор групп:** Позволяет пользователям отвечать на вызовы, выполненные для другого пользователя, назначенного группе раскладки, с помощью набора номера группы ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-107">**Group Pickup:** Enables users to answer calls made to another user who is assigned to a pickup group by dialing the call pickup group number.</span></span>

  - <span data-ttu-id="bfdc6-108">**Группа ответа:** Направляет входящие вызовы в группы агентов с помощью сервисных групп или вопросов и ответов интерактивного речевого ответа (IVR).</span><span class="sxs-lookup"><span data-stu-id="bfdc6-108">**Response Group:** Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

  - <span data-ttu-id="bfdc6-109">**Извещение:** Воспроизводит сообщение для вызовов, выполненных с неназначенным номером, или направляет вызов в другое место или обоими способами.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-109">**Announcement:** Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="bfdc6-110">В этом разделе описывается, как настроить эти функции управления вызовами во время развертывания корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="bfdc6-110">This section describes how to configure these call management features during an Enterprise Voice deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bfdc6-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="bfdc6-111">In This Section</span></span>

  - [<span data-ttu-id="bfdc6-112">Настройка парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfdc6-112">Configuring Call Park in Lync Server 2013</span></span>](lync-server-2013-configuring-call-park.md)

  - [<span data-ttu-id="bfdc6-113">Настройка групповой отправки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfdc6-113">Configuring Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-configuring-group-call-pickup.md)

  - [<span data-ttu-id="bfdc6-114">Настройка группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfdc6-114">Configuring Response Group in Lync Server 2013</span></span>](lync-server-2013-configuring-response-group.md)

  - [<span data-ttu-id="bfdc6-115">Настройка объявлений для неназначенных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bfdc6-115">Configuring announcements for unassigned numbers in Lync Server 2013</span></span>](lync-server-2013-configuring-announcements-for-unassigned-numbers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

