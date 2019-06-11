---
title: Авторизовать подключение к Office Communications Server 2007 R2 Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f81d8aaf9a01fc73516778487f8cc9a2d28a04ca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841106"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="59afb-102">Авторизовать подключение к Office Communications Server 2007 R2 Edge Server</span><span class="sxs-lookup"><span data-stu-id="59afb-102">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="59afb-103">_**Тема последнего изменения:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="59afb-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="59afb-104">Для каждого сервера переднего плана и сервера Standard Edition для Lync Server 2013 в пилотном пуле необходимо обновить список внутренних серверов, которым разрешено подключаться к серверу Office Communications Server 2007 R2 Edge.</span><span class="sxs-lookup"><span data-stu-id="59afb-104">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="59afb-105">Без этих обновлений не работают внешние аудио-и визуальные конференции для пользователей, присоединяющихся с помощью устаревшего пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="59afb-105">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="59afb-106">Чтобы авторизовать подключение к Office Communications Server 2007 R2 Edge Server</span><span class="sxs-lookup"><span data-stu-id="59afb-106">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="59afb-107">На пограничном сервере Office Communications Server 2007 R2 в группе **средства администрирования** откройте оснастку **Управление компьютером** .</span><span class="sxs-lookup"><span data-stu-id="59afb-107">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="59afb-108">В дереве консоли разверните узел **службы и приложения**.</span><span class="sxs-lookup"><span data-stu-id="59afb-108">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="59afb-109">Щелкните правой кнопкой мыши **Office Communications Server 2007 R2**и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="59afb-109">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="59afb-110">Откройте вкладку **внутренний** .</span><span class="sxs-lookup"><span data-stu-id="59afb-110">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="59afb-111">В разделе **Добавить сервер**нажмите кнопку **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="59afb-111">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="59afb-112">В диалоговом окне **Добавление сервера Office Communications Server** введите нужные сведения.</span><span class="sxs-lookup"><span data-stu-id="59afb-112">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="59afb-113">Укажите полное доменное имя (FQDN) каждого сервера Lync Server 2013, а также сервера Standard Edition и пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="59afb-113">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="59afb-114">Укажите полное доменное имя режиссера Lync Server 2013, если вы настроили статический маршрут для пула, указывающий на следующий компьютер по полному доменному имени.</span><span class="sxs-lookup"><span data-stu-id="59afb-114">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="59afb-115">После добавления записи для каждого сервера Lync Server 2013, сервера переднего плана, сервера Standard Edition, пула и режиссера нажмите кнопку **Применить** , а затем нажмите кнопку **ОК** , чтобы закрыть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="59afb-115">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

