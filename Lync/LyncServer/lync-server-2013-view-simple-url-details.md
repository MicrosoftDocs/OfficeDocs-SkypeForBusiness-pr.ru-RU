---
title: 'Lync Server 2013: Просмотр данных простого URL-адреса'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View simple URL details
ms:assetid: 6ab00f2c-e1d5-4698-a58f-04b72260f9ac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521010(v=OCS.15)
ms:contentKeyID: 48184399
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f77c860d58ecc391298b88f4e1855ddd80199d8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757433"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-simple-url-details-in-lync-server-2013"></a><span data-ttu-id="7be6d-102">Просмотр простых данных URL-адреса в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7be6d-102">View simple URL details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7be6d-103">_**Тема последнего изменения:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="7be6d-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="7be6d-104">Вы можете использовать панель управления Lync Server 2013 для просмотра простых данных URL-адреса для вашей среды Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7be6d-104">You can use Lync Server 2013 Control Panel to view simple URL details for your Lync Server 2013 environment.</span></span> <span data-ttu-id="7be6d-105">Простые URL-адреса упрощают присоединение к собраниям, а также облегчает администраторам доступ к средствам администрирования.</span><span class="sxs-lookup"><span data-stu-id="7be6d-105">Simple URLs make it easier for users to join meetings, and they make it easier for administrators to get to administrative tools.</span></span> <span data-ttu-id="7be6d-106">Подробные сведения можно найти [в разделе Планирование простых URL-адресов в Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="7be6d-106">For details, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<div>

## <a name="to-view-simple-url-details"></a><span data-ttu-id="7be6d-107">Просмотр простых данных URL-адреса</span><span class="sxs-lookup"><span data-stu-id="7be6d-107">To view Simple URL details</span></span>

1.  <span data-ttu-id="7be6d-108">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи, назначенной роли CsServerAdministrator, CsAdministrator, CsHelpDesk или CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="7be6d-108">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="7be6d-109">Подробные сведения о стандартных ролях администратора, доступных в Lync Server 2013, можно найти [в разделе Планирование управления доступом на основе ролей в Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="7be6d-109">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="7be6d-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7be6d-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7be6d-111">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7be6d-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7be6d-112">На панели навигации слева выберите пункт **топология** и щелкните **простой URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="7be6d-112">In the left navigation bar, click **Topology** and then click **Simple URL**.</span></span>

4.  <span data-ttu-id="7be6d-113">На странице **простой URL-адрес** щелкните заголовок столбца, чтобы отсортировать список (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="7be6d-113">On the **Simple URL** page, click a column heading to sort the list, if needed.</span></span>

5.  <span data-ttu-id="7be6d-114">Выберите имя, для которого требуется получить простой URL-адрес, и нажмите кнопку **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7be6d-114">Select the name for which you want to see simple URL details, and then click **Properties**.</span></span>

6.  <span data-ttu-id="7be6d-115">Когда вы закончите просмотр сведений, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="7be6d-115">When you are finished viewing details, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7be6d-116">См. также</span><span class="sxs-lookup"><span data-stu-id="7be6d-116">See Also</span></span>


[<span data-ttu-id="7be6d-117">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7be6d-117">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

