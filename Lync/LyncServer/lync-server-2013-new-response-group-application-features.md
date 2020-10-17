---
title: 'Lync Server 2013: новые функции приложения группы ответа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4ae3ad427164d8a948130e69fd54d1e6f8c37b9
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48536856"
---
# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="0e0dc-102">Новые функции приложения группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e0dc-102">New Response Group application features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0e0dc-103">_**Последнее изменение темы:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="0e0dc-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="0e0dc-104">Приложение «Группа ответа» позволяет направлять входящие вызовы определенным пользователям в особых целях или включать их в очередь; в список таких целей входит обслуживание клиентов, обращение во внутреннюю службу поддержки или службу общей телефонной поддержки подразделения.</span><span class="sxs-lookup"><span data-stu-id="0e0dc-104">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="0e0dc-105">Следующие функции приложения группы ответа являются новыми в Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="0e0dc-105">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="0e0dc-106">**Роль менеджера**</span><span class="sxs-lookup"><span data-stu-id="0e0dc-106">**Manager role**</span></span>
    
    <span data-ttu-id="0e0dc-107">Lync Server 2013 содержит новую роль руководителя группы ответа.</span><span class="sxs-lookup"><span data-stu-id="0e0dc-107">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="0e0dc-108">Теперь Существуют две роли управления для групп ответа: Диспетчер группы ответа и администратор группы ответа.</span><span class="sxs-lookup"><span data-stu-id="0e0dc-108">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="0e0dc-109">Несмотря на то, что администраторы группы ответа все еще могут настраивать любой элемент для любой группы ответа, менеджеры могут настраивать только определенные элементы, а только для групп ответа, которыми они владеют.</span><span class="sxs-lookup"><span data-stu-id="0e0dc-109">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="0e0dc-110">Это улучшение модели администрирования повышает масштабируемость приложения «Группа ответа», особенно если речь идет о крупных сценариях развертывания.</span><span class="sxs-lookup"><span data-stu-id="0e0dc-110">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="0e0dc-111">**Высокая доступность**</span><span class="sxs-lookup"><span data-stu-id="0e0dc-111">**High availability**</span></span>
    
    <span data-ttu-id="0e0dc-112">Поддержка высокого уровня доступности для приложения группы ответа в виде зеркального отображения SQL Server включена в рамках общей конфигурации и развертывания высокого уровня доступности для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e0dc-112">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="0e0dc-113">Если вы настроили поддержку высокой доступности, но при этом подключение к основному внутреннему серверу разрывается, на функционирование группы ответа не влияет использование зеркально отраженного внутреннего сервера.</span><span class="sxs-lookup"><span data-stu-id="0e0dc-113">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="0e0dc-114">Поддержка зеркального отображения SQL Server для приложения группы ответа не может быть индивидуально включена или настроена вне общей конфигурации сервера Lync Server 2013 с высокой доступностью.</span><span class="sxs-lookup"><span data-stu-id="0e0dc-114">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="0e0dc-115">**Аварийное восстановление**</span><span class="sxs-lookup"><span data-stu-id="0e0dc-115">**Disaster recovery**</span></span>
    
    <span data-ttu-id="0e0dc-116">Поддержка аварийного восстановления для приложения группы ответа включена в рамках настройки и развертывания связанных пулов переднего плана, которые являются частью общей конфигурации аварийного восстановления Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0e0dc-116">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="0e0dc-117">Кроме того, командлеты импорта и экспорта группы ответа поддерживают процесс аварийного переключения на резервный пул и восстановления размещения в основном пуле или новом пуле.</span><span class="sxs-lookup"><span data-stu-id="0e0dc-117">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="0e0dc-118">В случае сбоя в основном пуле группы ответа могут быть переключены на резервный пул, а затем возвращены в основной пул или новый пул после ликвидации сбоя.</span><span class="sxs-lookup"><span data-stu-id="0e0dc-118">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0e0dc-119">См. также</span><span class="sxs-lookup"><span data-stu-id="0e0dc-119">See Also</span></span>


[<span data-ttu-id="0e0dc-120">Планирование групп ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0e0dc-120">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

