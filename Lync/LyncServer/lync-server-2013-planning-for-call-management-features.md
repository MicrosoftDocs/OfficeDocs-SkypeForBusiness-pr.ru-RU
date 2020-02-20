---
title: 'Lync Server 2013: Планирование функций управления звонками'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for call management features
ms:assetid: 5f557345-5a04-45d6-b274-c02dbfe41b33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398421(v=OCS.15)
ms:contentKeyID: 48184298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e02b983352aa22e49751aaa65423d05f43415b8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-call-management-features-in-lync-server-2013"></a><span data-ttu-id="d322a-102">Планирование функций управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d322a-102">Planning for call management features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d322a-103">_**Последнее изменение темы:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="d322a-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="d322a-104">Функции управления вызовами в корпоративной голосовой связи управляют тем, каким образом происходит маршрутизация входящих вызовов и ответ на них.</span><span class="sxs-lookup"><span data-stu-id="d322a-104">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="d322a-105">Lync Server 2013 предоставляет следующие функции управления звонками:</span><span class="sxs-lookup"><span data-stu-id="d322a-105">Lync Server 2013 provides the following call management features:</span></span>

  - <span data-ttu-id="d322a-106">**Приложение "Парковка вызовов"**:   предоставляет пользователям голосовой связи возможность временно запарковать вызов, а затем ответить на него с того же или с другого телефона.</span><span class="sxs-lookup"><span data-stu-id="d322a-106">**Call Park**:   Enables voice users to temporarily park a call and then pick it up from the same or another phone.</span></span>

  - <span data-ttu-id="d322a-107">**Подбор групп**: позволяет пользователям голосовых вызовов получать звонки, которые обзвонают для других пользователей голосовой связи, назначенных группам ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="d322a-107">**Group Pickup**:   Enables voice users to pick up calls that are ringing for other voice users who are assigned to call pickup groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d322a-108">Подбор групп — это новая поддержка накопительных обновлений для Lync Server 2013:2013 февраля.</span><span class="sxs-lookup"><span data-stu-id="d322a-108">Group Pickup is new with Cumulative Updates for Lync Server 2013: February 2013.</span></span>

    
    </div>

  - <span data-ttu-id="d322a-109">**Группа ответа**: направляет входящие вызовы в группы агентов с помощью сервисных групп или вопросов и ответов интерактивного речевого ответа (IVR).</span><span class="sxs-lookup"><span data-stu-id="d322a-109">**Response Group**:   Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

  - <span data-ttu-id="d322a-110">**Извещение:**    воспроизводит сообщение для вызовов, выполненных с неназначенным номером, или направляет вызов в другое место или обоими способами.</span><span class="sxs-lookup"><span data-stu-id="d322a-110">**Announcement:**    Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="d322a-111">Если планируется развертывание корпоративной голосовой связи, то можно указать, какие из этих функций управления вызовами следует реализовать.</span><span class="sxs-lookup"><span data-stu-id="d322a-111">If you plan to deploy Enterprise Voice, you can choose to implement any or all of these call management features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d322a-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="d322a-112">In This Section</span></span>

  - [<span data-ttu-id="d322a-113">Планирование парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d322a-113">Planning for Call Park in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-park.md)

  - [<span data-ttu-id="d322a-114">Планирование групповой отправки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d322a-114">Planning for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-planning-for-group-call-pickup.md)

  - [<span data-ttu-id="d322a-115">Планирование групп ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d322a-115">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)

  - [<span data-ttu-id="d322a-116">Планирование объявлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d322a-116">Planning for announcements in Lync Server 2013</span></span>](lync-server-2013-planning-for-announcements.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

