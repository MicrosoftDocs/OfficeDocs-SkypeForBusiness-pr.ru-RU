---
title: 'Lync Server 2013: Просмотр списка надежных приложений'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View a list of trusted applications
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182604(v=OCS.15)
ms:contentKeyID: 48185844
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3d5f9d112e045e753147f7fcffa875177a6feb0d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757503"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a><span data-ttu-id="41721-102">Просмотр списка надежных приложений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41721-102">View a list of trusted applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41721-103">_**Тема последнего изменения:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="41721-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="41721-104">Вы можете использовать панель управления Lync Server 2013 для просмотра списка доверенных приложений, развернутых в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41721-104">You can use Lync Server 2013 Control Panel to view a list of the trusted applications that you have deployed in your Lync Server 2013 environment.</span></span> <span data-ttu-id="41721-105">Надежное приложение — это приложение, основанное на управляемом наборе API Microsoft Unified Communications (УКМА 3,0), который является надежным для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41721-105">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Lync Server 2013.</span></span> <span data-ttu-id="41721-106">Это отношение доверия представлено в следующем списке.</span><span class="sxs-lookup"><span data-stu-id="41721-106">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="41721-107">Доверенные приложения не предназначены для проверки подлинности на сервере Lync Server.</span><span class="sxs-lookup"><span data-stu-id="41721-107">Trusted applications are not challenged for authentication by Lync Server.</span></span>

  - <span data-ttu-id="41721-108">Доверенные приложения не заменяются на Lync Server для транзакций SIP, подключений и исходящих голосовых вызовов по протоколу VoIP.</span><span class="sxs-lookup"><span data-stu-id="41721-108">Trusted applications are not throttled by Lync Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="41721-109">Доверенные приложения могут олицетворять любого пользователя и могут присоединиться к конференциям без отображения в списке.</span><span class="sxs-lookup"><span data-stu-id="41721-109">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="41721-110">Доверенные приложения являются высокодоступными и устойчивыми.</span><span class="sxs-lookup"><span data-stu-id="41721-110">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="41721-111">На панели управления Lync Server вы можете просматривать имена приложений, пула, в которых они выполняются, и используемого ими порта.</span><span class="sxs-lookup"><span data-stu-id="41721-111">In Lync Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>

<div>

## <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="41721-112">Просмотр списка надежных приложений</span><span class="sxs-lookup"><span data-stu-id="41721-112">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="41721-113">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи, назначенной роли CsServerAdministrator, CsAdministrator, CsHelpDesk или CsViewOnlyAdministrator.</span><span class="sxs-lookup"><span data-stu-id="41721-113">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="41721-114">Подробные сведения о стандартных ролях администратора, доступных в Lync Server 2013, можно найти [в разделе Планирование управления доступом на основе ролей в Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="41721-114">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="41721-115">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="41721-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="41721-116">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="41721-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="41721-117">На панели навигации слева щелкните **топология** и выберите пункт **доверенное приложение**.</span><span class="sxs-lookup"><span data-stu-id="41721-117">In the left navigation bar, click **Topology** and the click **Trusted Application**.</span></span>

4.  <span data-ttu-id="41721-118">На странице **Trusted Application (доверенное приложение** ) щелкните заголовок столбца, чтобы отсортировать приложения, если это необходимо.</span><span class="sxs-lookup"><span data-stu-id="41721-118">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="41721-119">См. также</span><span class="sxs-lookup"><span data-stu-id="41721-119">See Also</span></span>


[<span data-ttu-id="41721-120">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41721-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

