---
title: 'Lync Server 2013: управление вызовами неназначенных номеров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing calls to unassigned numbers
ms:assetid: a45a7546-5ee6-4c1e-ab13-20a71a058f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688167(v=OCS.15)
ms:contentKeyID: 49733772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14229f4550773c8b75460cca544da2298129f518
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140192"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="c5861-102">Управление вызовами неназначенных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5861-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5861-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="c5861-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="c5861-104">Lync Server позволяет настроить обработку входящих телефонных звонков, если набранный номер действителен для вашей организации, но не назначен пользователю или телефону.</span><span class="sxs-lookup"><span data-stu-id="c5861-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="c5861-105">Приложение извещения можно использовать для передачи этих вызовов в предварительно определенный адрес назначения (номер телефона, URI SIP или голосовую почту), а также для воспроизведения звукового оповещения или и того, и другое.</span><span class="sxs-lookup"><span data-stu-id="c5861-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="c5861-106">Вы также можете переключать звонки на номер телефона, назначенный автосекретарю единой системы обмена сообщениями Exchange.</span><span class="sxs-lookup"><span data-stu-id="c5861-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="c5861-107">Обработка звонков на неназначенные номера — это один из способов избежать ситуаций, когда звонящий набирает неправильный номер и слышит сигнал "занято" или клиент SIP получает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="c5861-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="c5861-p102">В этом разделе описывается, как управлять диапазонами неназначенных номеров для обработки звонков на незначенные номера телефонов. В нем также описывается, как управлять оповещениями в процессе аварийного восстановления, если необходимо, чтобы эта функция работала во время простоя.</span><span class="sxs-lookup"><span data-stu-id="c5861-p102">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers. The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c5861-110">Использование обработки звонков на незначенные номера во время простоя является необязательным.</span><span class="sxs-lookup"><span data-stu-id="c5861-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c5861-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="c5861-111">In This Section</span></span>

  - [<span data-ttu-id="c5861-112">Создание извещения в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5861-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="c5861-113">Настройка неназначенных телефонных номеров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5861-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="c5861-114">Управление объявлениями во время аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c5861-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

