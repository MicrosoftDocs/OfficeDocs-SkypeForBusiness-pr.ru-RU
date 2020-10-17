---
title: Авторизация подключения к пограничному серверу Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Authorize connection to Office Communications Server 2007 R2 Edge Server
ms:assetid: 14f6798a-28d6-4b3d-8734-942192e1bbf5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204702(v=OCS.15)
ms:contentKeyID: 48183493
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6181f3d42facaf49b84b7c07776dc8717e88b271
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499766"
---
# <a name="authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="0bfd1-102">Авторизация подключения к пограничному серверу Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="0bfd1-102">Authorize connection to Office Communications Server 2007 R2 Edge Server</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0bfd1-103">_**Последнее изменение темы:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="0bfd1-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="0bfd1-104">Для каждого сервера переднего плана Lync Server 2013 или сервера Standard Edition в пилотном пуле необходимо обновить список внутренних серверов, которым разрешено подключаться к пограничному серверу Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="0bfd1-104">For each Lync Server 2013 Front End Server or Standard Edition server in your pilot pool, you must update the list of internal servers that are authorized to connect to the Office Communications Server 2007 R2 Edge Server.</span></span> <span data-ttu-id="0bfd1-105">Без этих обновлений внешние аудио и видеоконференции для пользователей, присоединяющихся к конференц-связи с помощью унаследованного пограничного сервера, не будут работать.</span><span class="sxs-lookup"><span data-stu-id="0bfd1-105">Without these updates, external audio/visual (A/V) conferencing for users joining by using the legacy Edge Server will not work.</span></span>

<div>

## <a name="to-authorize-connection-to-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="0bfd1-106">Авторизация подключения к пограничному серверу Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="0bfd1-106">To Authorize Connection to Office Communications Server 2007 R2 Edge Server</span></span>

1.  <span data-ttu-id="0bfd1-107">На пограничном сервере Office Communications Server 2007 R2 **в группе Администрирование** откройте оснастку " **Управление компьютером** ".</span><span class="sxs-lookup"><span data-stu-id="0bfd1-107">From the Office Communications Server 2007 R2 Edge Server, from the **Administrative Tools** group, open the **Computer Management** snap-in.</span></span>

2.  <span data-ttu-id="0bfd1-108">В дереве консоли разверните узел **Службы и приложения**.</span><span class="sxs-lookup"><span data-stu-id="0bfd1-108">In the console tree, expand **Services and Applications**.</span></span>

3.  <span data-ttu-id="0bfd1-109">Щелкните правой кнопкой мыши **Office Communications Server 2007 R2**и выберите пункт **свойства**.</span><span class="sxs-lookup"><span data-stu-id="0bfd1-109">Right-click **Office Communications Server 2007 R2**, and then click **Properties**.</span></span>

4.  <span data-ttu-id="0bfd1-110">Откройте вкладку **Внутренние**.</span><span class="sxs-lookup"><span data-stu-id="0bfd1-110">Click the **Internal** tab.</span></span>

5.  <span data-ttu-id="0bfd1-111">В разделе **Добавить сервер** щелкните **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="0bfd1-111">Under **Add Server**, click **Add**.</span></span>

6.  <span data-ttu-id="0bfd1-112">В диалоговом окне **Добавление сервера Office Communications Server** введите соответствующие сведения:</span><span class="sxs-lookup"><span data-stu-id="0bfd1-112">In the **Add Office Communications Server** dialog box, enter the appropriate information:</span></span>
    
      - <span data-ttu-id="0bfd1-113">Укажите полное доменное имя (FQDN) каждого сервера переднего плана Lync Server 2013 или сервера Standard Edition и пула Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0bfd1-113">Specify the fully qualified domain name (FQDN) of each Lync Server 2013 Front End Server or Standard Edition server, and Lync Server 2013 pool.</span></span>
    
      - <span data-ttu-id="0bfd1-114">Укажите полное доменное имя для Lync Server 2013 Director, если вы настроили статический маршрут в пуле, указывающий компьютер следующего прыжка по полному доменному имени.</span><span class="sxs-lookup"><span data-stu-id="0bfd1-114">Specify the FQDN of the Lync Server 2013 Director if you configured a static route on the pool that specifies the next hop computer by its FQDN.</span></span>

7.  <span data-ttu-id="0bfd1-115">После добавления записи для каждого сервера Lync Server 2013, сервера переднего плана, сервера Standard Edition, пула и директора, нажмите кнопку **Применить** , а затем нажмите кнопку **ОК** , чтобы закрыть страницу свойств.</span><span class="sxs-lookup"><span data-stu-id="0bfd1-115">After you have added an entry for each Lync Server 2013, Front End Server, Standard Edition server, pool, and Director, click **Apply** and then click **OK** to close the Properties page.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

