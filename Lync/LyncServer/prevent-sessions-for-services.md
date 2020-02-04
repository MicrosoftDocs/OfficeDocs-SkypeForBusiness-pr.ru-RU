---
title: Запрет сеансов для служб
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bf8fb96fef5a01f9b25ca954dd27d1bdfd1f7055
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="prevent-sessions-for-services"></a><span data-ttu-id="1e361-102">Запрет сеансов для служб</span><span class="sxs-lookup"><span data-stu-id="1e361-102">Prevent sessions for services</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e361-103">_**Тема последнего изменения:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="1e361-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="1e361-104">С помощью панели управления Microsoft Lync Server 2010 можно запретить новые сеансы для всех служб Lync Server 2010, запущенных на определенном компьютере, или запретить новые сеансы для конкретной службы Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="1e361-104">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="1e361-105">Запрещение новых сеансов для всех служб Lync Server на компьютере</span><span class="sxs-lookup"><span data-stu-id="1e361-105">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="1e361-106">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e361-106">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="1e361-107">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1e361-107">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="1e361-108">На панели навигации слева щелкните **топология** и выберите **состояние**.</span><span class="sxs-lookup"><span data-stu-id="1e361-108">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="1e361-109">На странице " **состояние** " выполните сортировку или поиск по списку, если это необходимо, чтобы найти компьютер, на котором запущены службы, для которых вы хотите запретить новые сеансы, а затем щелкните его.</span><span class="sxs-lookup"><span data-stu-id="1e361-109">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="1e361-110">Нажмите кнопку **действие**.</span><span class="sxs-lookup"><span data-stu-id="1e361-110">Click **Action**.</span></span>

6.  <span data-ttu-id="1e361-111">Нажмите кнопку **запретить новые сеансы для всех служб**.</span><span class="sxs-lookup"><span data-stu-id="1e361-111">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="1e361-112">Запрещение новых сеансов для конкретной службы</span><span class="sxs-lookup"><span data-stu-id="1e361-112">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="1e361-113">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e361-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="1e361-114">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1e361-114">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="1e361-115">На панели навигации слева щелкните **топология** и выберите **состояние**.</span><span class="sxs-lookup"><span data-stu-id="1e361-115">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="1e361-116">На странице " **состояние** " выполните сортировку и поиск по списку, если это необходимо, чтобы найти компьютер, на котором запущена служба, которую вы хотите запустить или остановить, а затем щелкните ее.</span><span class="sxs-lookup"><span data-stu-id="1e361-116">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="1e361-117">Нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="1e361-117">Click **Properties**.</span></span>

6.  <span data-ttu-id="1e361-118">При необходимости отсортируйте список служб и выберите службу, для которой вы хотите запретить новые сеансы.</span><span class="sxs-lookup"><span data-stu-id="1e361-118">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="1e361-119">Нажмите кнопку **действие**.</span><span class="sxs-lookup"><span data-stu-id="1e361-119">Click **Action**.</span></span>

8.  <span data-ttu-id="1e361-120">Выберите команду **запретить новые сеансы для службы**.</span><span class="sxs-lookup"><span data-stu-id="1e361-120">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="1e361-121">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1e361-121">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

