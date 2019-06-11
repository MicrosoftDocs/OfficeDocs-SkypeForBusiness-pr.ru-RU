---
title: 'Lync Server 2013: Планирование функций управления звонками'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for call management features
ms:assetid: 5f557345-5a04-45d6-b274-c02dbfe41b33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398421(v=OCS.15)
ms:contentKeyID: 48184298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c799051615a75801640c63ade6fe6d23b8a62dda
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-call-management-features-in-lync-server-2013"></a><span data-ttu-id="6a1f7-102">Планирование функций управления звонками в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a1f7-102">Planning for call management features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6a1f7-103">_**Тема последнего изменения:** 2012-12-17_</span><span class="sxs-lookup"><span data-stu-id="6a1f7-103">_**Topic Last Modified:** 2012-12-17_</span></span>

<span data-ttu-id="6a1f7-104">Возможности управления голосом на корпоративном звонке определяют маршрутизацию и ответ на входящие звонки.</span><span class="sxs-lookup"><span data-stu-id="6a1f7-104">Enterprise Voice call management features control how incoming calls are routed and answered.</span></span> <span data-ttu-id="6a1f7-105">Lync Server 2013 обеспечивает следующие функции управления звонками:</span><span class="sxs-lookup"><span data-stu-id="6a1f7-105">Lync Server 2013 provides the following call management features:</span></span>

  - <span data-ttu-id="6a1f7-106">**Парковка вызовов**:   предоставляет пользователям голосовой связи возможность временно запарковать вызов, а затем ответить на него с того же или с другого телефона.</span><span class="sxs-lookup"><span data-stu-id="6a1f7-106">**Call Park**:   Enables voice users to temporarily park a call and then pick it up from the same or another phone.</span></span>

  - <span data-ttu-id="6a1f7-107">**Групповой ответ**:   позволяет пользователям голосовой связи отвечать на звонки, которые адресованы другим пользователям, назначенным группам ответа на звонки.</span><span class="sxs-lookup"><span data-stu-id="6a1f7-107">**Group Pickup**:   Enables voice users to pick up calls that are ringing for other voice users who are assigned to call pickup groups.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="6a1f7-108">Отправка групп — это новая платформа с накопительными обновлениями для Lync Server 2013: Февраль 2013.</span><span class="sxs-lookup"><span data-stu-id="6a1f7-108">Group Pickup is new with Cumulative Updates for Lync Server 2013: February 2013.</span></span>

    
    </div>

  - <span data-ttu-id="6a1f7-109">**Группа ответа**:    направляет входящие звонки в группы агентов с помощью сервисных групп или вопросов и ответов интерактивного автоответчика (IVR).</span><span class="sxs-lookup"><span data-stu-id="6a1f7-109">**Response Group**:   Routes incoming calls to groups of agents by using hunt groups or interactive voice response (IVR) questions and answers.</span></span>

  - <span data-ttu-id="6a1f7-110">**Объявление:**    Воспроизводит сообщение для звонков, выполненных на неназначенные номера, или направляет Звонок на другое место.</span><span class="sxs-lookup"><span data-stu-id="6a1f7-110">**Announcement:**    Plays a message for calls made to an unassigned number, or routes the call elsewhere, or both.</span></span>

<span data-ttu-id="6a1f7-111">Если планируется развертывание корпоративной голосовой связи, то можно указать, какие из этих функций управления вызовами следует реализовать.</span><span class="sxs-lookup"><span data-stu-id="6a1f7-111">If you plan to deploy Enterprise Voice, you can choose to implement any or all of these call management features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6a1f7-112">Содержание</span><span class="sxs-lookup"><span data-stu-id="6a1f7-112">In This Section</span></span>

  - [<span data-ttu-id="6a1f7-113">Планирование парковки вызовов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a1f7-113">Planning for Call Park in Lync Server 2013</span></span>](lync-server-2013-planning-for-call-park.md)

  - [<span data-ttu-id="6a1f7-114">Планирование отправки группового звонка в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a1f7-114">Planning for Group Call Pickup in Lync Server 2013</span></span>](lync-server-2013-planning-for-group-call-pickup.md)

  - [<span data-ttu-id="6a1f7-115">Планирование групп ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a1f7-115">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)

  - [<span data-ttu-id="6a1f7-116">Планирование объявлений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6a1f7-116">Planning for announcements in Lync Server 2013</span></span>](lync-server-2013-planning-for-announcements.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

