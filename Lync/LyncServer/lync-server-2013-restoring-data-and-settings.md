---
title: 'Lync Server 2013: восстановление данных и параметров'
description: 'Lync Server 2013: восстановление данных и параметров.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring data and settings
ms:assetid: b07f5dd7-7bed-4819-8cb5-617f5acd478e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202185(v=OCS.15)
ms:contentKeyID: 51541503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 694b1e362d729d354b08367d31c47e8ca866dd91
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560295"
---
# <a name="restoring-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="5db30-103">Восстановление данных и параметров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5db30-103">Restoring data and settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5db30-104">_**Последнее изменение темы:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="5db30-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="5db30-105">Если вы реализовали топологию аварийного восстановления с подключенными пулами, а один из этих интерфейсных пулов прекратил работу и вам потребуется быстро восстановить службу для пользователей, ознакомьтесь [с разработкой отказа для пула в Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="5db30-105">If you have implemented a disaster recovery topology with paired pools, and one of those Front End pools has gone down and you need to quickly restore service to your users, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="5db30-106">В противном случае используйте сведения, приведенные в следующих разделах, вместе с листами в [таблицах резервного копирования и восстановления для Lync server 2013](lync-server-2013-backup-and-restoration-worksheets.md), чтобы восстановить Lync Server после сбоя или сбоя.</span><span class="sxs-lookup"><span data-stu-id="5db30-106">Otherwise, use the information in the following topics, along with the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md), to restore Lync Server after a failure or outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="5db30-107">Чтобы сократить время простоя и возможной потери данных, выполните процедуры восстановления, описанные в этом документе, только в том случае, если процедуры устранения неполадок неэффективны при определении и исправлении проблемы.</span><span class="sxs-lookup"><span data-stu-id="5db30-107">To reduce downtime and potential data loss, perform the restoration procedures described in this document only if troubleshooting procedures are not effective in identifying and correcting the problem.</span></span> <span data-ttu-id="5db30-108">Во время устранения неполадок попробуйте минимизировать влияние на другие серверы и компоненты при завершении работы и перезапуске серверов.</span><span class="sxs-lookup"><span data-stu-id="5db30-108">During troubleshooting, try to minimize the impact on other servers and components as you shut down and restart servers.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="5db30-109">Содержание</span><span class="sxs-lookup"><span data-stu-id="5db30-109">In This Section</span></span>

  - [<span data-ttu-id="5db30-110">Подготовка к восстановлению Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5db30-110">Preparing to restore Lync Server 2013</span></span>](lync-server-2013-preparing-to-restore-lync-server.md)

  - [<span data-ttu-id="5db30-111">Восстановление сервера Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5db30-111">Restoring a Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-restoring-a-standard-edition-server.md)

  - [<span data-ttu-id="5db30-112">Восстановление сервера, на котором размещается центральное хранилище управления, в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5db30-112">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [<span data-ttu-id="5db30-113">Восстановление внутреннего сервера Enterprise Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5db30-113">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [<span data-ttu-id="5db30-114">Восстановление рядового сервера Enterprise Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5db30-114">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [<span data-ttu-id="5db30-115">Восстановление пула Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5db30-115">Restoring a Lync Server pool in Lync Server 2013</span></span>](lync-server-2013-restoring-a-lync-server-pool.md)

  - [<span data-ttu-id="5db30-116">Выполнение отработки отказа для пула переднего плана ABC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5db30-116">Performing an ABC Front End pool failover in Lync Server 2013</span></span>](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [<span data-ttu-id="5db30-117">Восстановление хранилища файлов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5db30-117">Restoring a file store in Lync Server 2013</span></span>](lync-server-2013-restoring-a-file-store.md)

  - [<span data-ttu-id="5db30-118">Восстановление данных мониторинга или архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5db30-118">Restoring monitoring or archiving data in Lync Server 2013</span></span>](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [<span data-ttu-id="5db30-119">Восстановление данных сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5db30-119">Restoring Persistent Chat data in Lync Server 2013</span></span>](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

