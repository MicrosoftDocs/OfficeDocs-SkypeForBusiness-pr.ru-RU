---
title: 'Lync Server 2013: поддержка больших собраний'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 73c9a5d2ad4688f622298378c84b61574048a3b1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a><span data-ttu-id="b9861-102">Поддержка больших собраний с помощью Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9861-102">Supporting large meetings using Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9861-103">_**Последнее изменение темы:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b9861-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b9861-104">Крупные собрания не соответствуют тестовой модели, описанной в предыдущем разделе, поскольку они обладают следующими характеристиками:</span><span class="sxs-lookup"><span data-stu-id="b9861-104">Large meetings do not follow the test model described in the previous section because they have the following characteristics:</span></span>

  - <span data-ttu-id="b9861-105">формат собрания: презентация один-ко-многим;</span><span class="sxs-lookup"><span data-stu-id="b9861-105">The meeting format is a one-to-many presentation.</span></span>

  - <span data-ttu-id="b9861-106">один или несколько пользователей являются докладчиками, а все остальные являются участниками;</span><span class="sxs-lookup"><span data-stu-id="b9861-106">One or a few users are presenters, and everyone else participates only as attendees.</span></span>

  - <span data-ttu-id="b9861-107">совместное использование презентации PowerPoint — это основное действие для совместной работы с данными;</span><span class="sxs-lookup"><span data-stu-id="b9861-107">PowerPoint presentation sharing is the main data collaboration activity.</span></span>

  - <span data-ttu-id="b9861-108">аудио является обязательным, видео также может использоваться;</span><span class="sxs-lookup"><span data-stu-id="b9861-108">Audio is required and video may also be used.</span></span>

  - <span data-ttu-id="b9861-109">выделенный человек, обычно организатор собрания или помощник организатора, настраивает собрание заблаговременно;</span><span class="sxs-lookup"><span data-stu-id="b9861-109">A dedicated person, generally either the meeting organizer or an assistant to the organizer sets up the meeting well in advance.</span></span>

  - <span data-ttu-id="b9861-110">выделенные сотрудники (не докладчики) руководят собранием, в том числе контролируют подключение к собранию по сети, проверка работы аудио, видео и совместного использования слайдов, управляют залом ожидания и ролями пользователей, отключают и включают звук участников, принимают вопросов и управляют записями, по мере необходимости.</span><span class="sxs-lookup"><span data-stu-id="b9861-110">Dedicated staff (not the presenters) runs the meeting, including connecting to an online meeting, verifying that audio, video, and slide sharing work, managing lobby and user roles, muting and unmuting participants, taking questions, and managing recordings, as appropriate.</span></span>

<span data-ttu-id="b9861-111">Для поддержки крупных собраний с участием до 1000 пользователей необходимо решить вопросы, связанные с моделью общего оборудования и моделью без резервирования.</span><span class="sxs-lookup"><span data-stu-id="b9861-111">Supporting large meetings of up to 1000 users requires addressing the issues related to both the shared hardware model and the no-reservation model.</span></span>

<span data-ttu-id="b9861-112">Чтобы иметь достаточные ресурсы ЦП и памяти для собраний до 1000 пользователей, серверы переднего плана размещения не должны содержать другие рабочие нагрузки для обмена мгновенными сообщениями и присутствия и корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="b9861-112">To have sufficient CPU and memory resources for meetings of up to 1000 users, the hosting Front End Servers should not host any other instant messaging (IM) and presence or Enterprise Voice workloads.</span></span> <span data-ttu-id="b9861-113">На них также не должны размещаться другие собрания независимо от их размера.</span><span class="sxs-lookup"><span data-stu-id="b9861-113">It should also not host any other meetings, regardless of the size of the other meetings.</span></span> <span data-ttu-id="b9861-114">Это означает, что при размещении собраний до 1000 пользователей необходимо настроить отдельный пул Lync Server, предназначенный для хранения больших собраний до 1000 пользователей.</span><span class="sxs-lookup"><span data-stu-id="b9861-114">This means that hosting meetings of up to 1000 users requires setting up a separate Lync Server pool that is dedicated to hosting large meetings of up to 1000 users.</span></span>

<span data-ttu-id="b9861-115">Пул Lync Server, предназначенный для размещения больших собраний, должен размещать одно и только одно собрание до 1000 пользователей одновременно, поэтому время проведения собрания должно быть зарезервировано заранее с помощью фонового процесса планирования, чтобы обеспечить специальную поддержку из интерфейса серв. ЕРС.</span><span class="sxs-lookup"><span data-stu-id="b9861-115">A Lync Server pool that is dedicated to hosting large meetings should host one and only one meeting of up to 1000 users at the same time, so meeting times need to be reserved in advance via an out of band scheduling process to ensure dedicated support from the Front End Servers.</span></span> <span data-ttu-id="b9861-116">Для одновременной поддержки нескольких крупных собраний мы рекомендуем настроить несколько выделенных пулов для крупных собраний.</span><span class="sxs-lookup"><span data-stu-id="b9861-116">To support more than one large meeting at the same time, we recommend setting up multiple dedicated large-meeting pools.</span></span>

<span data-ttu-id="b9861-p103">Рекомендуется, чтобы выделенный специалист выполнял и отслеживал сетевую часть крупного собрания. Этот пользователь может быть организатором, делегатом организатора или докладчика или участником выделенной группы поддержки крупных собраний в зависимости от предпочтений организации.</span><span class="sxs-lookup"><span data-stu-id="b9861-p103">We recommend that a dedicated person run and monitor the online portion of a large meeting. This person might be the organizer, delegate of the organizer or presenter, or a member of the dedicated large meeting support team, depending on the organization’s preferences.</span></span>

<span data-ttu-id="b9861-119">В следующих разделах описывается реализация выделенного пула для больших собраний, в том числе рекомендации по использованию Lync Server 2013 для поддержки больших сценариев собраний.</span><span class="sxs-lookup"><span data-stu-id="b9861-119">In the following sections, we describe how to implement a dedicated pool for large meetings, including best practices for using Lync Server 2013 to support large meeting scenarios.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="b9861-120">Содержание</span><span class="sxs-lookup"><span data-stu-id="b9861-120">In This Section</span></span>

  - [<span data-ttu-id="b9861-121">Настройка поддержки больших собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9861-121">Setting up support for large meetings in Lync Server 2013</span></span>](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [<span data-ttu-id="b9861-122">Управление большим объемом собраний в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b9861-122">Managing large meetings in Lync Server 2013</span></span>](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

