---
title: 'Lync Server 2013: Просмотр списка компьютеров, на которых работает Lync Server 2013'
description: 'Lync Server 2013: Просмотр списка компьютеров, на которых работает Lync Server 2013.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of computers running Lync Server 2013
ms:assetid: 44eeec27-8b99-44f0-b0bd-622c12393d34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520987(v=OCS.15)
ms:contentKeyID: 48184030
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: baeb2d8e926b1597c463259378332e0c9f50268f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567185"
---
# <a name="view-a-list-of-computers-running-lync-server-2013"></a><span data-ttu-id="2d891-103">Просмотр списка компьютеров, на которых работает Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d891-103">View a list of computers running Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2d891-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="2d891-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="2d891-105">Вы можете использовать панель управления Lync Server 2013, чтобы просмотреть список всех компьютеров, на которых работает Lync Server 2013 в вашей топологии, и просмотреть состояние каждой службы.</span><span class="sxs-lookup"><span data-stu-id="2d891-105">You can use Lync Server 2013 Control Panel to view a list of all the computers that are running Lync Server 2013 in your topology and see the service status of each.</span></span> <span data-ttu-id="2d891-106">Этот список можно упорядочивать по компьютерам, пулам или сайтам.</span><span class="sxs-lookup"><span data-stu-id="2d891-106">You can sort the list by computer, pool, or site.</span></span>

<div>

## <a name="to-view-a-list-of-computers-running-lync-server"></a><span data-ttu-id="2d891-107">Просмотр списка компьютеров, на которых работает Lync Server</span><span class="sxs-lookup"><span data-stu-id="2d891-107">To view a list of computers running Lync Server</span></span>

1.  <span data-ttu-id="2d891-108">Из учетной записи пользователя, назначенной любой из предопределенных административных ролей Lync Server 2013, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="2d891-108">From a user account that is assigned to any of the predefined administrative roles for Lync Server 2013, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="2d891-109">Подробные сведения о предопределенных административных ролях, доступных в Lync Server 2013, приведены в статье [Планирование управления доступом на основе ролей в Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="2d891-109">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="2d891-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2d891-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="2d891-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="2d891-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2d891-112">В левой панели навигации щелкните элемент **Топология**, а затем элемент **Состояние**.</span><span class="sxs-lookup"><span data-stu-id="2d891-112">In the left navigation bar, click **Topology** and then click **Status**.</span></span>

4.  <span data-ttu-id="2d891-113">На странице **Состояние** выполните все необходимые действия из приведенных ниже.</span><span class="sxs-lookup"><span data-stu-id="2d891-113">On the **Status** page, do any of the following as needed:</span></span>
    
      - <span data-ttu-id="2d891-114">Упорядочите список, щелкнув заголовок столбца **Компьютер**, **Пул** или **Сайт**, а затем щелкнув стрелку вверх или вниз.</span><span class="sxs-lookup"><span data-stu-id="2d891-114">Sort the list by clicking the **Computer**, **Pool**, or **Site** column heading, and then clicking the up arrow or the down arrow.</span></span>
    
      - <span data-ttu-id="2d891-115">Нажмите кнопку **Обновить**, чтобы просмотреть наиболее актуальный список.</span><span class="sxs-lookup"><span data-stu-id="2d891-115">Click **Refresh** to view the most up-to-date list.</span></span>
    
      - <span data-ttu-id="2d891-116">Найдите конкретный компьютер, введя его имя в поле поиска.</span><span class="sxs-lookup"><span data-stu-id="2d891-116">Search for a specific computer by typing the computer name in the search field.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2d891-117">См. также</span><span class="sxs-lookup"><span data-stu-id="2d891-117">See Also</span></span>


[<span data-ttu-id="2d891-118">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2d891-118">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

