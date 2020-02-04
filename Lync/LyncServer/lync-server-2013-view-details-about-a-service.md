---
title: 'Lync Server 2013: Просмотр сведений о службе'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View details about a service
ms:assetid: bc8e8202-cd68-47e4-95b2-bb36e51cc124
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182578(v=OCS.15)
ms:contentKeyID: 48185253
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bc8f0f9f6e0296f279cb09495a92fd9950625e6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-details-about-a-service-in-lync-server-2013"></a><span data-ttu-id="6f412-102">Просмотр подробных сведений о службе в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f412-102">View details about a service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6f412-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="6f412-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="6f412-104">С помощью панели управления Lync Server можно просматривать сведения о каждой службе, работающей на определенном компьютере в вашей топологии.</span><span class="sxs-lookup"><span data-stu-id="6f412-104">You can use Lync Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="6f412-105">Вы можете просматривать состояние каждой службы и такие сведения, как связанные базы данных, порты и зависимые службы.</span><span class="sxs-lookup"><span data-stu-id="6f412-105">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>

<div>

## <a name="to-view-details-for-a-service"></a><span data-ttu-id="6f412-106">Просмотр подробных сведений о службе</span><span class="sxs-lookup"><span data-stu-id="6f412-106">To view details for a service</span></span>

1.  <span data-ttu-id="6f412-107">Из учетной записи пользователя, назначенной какой-либо из предопределенных административных ролей для Lync Server 2013, войдите на любой компьютер во внутренней среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="6f412-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="6f412-108">Подробные сведения о стандартных ролях администратора, доступных в Lync Server 2013, можно найти [в разделе Планирование управления доступом на основе ролей в Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="6f412-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="6f412-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="6f412-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="6f412-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="6f412-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="6f412-111">На панели навигации слева щелкните **топология** и выберите **состояние**.</span><span class="sxs-lookup"><span data-stu-id="6f412-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="6f412-112">На странице " **состояние** " выполните сортировку и поиск по списку, а затем щелкните компьютер, который вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="6f412-112">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>

5.  <span data-ttu-id="6f412-113">Нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="6f412-113">Click **Properties**.</span></span>

6.  <span data-ttu-id="6f412-114">В окне **Просмотр сведений о компьютере** при необходимости отсортируйте список служб, а затем выберите службу, которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="6f412-114">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>

7.  <span data-ttu-id="6f412-115">При необходимости выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="6f412-115">Do any of the following as needed:</span></span>
    
      - <span data-ttu-id="6f412-116">Чтобы просмотреть Последнее состояние данной службы, щелкните **получить состояние службы**.</span><span class="sxs-lookup"><span data-stu-id="6f412-116">To see the latest status of that specific service, click **Get service status**.</span></span>
    
      - <span data-ttu-id="6f412-117">Чтобы просмотреть сведения о конкретной службе, нажмите кнопку **Свойства** , а затем — кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="6f412-117">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
    
      - <span data-ttu-id="6f412-118">Чтобы вернуться к списку всех компьютеров в вашей топологии, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="6f412-118">To return to the list of all computers in your topology, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6f412-119">См. также</span><span class="sxs-lookup"><span data-stu-id="6f412-119">See Also</span></span>


[<span data-ttu-id="6f412-120">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6f412-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

