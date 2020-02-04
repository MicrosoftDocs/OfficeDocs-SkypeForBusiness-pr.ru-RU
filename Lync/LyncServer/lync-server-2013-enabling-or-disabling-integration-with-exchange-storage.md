---
title: 'Lync Server 2013: Включение и отключение интеграции с хранилищем Exchange'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling integration with Exchange storage
ms:assetid: c08b9ba5-04f6-452a-b44c-c130f1564a34
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205228(v=OCS.15)
ms:contentKeyID: 48185295
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5c8a52aabb504ce63ef6e340b5a68e9e8c4c0e7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735669"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-integration-of-lync-server-2013-with-exchange-storage"></a><span data-ttu-id="60cc2-102">Включение и отключение интеграции Lync Server 2013 с хранилищем Exchange</span><span class="sxs-lookup"><span data-stu-id="60cc2-102">Enabling or disabling integration of Lync Server 2013 with Exchange storage</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60cc2-103">_**Тема последнего изменения:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="60cc2-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="60cc2-104">В панели управления Lync Server 2013 вы можете включать и отключать интеграцию с хранилищем Exchange с помощью конфигураций архивации.</span><span class="sxs-lookup"><span data-stu-id="60cc2-104">In Lync Server 2013 Control Panel, you use Archiving configurations to enable and disable integration with Exchange storage.</span></span> <span data-ttu-id="60cc2-105">К ним относятся следующие конфигурации архивации:</span><span class="sxs-lookup"><span data-stu-id="60cc2-105">This includes the following Archiving configurations:</span></span>

  - <span data-ttu-id="60cc2-106">Глобальная конфигурация, создаваемая по умолчанию при развертывании Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="60cc2-106">A global configuration that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="60cc2-107">Необязательные конфигурации уровня сайта и пула, которые можно создать и использовать для определения способа реализации архивации для конкретных сайтов или пулов.</span><span class="sxs-lookup"><span data-stu-id="60cc2-107">Optional site-level and pool-level configurations that you can create and use to specify how archiving is implemented for specific sites or pools.</span></span>

<span data-ttu-id="60cc2-108">Сведения о том, как работают конфигурации архивации, в том числе о параметрах, которые можно указать и в иерархии конфигураций архивации, описаны в разделе [Использование архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="60cc2-108">For details about how Archiving configurations are implemented, including which options you can specify and the hierarchy of Archiving configurations, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>

## <a name="to-enable-or-disable-integration-with-microsoft-exchange-storage"></a><span data-ttu-id="60cc2-109">Включение и отключение интеграции с хранилищем Microsoft Exchange</span><span class="sxs-lookup"><span data-stu-id="60cc2-109">To enable or disable integration with Microsoft Exchange storage</span></span>

1.  <span data-ttu-id="60cc2-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsArchivingAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="60cc2-110">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="60cc2-111">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="60cc2-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="60cc2-112">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="60cc2-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="60cc2-113">На левой панели навигации щелкните **Мониторинг и архивация**, а затем щелкните **Конфигурация архивации**.</span><span class="sxs-lookup"><span data-stu-id="60cc2-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>

4.  <span data-ttu-id="60cc2-114">В списке конфигураций архивации щелкните имя подходящей глобальной конфигурации либо конфигурации сайта или пула, щелкните **Изменить** и **Показать подробности**, затем выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="60cc2-114">Click the name of the appropriate global, site, or pool configuration in the list of archiving configurations, click **Edit**, click **Show details**, and then do the following:</span></span>
    
      - <span data-ttu-id="60cc2-115">Чтобы включить интеграцию с хранилищем Exchange 2013, установите флажок **интеграция Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="60cc2-115">To enable integration with Exchange 2013 storage, select the **Microsoft Exchange integration** check box.</span></span>
    
      - <span data-ttu-id="60cc2-116">Чтобы отключить интеграцию с хранилищем Exchange 2013, снимите флажок **интеграция Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="60cc2-116">To disable integration with Exchange 2013 storage, clear the **Microsoft Exchange integration** check box.</span></span>

5.  <span data-ttu-id="60cc2-117">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="60cc2-117">Click **Commit**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="60cc2-118">См. также</span><span class="sxs-lookup"><span data-stu-id="60cc2-118">See Also</span></span>


[<span data-ttu-id="60cc2-119">Как работает архивация в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="60cc2-119">How Archiving works in Lync Server 2013</span></span>](lync-server-2013-how-archiving-works.md)  


[<span data-ttu-id="60cc2-120">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов</span><span class="sxs-lookup"><span data-stu-id="60cc2-120">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</span></span>](lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

