---
title: 'Lync Server 2013: отработка отказа для пограничного пула, используемого для Федерации XMPP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 182bc427c7b4faf3bd937bd58af8ca1d4d9c7d77
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a><span data-ttu-id="53837-102">Отработка отказа для пограничного пула, используемого для Федерации XMPP в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53837-102">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53837-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="53837-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="53837-p101">В организации присутствует только один пограничный пул, назначенный  качестве пула для федерации XMPP. Если этот пул перестанет работать, необходимо выполнить отработку отказа федерации XMPP для использования другого пограничного пула, чтобы федерация XMPP снова начала функционировать.\</span><span class="sxs-lookup"><span data-stu-id="53837-p101">In your organization, there is one Edge pool designated as the pool to use for XMPP federation. If this pool goes down, you must fail over XMPP federation to use a different Edge pool before XMPP federation can work again.</span></span>

<span data-ttu-id="53837-106">При первой установке пограничных пулов и включении федерации XMPP можно упростить процедуру аварийного восстановления путем определения внешних SRV-записей DNS для всех пограничных пулов федерации XMPP, а не только одного.</span><span class="sxs-lookup"><span data-stu-id="53837-106">When you first install Edge pools and enable XMPP Federation, you can simplify the disaster recovery process by setting up external DNS SRV records for all of your Edge pools for XMPP federation, instead of just one.</span></span> <span data-ttu-id="53837-107">Каждая из этих SRV-записей должна содержать собственное значение приоритета.</span><span class="sxs-lookup"><span data-stu-id="53837-107">Each of these SRV records must have a different priority set.</span></span> <span data-ttu-id="53837-108">Весь трафик федерации XMPP проходит через пул с SRV-записью, имеющей наивысший приоритет.</span><span class="sxs-lookup"><span data-stu-id="53837-108">All XMPP federation traffic goes through the pool with the SRV record with the highest priority.</span></span> <span data-ttu-id="53837-109">Дополнительные сведения о включении и настройке Федерации XMPP можно найти [в статье Настройка Федерации XMPP в Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span><span class="sxs-lookup"><span data-stu-id="53837-109">For more information on enabling and setting up XMPP federation, see [Setting up XMPP federation in Lync Server 2013](lync-server-2013-setting-up-xmpp-federation.md).</span></span>

<span data-ttu-id="53837-110">В следующей процедуре EdgePool1 — это пул, в котором изначально была размещена федерация XMPP, а EdgePool2 — пул, в котором будет размещена федерация XMPP.</span><span class="sxs-lookup"><span data-stu-id="53837-110">In the following procedure, EdgePool1 is the pool which originally hosted XMPP federation, and EdgePool2 is the pool which will now host XMPP federation.</span></span>

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a><span data-ttu-id="53837-111">Отработка отказа пограничного пула, используемого для федерации XMPP</span><span class="sxs-lookup"><span data-stu-id="53837-111">Failing Over the Edge Pool Used for XMPP Federation</span></span>

1.  <span data-ttu-id="53837-112">Если другой пограничный пул еще не развернут (т. е. единственный пограничный пул в настоящее время не работает), разверните новый пул.</span><span class="sxs-lookup"><span data-stu-id="53837-112">If you don’t already have another Edge pool deployed (besides the one which is currently down), deploy that pool.</span></span> <span data-ttu-id="53837-113">Дополнительную информацию можно узнать [в статье Развертывание доступа внешних пользователей в Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span><span class="sxs-lookup"><span data-stu-id="53837-113">For details, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md).</span></span>

2.  <span data-ttu-id="53837-114">На каждом пограничном сервере в новом пограничном пуле, который теперь размещает федерацию XMPP EdgePool2), запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="53837-114">On each Edge Server in the new Edge pool which will now host XMPP federation (EdgePool2), run the following cmdlet:</span></span>
    
        Stop-CsWindowsService

3.  <span data-ttu-id="53837-115">Выполните следующий командлет, чтобы переопределить маршрут федерации XMPP на сервер EdgePool2:</span><span class="sxs-lookup"><span data-stu-id="53837-115">Run the following cmdlet to repoint the XMPP federation route to EdgePool2:</span></span>
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    <span data-ttu-id="53837-116">В этом примере Site2 — это сайт, содержащий пограничный пул, который в настоящее время содержит пограничный пул, через который проходит маршрут федерации XMPP, а EdgeServer2.contoso.com — это полное доменное имя пограничного сервера в этом пуле.</span><span class="sxs-lookup"><span data-stu-id="53837-116">In this example, Site2 is the site containing the Edge pool which will now host the XMPP federation route, and EdgeServer2.contoso.com is the FQDN of an Edge Server in that pool.</span></span>

4.  <span data-ttu-id="53837-117">На внешнем DNS-сервере измените запись узла A для федерации XMPP, чтобы она указывала на EdgeServer2.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="53837-117">On the external DNS server, change the DNS A record for XMPP federation to point to EdgeServer2.contoso.com.</span></span>

5.  <span data-ttu-id="53837-p104">Если отсутствует SRV-запись федерации XMPP, которая разрешается в адрес пограничного пула, поддерживающего в настоящее время федерацию XMPP, необходимо добавить ее, как показано в следующем примере. В этой SRV-записи необходимо указать значение порта 5269.</span><span class="sxs-lookup"><span data-stu-id="53837-p104">If you do not already have a DNS SRV record for XMPP federation which resolves to the Edge pool which will now host XMPP federation, you must add it, as in the following example. This SRV record must have a port value of 5269.</span></span>
    
        _xmpp-server._tcp.contoso.com

6.  <span data-ttu-id="53837-120">Убедитесь, что на внешнем интерфейсе пограничного пула, в котором теперь размещена федерация XMPP, открыт порт 5269.</span><span class="sxs-lookup"><span data-stu-id="53837-120">Verify that the Edge pool which will now host XMPP federation has port 5269 open externally.</span></span>

7.  <span data-ttu-id="53837-121">Запустите службу на всех пограничных серверах в пограничном пуле, содержащем федерацию XMPP:</span><span class="sxs-lookup"><span data-stu-id="53837-121">Start the services on all Edge Servers in the Edge pool which will now host XMPP federation:</span></span>
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

