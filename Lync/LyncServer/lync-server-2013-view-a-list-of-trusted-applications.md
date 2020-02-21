---
title: 'Lync Server 2013: Просмотр списка доверенных приложений'
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
ms.openlocfilehash: 8678ed12269f7f78d6d169b518e7f1208d92a7fd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211605"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="view-a-list-of-trusted-applications-in-lync-server-2013"></a><span data-ttu-id="544a0-102">Просмотр списка доверенных приложений в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="544a0-102">View a list of trusted applications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="544a0-103">_**Последнее изменение темы:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="544a0-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="544a0-104">Вы можете использовать панель управления Lync Server 2013 для просмотра списка доверенных приложений, развернутых в среде Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="544a0-104">You can use Lync Server 2013 Control Panel to view a list of the trusted applications that you have deployed in your Lync Server 2013 environment.</span></span> <span data-ttu-id="544a0-105">Доверенное приложение — это приложение, основанное на Microsoft Unified Communications Managed API (UCMA) 3,0 Core SDK, которому доверяет Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="544a0-105">A trusted application is an application based on Microsoft Unified Communications Managed API (UCMA) 3.0 Core SDK that is trusted by Lync Server 2013.</span></span> <span data-ttu-id="544a0-106">В списке ниже приведены сведения об этом отношении доверия.</span><span class="sxs-lookup"><span data-stu-id="544a0-106">This trust relationship is summarized in the following list:</span></span>

  - <span data-ttu-id="544a0-107">Доверенные приложения не вызывают проверку подлинности Lync Server.</span><span class="sxs-lookup"><span data-stu-id="544a0-107">Trusted applications are not challenged for authentication by Lync Server.</span></span>

  - <span data-ttu-id="544a0-108">Доверенные приложения не регулируется сервером Lync Server для транзакций SIP, подключений или исходящих звонков по протоколу VoIP.</span><span class="sxs-lookup"><span data-stu-id="544a0-108">Trusted applications are not throttled by Lync Server for SIP transactions, connections or outgoing Voice over Internet Protocol (VoIP) calls.</span></span>

  - <span data-ttu-id="544a0-109">Доверенные приложения могут олицетворять любого пользователя и присоединиться к конференциям, минуя списки.</span><span class="sxs-lookup"><span data-stu-id="544a0-109">Trusted applications can impersonate any user and can join conferences without appearing in rosters.</span></span>

  - <span data-ttu-id="544a0-110">Доверенные приложения устойчивы и надежны.</span><span class="sxs-lookup"><span data-stu-id="544a0-110">Trusted applications are highly available and resilient.</span></span>

<span data-ttu-id="544a0-111">В панели управления Lync Server можно просмотреть имена приложений, пула, в котором они выполняются, и порт, который они используют.</span><span class="sxs-lookup"><span data-stu-id="544a0-111">In Lync Server Control Panel, you can see the name of the applications, the pool where they run, and the port they use.</span></span>

<div>

## <a name="to-view-a-list-of-trusted-applications"></a><span data-ttu-id="544a0-112">Просмотр списка доверенных приложений</span><span class="sxs-lookup"><span data-stu-id="544a0-112">To view a list of trusted applications</span></span>

1.  <span data-ttu-id="544a0-113">Из учетной записи пользователя, назначенной для роли CsServerAdministrator, CsAdministrator, CsHelpDesk или CsViewOnlyAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="544a0-113">From a user account that is assigned to the CsServerAdministrator, CsAdministrator, CsHelpDesk, or CsViewOnlyAdministrator role, log on to any computer in your internal deployment.</span></span> <span data-ttu-id="544a0-114">Подробные сведения о предопределенных административных ролях, доступных в Lync Server 2013, приведены в статье [Планирование управления доступом на основе ролей в Lync server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="544a0-114">For details about the predefined administrative roles available in Lync Server 2013, see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md).</span></span>

2.  <span data-ttu-id="544a0-115">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="544a0-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="544a0-116">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="544a0-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="544a0-117">В левой области навигации щелкните элемент **Топология**, а затем **Доверенное приложение**.</span><span class="sxs-lookup"><span data-stu-id="544a0-117">In the left navigation bar, click **Topology** and the click **Trusted Application**.</span></span>

4.  <span data-ttu-id="544a0-118">На странице **Доверенное приложение** щелкните заголовок столбца, чтобы выполнить сортировку приложений (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="544a0-118">On the **Trusted Application** page, click a column heading to sort the applications, if needed.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="544a0-119">См. также</span><span class="sxs-lookup"><span data-stu-id="544a0-119">See Also</span></span>


[<span data-ttu-id="544a0-120">Управление топологией Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="544a0-120">Managing the Lync Server 2013 topology</span></span>](lync-server-2013-managing-the-lync-server-topology.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

