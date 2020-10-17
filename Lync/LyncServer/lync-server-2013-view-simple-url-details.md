---
title: 'Lync Server 2013: Просмотр сведений о простых URL-адресах'
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
ms.openlocfilehash: 853ab8a5727991eace45b452f6991ed2efaacde7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518426"
---
# <a name="view-simple-url-details-in-lync-server-2013"></a><span data-ttu-id="124e0-102">Просмотр сведений об простых URL-адресах в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="124e0-102">View simple URL details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="124e0-103">_**Последнее изменение темы:** 2012-10-11_</span><span class="sxs-lookup"><span data-stu-id="124e0-103">_**Topic Last Modified:** 2012-10-11_</span></span>

<span data-ttu-id="124e0-104">Вы можете использовать панель управления Lync Server 2013 для просмотра простых URL-адресов для вашей среды Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="124e0-104">You can use Lync Server 2013 Control Panel to view simple URL details for your Lync Server 2013 environment.</span></span> <span data-ttu-id="124e0-105">Простые URL-адреса облегчают пользователям присоединение к собраниям и упрощают доступ администраторов к средствам администрирования.</span><span class="sxs-lookup"><span data-stu-id="124e0-105">Simple URLs make it easier for users to join meetings, and they make it easier for administrators to get to administrative tools.</span></span> <span data-ttu-id="124e0-106">Подробные сведения см. [в статье Планирование простых URL-адресов в Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span><span class="sxs-lookup"><span data-stu-id="124e0-106">For details, see [Planning for simple URLs in Lync Server 2013](lync-server-2013-planning-for-simple-urls.md).</span></span>

<div>

## <a name="to-view-simple-url-details"></a><span data-ttu-id="124e0-107">Просмотр сведений о простых URL-адресах</span><span class="sxs-lookup"><span data-stu-id="124e0-107">To view Simple URL details</span></span>

1.  <span data-ttu-id="124e0-108">Из учетной записи пользователя, назначенной для роли CsServerAdministrator, CsAdministrator, CsHelpDesk или CsViewOnlyAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="124e0-108">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="124e0-109">Подробные сведения о предопределенных административных ролях, доступных в Lync Server 2013, приведены в статье [Планирование управления доступом на основе ролей в Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="124e0-109">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="124e0-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="124e0-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="124e0-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="124e0-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="124e0-112">В левой панели навигации щелкните элемент **Топология**, а затем элемент **Простой URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="124e0-112">In the left navigation bar, click **Topology** and then click **Simple URL**.</span></span>

4.  <span data-ttu-id="124e0-113">На странице **Простой URL-адрес** щелкните заголовок столбца, чтобы упорядочить список при необходимости.</span><span class="sxs-lookup"><span data-stu-id="124e0-113">On the **Simple URL** page, click a column heading to sort the list, if needed.</span></span>

5.  <span data-ttu-id="124e0-114">Выберите имя, для которого требуется просмотреть сведения о простых URL-адресах, а затем щелкните **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="124e0-114">Select the name for which you want to see simple URL details, and then click **Properties**.</span></span>

6.  <span data-ttu-id="124e0-115">Закончив просмотр сведений, нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="124e0-115">When you are finished viewing details, click **Close**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="124e0-116">См. также</span><span class="sxs-lookup"><span data-stu-id="124e0-116">See Also</span></span>


[<span data-ttu-id="124e0-117">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="124e0-117">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

