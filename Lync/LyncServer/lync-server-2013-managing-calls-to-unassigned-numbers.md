---
title: 'Lync Server 2013: Управление звонками на неназначенные номера'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing calls to unassigned numbers
ms:assetid: a45a7546-5ee6-4c1e-ab13-20a71a058f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688167(v=OCS.15)
ms:contentKeyID: 49733772
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50a6c7fe05729f705bd7ea752658f7c890188159
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-calls-to-unassigned-numbers-in-lync-server-2013"></a><span data-ttu-id="140a1-102">Управление звонками на неназначенные номера в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="140a1-102">Managing calls to unassigned numbers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="140a1-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="140a1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="140a1-104">Lync Server позволяет настраивать обработку входящих звонков, когда номер набора номера действителен для вашей организации, но не назначен пользователю или телефону.</span><span class="sxs-lookup"><span data-stu-id="140a1-104">Lync Server lets you configure the handling of incoming phone calls when the dialed number is valid for your organization, but is not assigned to a user or phone.</span></span> <span data-ttu-id="140a1-105">Вы можете использовать приложение извещения для передачи этих звонков на предварительно определенный адрес назначения (номер телефона, URI SIP или голосовую почту), а также воспроизводить звуковое извещение или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="140a1-105">You can use the Announcement application to transfer these calls to a predetermined destination (phone number, SIP URI, or voice mail), or play an audio announcement, or both.</span></span> <span data-ttu-id="140a1-106">Вы также можете передать эти звонки на номер телефона автосекретаря для Exchange UM.</span><span class="sxs-lookup"><span data-stu-id="140a1-106">You can also transfer these calls to an Exchange UM Auto Attendant phone number.</span></span> <span data-ttu-id="140a1-107">Обработка вызовов неназначенных номеров одним из этих способов поможет избежать ситуаций, в которых вызывающий абонент не набирает номер, а затем слышит сигнал "занято", а клиент SIP получает сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="140a1-107">Handling calls to unassigned numbers in one of these ways helps you avoid the situations in which a caller misdials and then hears a busy tone, or the SIP client receives an error message.</span></span>

<span data-ttu-id="140a1-108">В этом разделе объясняется, как управлять неназначенными диапазонами номеров для обработки звонков на неназначенные телефонные номера.</span><span class="sxs-lookup"><span data-stu-id="140a1-108">This section describes how to manage unassigned number ranges to handle calls to unassigned phone numbers.</span></span> <span data-ttu-id="140a1-109">Кроме того, в разделе описано, как управлять извещениями во время аварийного восстановления, если вы хотите использовать эту функцию во время отключения.</span><span class="sxs-lookup"><span data-stu-id="140a1-109">The section also describes how to manage Announcements during disaster recovery if you want this functionality during an outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="140a1-110">Необязательное использование неназначенной обработки номера во время отключения.</span><span class="sxs-lookup"><span data-stu-id="140a1-110">Using unassigned number handling during an outage is optional.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="140a1-111">Содержание</span><span class="sxs-lookup"><span data-stu-id="140a1-111">In This Section</span></span>

  - [<span data-ttu-id="140a1-112">Создание объявления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="140a1-112">Create an announcement in Lync Server 2013</span></span>](lync-server-2013-create-an-announcement.md)

  - [<span data-ttu-id="140a1-113">Настройка неназначенных номеров телефонов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="140a1-113">Configure unassigned phone numbers in Lync Server 2013</span></span>](lync-server-2013-configure-unassigned-phone-numbers.md)

  - [<span data-ttu-id="140a1-114">Управление оповещениями во время аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="140a1-114">Manage announcements during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-announcements-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

