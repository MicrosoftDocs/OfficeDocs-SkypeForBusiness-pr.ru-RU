---
title: Запрет сеансов для служб
description: Предотвращение сеансов для служб.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Prevent sessions for services
ms:assetid: 4b541c72-cdc1-4f86-a5a8-c43c24f41d8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688049(v=OCS.15)
ms:contentKeyID: 49733642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a452f8091716daa0a15967e2a278e82c5bc8c4f3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48563695"
---
# <a name="prevent-sessions-for-services"></a><span data-ttu-id="bbb82-103">Запрет сеансов для служб</span><span class="sxs-lookup"><span data-stu-id="bbb82-103">Prevent sessions for services</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bbb82-104">_**Последнее изменение темы:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="bbb82-104">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="bbb82-105">Вы можете использовать панель управления Microsoft Lync Server 2010, чтобы запретить новые сеансы для всех служб Lync Server 2010, работающих на определенном компьютере, или запретить новые сеансы для конкретной службы Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="bbb82-105">You can use Microsoft Lync Server 2010 Control Panel to prevent new sessions for all the Lync Server 2010 services running on a specific computer or to prevent new sessions for a specific Lync Server 2010 service.</span></span>

<div>

## <a name="to-prevent-new-sessions-for-all-lync-server-services-on-a-computer"></a><span data-ttu-id="bbb82-106">Запрет новых сеансов для всех служб Lync Server на компьютере</span><span class="sxs-lookup"><span data-stu-id="bbb82-106">To prevent new sessions for all Lync Server services on a computer</span></span>

1.  <span data-ttu-id="bbb82-107">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bbb82-107">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="bbb82-108">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bbb82-108">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="bbb82-109">В левой панели навигации щелкните **Топология**, а затем щелкните **Состояние**.</span><span class="sxs-lookup"><span data-stu-id="bbb82-109">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="bbb82-110">На странице **Состояние** выполните сортировку или поиск по списку, чтобы найти компьютер, на котором выполняются службы, для которых нужно запретить новые сеансы, а затем щелкните ее.</span><span class="sxs-lookup"><span data-stu-id="bbb82-110">On the **Status** page, sort or search through the list as needed to find the computer that is running the services for which you want to prevent new sessions, and then click it.</span></span>

5.  <span data-ttu-id="bbb82-111">Щелкните **Действие**.</span><span class="sxs-lookup"><span data-stu-id="bbb82-111">Click **Action**.</span></span>

6.  <span data-ttu-id="bbb82-112">Щелкните **Запретить новые сеансы для всех служб**.</span><span class="sxs-lookup"><span data-stu-id="bbb82-112">Click **Prevent new sessions for all services**.</span></span>

</div>

<div>

## <a name="to-prevent-new-sessions-for-a-specific-service"></a><span data-ttu-id="bbb82-113">Запрет новых сеансов для определенной службы</span><span class="sxs-lookup"><span data-stu-id="bbb82-113">To prevent new sessions for a specific service</span></span>

1.  <span data-ttu-id="bbb82-114">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bbb82-114">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="bbb82-115">Откройте Панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bbb82-115">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="bbb82-116">В левой панели навигации щелкните элемент **Topology** (Топология), а затем **Status** (Состояние).</span><span class="sxs-lookup"><span data-stu-id="bbb82-116">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="bbb82-117">На странице **Status** (Состояние) отсортируйте список или выполните по нему поиск, чтобы найти компьютер с требуемыми службами, а затем щелкните его.</span><span class="sxs-lookup"><span data-stu-id="bbb82-117">On the **Status** page, sort or search through the list as needed to find the computer that is running the service you want to start or stop, and then click it.</span></span>

5.  <span data-ttu-id="bbb82-118">Нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="bbb82-118">Click **Properties**.</span></span>

6.  <span data-ttu-id="bbb82-119">Отсортируйте список служб, если это необходимо, и щелкните службу, для которой вы хотите запретить новые сеансы.</span><span class="sxs-lookup"><span data-stu-id="bbb82-119">Sort the list of services, if necessary, and click the service for which you want to prevent new sessions.</span></span>

7.  <span data-ttu-id="bbb82-120">Щелкните **Действие**.</span><span class="sxs-lookup"><span data-stu-id="bbb82-120">Click **Action**.</span></span>

8.  <span data-ttu-id="bbb82-121">Щелкните **Запретить новые сеансы для службы**.</span><span class="sxs-lookup"><span data-stu-id="bbb82-121">Click **Prevent new sessions for service**.</span></span>

9.  <span data-ttu-id="bbb82-122">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="bbb82-122">Click **Close**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

