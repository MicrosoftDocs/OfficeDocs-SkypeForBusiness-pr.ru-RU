---
title: 'Lync Server 2013: управление приостановкой звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Call Park
ms:assetid: 9554cdf6-8e7c-48c8-94dd-f28e2befefdc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688140(v=OCS.15)
ms:contentKeyID: 49733740
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1188f80c5dc8555b53f54e7a13c60f97817eaba2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-call-park-in-lync-server-2013"></a><span data-ttu-id="0c8bb-102">Управление приостановкой звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c8bb-102">Managing Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c8bb-103">_**Тема последнего изменения:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="0c8bb-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="0c8bb-104">Приложение для приема звонков позволяет корпоративному голосовому пользователю перевести звонок на удержание с одного телефона и затем получать Звонок позже с любого телефона.</span><span class="sxs-lookup"><span data-stu-id="0c8bb-104">The Call Park application enables an Enterprise Voice user to put a call on hold from one telephone and then retrieve the call later from any telephone.</span></span> <span data-ttu-id="0c8bb-105">Когда пользователь парки звонок, Lync Server передает Звонок на временный номер, именуемый *орбитой*, где звонок удерживается, пока кто-то не загружает ее или не истечет.</span><span class="sxs-lookup"><span data-stu-id="0c8bb-105">When the user parks a call, Lync Server transfers the call to a temporary number, called an *orbit*, where the call is held until someone retrieves it or it times out.</span></span>

<span data-ttu-id="0c8bb-106">В этой статье приведены пошаговые инструкции для задач, которые можно выполнять для настройки и обслуживания приложения для парковки звонков в развертывании.</span><span class="sxs-lookup"><span data-stu-id="0c8bb-106">Topics in this section provide step-by-step procedures for tasks that you can perform to customize and maintain the Call Park application in your deployment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0c8bb-107">Содержание</span><span class="sxs-lookup"><span data-stu-id="0c8bb-107">In This Section</span></span>

  - [<span data-ttu-id="0c8bb-108">Настройка расширений номеров телефонов для вызовов парковки в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c8bb-108">Configure phone number extensions for parking calls in Lync Server 2013</span></span>](lync-server-2013-configure-phone-number-extensions-for-parking-calls.md)

  - [<span data-ttu-id="0c8bb-109">Настройка параметров парковки звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c8bb-109">Configure Call Park settings in Lync Server 2013</span></span>](lync-server-2013-configure-call-park-settings.md)

  - [<span data-ttu-id="0c8bb-110">Настройка музыкального сопровождения для приема звонков на удержании в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c8bb-110">Customize Call Park music on hold in Lync Server 2013</span></span>](lync-server-2013-customize-call-park-music-on-hold.md)

  - [<span data-ttu-id="0c8bb-111">Управление парковкой вызовов во время аварийного восстановления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c8bb-111">Manage Call Park during disaster recovery in Lync Server 2013</span></span>](lync-server-2013-manage-call-park-during-disaster-recovery.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

