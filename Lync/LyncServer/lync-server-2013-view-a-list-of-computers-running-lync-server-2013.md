---
title: 'Lync Server 2013: Просмотр списка компьютеров с Lync Server 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View a list of computers running Lync Server 2013
ms:assetid: 44eeec27-8b99-44f0-b0bd-622c12393d34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520987(v=OCS.15)
ms:contentKeyID: 48184030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce8b81f213e11f62632f4c74bdf62e3ac64e0168
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849172"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-computers-running-lync-server-2013"></a><span data-ttu-id="9facf-102">Просмотр списка компьютеров с Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9facf-102">View a list of computers running Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9facf-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9facf-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9facf-104">Вы можете использовать панель управления Lync Server 2013 для просмотра списка всех компьютеров с операционной системой Lync Server 2013 в вашей топологии и просмотра состояния службы каждого из них.</span><span class="sxs-lookup"><span data-stu-id="9facf-104">You can use Lync Server 2013 Control Panel to view a list of all the computers that are running Lync Server 2013 in your topology and see the service status of each.</span></span> <span data-ttu-id="9facf-105">Вы можете отсортировать список по компьютеру, пулу или сайту.</span><span class="sxs-lookup"><span data-stu-id="9facf-105">You can sort the list by computer, pool, or site.</span></span>

<div>

## <a name="to-view-a-list-of-computers-running-lync-server"></a><span data-ttu-id="9facf-106">Просмотр списка компьютеров с Lync Server</span><span class="sxs-lookup"><span data-stu-id="9facf-106">To view a list of computers running Lync Server</span></span>

1.  <span data-ttu-id="9facf-107">Из учетной записи пользователя, назначенной какой-либо из предопределенных административных ролей для Lync Server 2013, войдите на любой компьютер во внутренней среде выполнения.</span><span class="sxs-lookup"><span data-stu-id="9facf-107">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="9facf-108">Подробные сведения о стандартных ролях администратора, доступных в Lync Server 2013, можно найти [в разделе Планирование управления доступом на основе ролей в Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="9facf-108">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="9facf-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9facf-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9facf-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9facf-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9facf-111">На панели навигации слева щелкните топология \*\*\*\* и выберите **состояние**.</span><span class="sxs-lookup"><span data-stu-id="9facf-111">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="9facf-112">На странице " **состояние** " выполните любое из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="9facf-112">On the **Status** page, do any of the following as needed:</span></span>
    
      - <span data-ttu-id="9facf-113">Чтобы отсортировать список, щелкните заголовок столбца **компьютер**, **пул**или **сайт** , а затем нажмите стрелку вверх или стрелка вниз.</span><span class="sxs-lookup"><span data-stu-id="9facf-113">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    
      - <span data-ttu-id="9facf-114">Нажмите кнопку **Обновить** , чтобы просмотреть список самых последних обновлений.</span><span class="sxs-lookup"><span data-stu-id="9facf-114">Click **Refresh** to view the most up-to-date list.</span></span>
    
      - <span data-ttu-id="9facf-115">Поиск определенного компьютера с помощью ввода имени компьютера в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="9facf-115">Search for a specific computer by typing the computer name in the search field.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9facf-116">См. также</span><span class="sxs-lookup"><span data-stu-id="9facf-116">See Also</span></span>


[<span data-ttu-id="9facf-117">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9facf-117">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

