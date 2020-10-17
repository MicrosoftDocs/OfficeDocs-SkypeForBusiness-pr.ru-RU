---
title: Остановка служб Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Stop Lync Server 2010 services
ms:assetid: bbb29565-819c-4f6f-a222-22494e56e91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721863(v=OCS.15)
ms:contentKeyID: 49733796
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9a7282bafa8a286a7aff2d1daaa07bb9c9d61238
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532786"
---
# <a name="stop-lync-server-2010-services"></a><span data-ttu-id="4271b-102">Остановка служб Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="4271b-102">Stop Lync Server 2010 services</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4271b-103">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="4271b-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="4271b-104">Можно использовать панель управления Lync Server для запуска или остановки всех служб Lync Server 2010, работающих на определенном компьютере или для запуска или остановки определенной службы Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="4271b-104">You can use Lync Server Control Panel to start or stop all the Lync Server 2010 services running on a specific computer or to start or stop a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-start-or-stop-all-lync-server-services-on-a-computer"></a><span data-ttu-id="4271b-105">Запуск или остановка всех служб Lync Server на компьютере</span><span class="sxs-lookup"><span data-stu-id="4271b-105">To start or stop all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="4271b-106">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4271b-106">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="4271b-107">В левой панели навигации щелкните элемент **Topology** (Топология), а затем **Status** (Состояние).</span><span class="sxs-lookup"><span data-stu-id="4271b-107">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

3.  <span data-ttu-id="4271b-108">На странице **Status** (Состояние) отсортируйте список или выполните по нему поиск, чтобы найти компьютер с требуемыми службами, а затем щелкните его.</span><span class="sxs-lookup"><span data-stu-id="4271b-108">On the **Status** page, sort or search through the list as needed to find the computer that is running the services you want to start or stop, and then click it.</span></span>

4.  <span data-ttu-id="4271b-109">Щелкните элемент **Action** (Действие).</span><span class="sxs-lookup"><span data-stu-id="4271b-109">Click **Action**.</span></span>

5.  <span data-ttu-id="4271b-110">Щелкните **Start All services** (Запустить все службы) или **Stop All services** (Остановить все службы).</span><span class="sxs-lookup"><span data-stu-id="4271b-110">Click **Start All services** or **Stop All services**.</span></span>

</div>

<div>

## <a name="to-start-or-stop-a-specific-service"></a><span data-ttu-id="4271b-111">Запуск или остановка конкретной службы</span><span class="sxs-lookup"><span data-stu-id="4271b-111">To start or stop a specific service</span></span>

1.  <span data-ttu-id="4271b-112">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4271b-112">Open Lync Server Control Panel.</span></span>

2.  <span data-ttu-id="4271b-113">В левой панели навигации щелкните элемент **Topology** (Топология), а затем **Status** (Состояние).</span><span class="sxs-lookup"><span data-stu-id="4271b-113">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

3.  <span data-ttu-id="4271b-114">На странице **Status** (Состояние) отсортируйте список или выполните по нему поиск, чтобы найти компьютер с требуемыми службами, а затем щелкните его.</span><span class="sxs-lookup"><span data-stu-id="4271b-114">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

4.  <span data-ttu-id="4271b-115">Щелкните элемент **Properties** (Свойства).</span><span class="sxs-lookup"><span data-stu-id="4271b-115">Click **Properties**.</span></span>

5.  <span data-ttu-id="4271b-116">Отсортируйте список служб, если это необходимо, и щелкните службу, которую хотите запустить или остановить.</span><span class="sxs-lookup"><span data-stu-id="4271b-116">Sort the list of services, if necessary, and click the service you want to start or stop.</span></span>

6.  <span data-ttu-id="4271b-117">Щелкните элемент **Action** (Действие).</span><span class="sxs-lookup"><span data-stu-id="4271b-117">Click **Action**.</span></span>

7.  <span data-ttu-id="4271b-118">Щелкните **Start service** (Запустить службу) или **Stop service** (Остановить службу).</span><span class="sxs-lookup"><span data-stu-id="4271b-118">Click **Start service** or **Stop service**.</span></span>

8.  <span data-ttu-id="4271b-119">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="4271b-119">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

