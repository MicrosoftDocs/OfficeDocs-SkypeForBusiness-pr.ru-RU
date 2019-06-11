---
title: 'Lync Server 2013: восстановление данных и параметров'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring data and settings
ms:assetid: b07f5dd7-7bed-4819-8cb5-617f5acd478e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202185(v=OCS.15)
ms:contentKeyID: 51541503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7562e0899a5129832ef4651c041b8c7daf545e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822393"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="04e28-102">Восстановление данных и параметров в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04e28-102">Restoring data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="04e28-103">_**Тема последнего изменения:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="04e28-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="04e28-104">Если вы реализовали топологию аварийного восстановления с объединенными пулами, а один из этих пулов переднего плана отключился и вам нужно быстро восстановить службу для пользователей, ознакомьтесь [с разработкой отказа в пуле в Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="04e28-104">If you have implemented a disaster recovery topology with paired pools, and one of those Front End pools has gone down and you need to quickly restore service to your users, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="04e28-105">В противном случае используйте сведения из указанных ниже разделов, а также листы резервного [копирования и восстановления для Lync server 2013](lync-server-2013-backup-and-restoration-worksheets.md)для восстановления сервера Lync после сбоя или сбоя.</span><span class="sxs-lookup"><span data-stu-id="04e28-105">Otherwise, use the information in the following topics, along with the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md), to restore Lync Server after a failure or outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="04e28-106">Чтобы сократить время бездействия и возможной потери данных, выполните процедуры восстановления, описанные в этом документе, только в том случае, если процедуры устранения неполадок не дают результатов для выявления и устранения проблемы.</span><span class="sxs-lookup"><span data-stu-id="04e28-106">To reduce downtime and potential data loss, perform the restoration procedures described in this document only if troubleshooting procedures are not effective in identifying and correcting the problem.</span></span> <span data-ttu-id="04e28-107">Во время устранения неполадок попробуйте минимизировать влияние на другие серверы и компоненты при завершении работы и перезапуске серверов.</span><span class="sxs-lookup"><span data-stu-id="04e28-107">During troubleshooting, try to minimize the impact on other servers and components as you shut down and restart servers.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="04e28-108">Содержание</span><span class="sxs-lookup"><span data-stu-id="04e28-108">In This Section</span></span>

  - [<span data-ttu-id="04e28-109">Подготовка к восстановлению Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04e28-109">Preparing to restore Lync Server 2013</span></span>](lync-server-2013-preparing-to-restore-lync-server.md)

  - [<span data-ttu-id="04e28-110">Восстановление сервера Standard Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04e28-110">Restoring a Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-restoring-a-standard-edition-server.md)

  - [<span data-ttu-id="04e28-111">Восстановление сервера, на котором размещается центральное хранилище для управления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04e28-111">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [<span data-ttu-id="04e28-112">Восстановление сервера выпуска Enterprise Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04e28-112">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [<span data-ttu-id="04e28-113">Восстановление сервера участника Enterprise Edition в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04e28-113">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [<span data-ttu-id="04e28-114">Восстановление пула сервера Lync Server в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04e28-114">Restoring a Lync Server pool in Lync Server 2013</span></span>](lync-server-2013-restoring-a-lync-server-pool.md)

  - [<span data-ttu-id="04e28-115">Выполнение отработки отказа в пуле переднего плана для электронной стороны в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04e28-115">Performing an ABC Front End pool failover in Lync Server 2013</span></span>](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [<span data-ttu-id="04e28-116">Восстановление хранилища файлов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04e28-116">Restoring a file store in Lync Server 2013</span></span>](lync-server-2013-restoring-a-file-store.md)

  - [<span data-ttu-id="04e28-117">Восстановление данных мониторинга или архивации в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04e28-117">Restoring monitoring or archiving data in Lync Server 2013</span></span>](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [<span data-ttu-id="04e28-118">Восстановление данных из сохраняемого чата в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="04e28-118">Restoring Persistent Chat data in Lync Server 2013</span></span>](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

