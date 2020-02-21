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
ms.openlocfilehash: 0769c8cc327a3cc4889a79f32bb5b9af0b1e3087
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-details-about-a-service-in-lync-server-2013"></a><span data-ttu-id="a51ab-102">Просмотр сведений о службе в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a51ab-102">View details about a service in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a51ab-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="a51ab-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="a51ab-104">Вы можете использовать панель управления Lync Server для просмотра сведений о каждой службе, запущенной на определенном компьютере в топологии.</span><span class="sxs-lookup"><span data-stu-id="a51ab-104">You can use Lync Server Control Panel to view details about each service that is running on a specific computer in your topology.</span></span> <span data-ttu-id="a51ab-105">Панель управления предоставляет сведения о состоянии каждой службы, а также дополнительные данные о службе, например сведения о подключенных базах данных, портах и зависимых службах.</span><span class="sxs-lookup"><span data-stu-id="a51ab-105">You can view the status of each service and details such as the associated databases, ports, and dependent services.</span></span>

<div>

## <a name="to-view-details-for-a-service"></a><span data-ttu-id="a51ab-106">Просмотр сведений о службе</span><span class="sxs-lookup"><span data-stu-id="a51ab-106">To view details for a service</span></span>

1.  <span data-ttu-id="a51ab-107">Из учетной записи пользователя, назначенной любой из предопределенных административных ролей Lync Server 2013, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="a51ab-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="a51ab-108">Подробные сведения о предопределенных административных ролях, доступных в Lync Server 2013, приведены в статье [Планирование управления доступом на основе ролей в Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="a51ab-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="a51ab-109">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a51ab-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a51ab-110">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a51ab-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a51ab-111">В левой панели навигации щелкните **Топология** и затем щелкните **Состояние**.</span><span class="sxs-lookup"><span data-stu-id="a51ab-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="a51ab-112">На странице **Состояние** выполните сортировку списка или найдите требуемый компьютер.</span><span class="sxs-lookup"><span data-stu-id="a51ab-112">In the **Status** page, sort or search through the list and then click the computer that you want to view.</span></span>

5.  <span data-ttu-id="a51ab-113">Щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="a51ab-113">Click **Properties**.</span></span>

6.  <span data-ttu-id="a51ab-114">В окне **Просмотр сведений о компьютере** отсортируйте список служб при необходимости и выберите службу, которую необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="a51ab-114">In the **View Computer Detail** window, sort the list of services, if necessary, and click the service you want to view.</span></span>

7.  <span data-ttu-id="a51ab-115">Выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a51ab-115">Do any of the following as needed:</span></span>
    
      - <span data-ttu-id="a51ab-116">Чтобы просмотреть последнее состояние определенной службы, щелкните **Получить сведения о состоянии службы**.</span><span class="sxs-lookup"><span data-stu-id="a51ab-116">To see the latest status of that specific service, click **Get service status**.</span></span>
    
      - <span data-ttu-id="a51ab-117">Чтобы просмотреть сведения об определенной службе, щелкните **Свойства** и затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a51ab-117">To see the details for that specific service, click **Properties** and then click **Close**.</span></span>
    
      - <span data-ttu-id="a51ab-118">Чтобы получить список компьютеров, используемых в топологии, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a51ab-118">To return to the list of all computers in your topology, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a51ab-119">См. также</span><span class="sxs-lookup"><span data-stu-id="a51ab-119">See Also</span></span>


[<span data-ttu-id="a51ab-120">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a51ab-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

