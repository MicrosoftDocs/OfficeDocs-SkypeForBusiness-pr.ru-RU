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
ms.openlocfilehash: bddf1f670ef2a0a246100564962b2f69db741186
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755903"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="64786-102">Новые функции приложения группы ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64786-102">New Response Group application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="64786-103">_**Тема последнего изменения:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="64786-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="64786-104">С помощью приложения "группа ответа" можно маршрутизировать и ставить в очередь входящие звонки определенным пользователям для специальных целей, таких как обслуживание клиентов, внутренняя служба поддержки или общая техническая поддержка по телефону для отдела.</span><span class="sxs-lookup"><span data-stu-id="64786-104">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="64786-105">В Lync Server 2013 доступны следующие функции приложения группы ответа:</span><span class="sxs-lookup"><span data-stu-id="64786-105">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="64786-106">**Роль руководителя**</span><span class="sxs-lookup"><span data-stu-id="64786-106">**Manager role**</span></span>
    
    <span data-ttu-id="64786-107">Lync Server 2013 представляет новую роль руководителя группы ответа.</span><span class="sxs-lookup"><span data-stu-id="64786-107">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="64786-108">Теперь для групп ответа существуют две роли: Диспетчер групп ответов и администратор групп ответов.</span><span class="sxs-lookup"><span data-stu-id="64786-108">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="64786-109">Несмотря на то, что администраторы групп ответа по-прежнему могут настраивать любой элемент для любой группы ответа, руководители могут настраивать только определенные элементы, только для групп ответа, которыми они владеют.</span><span class="sxs-lookup"><span data-stu-id="64786-109">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="64786-110">Это улучшение масштабируемости групп ответов на модель администрирования, особенно для крупных сценариев развертывания.</span><span class="sxs-lookup"><span data-stu-id="64786-110">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="64786-111">**Высокая доступность**</span><span class="sxs-lookup"><span data-stu-id="64786-111">**High availability**</span></span>
    
    <span data-ttu-id="64786-112">Поддержка высокого уровня доступности для приложения группы ответа в виде зеркального отображения SQL Server включена как часть общей конфигурации и развертывания высокого уровня доступности для Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="64786-112">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="64786-113">Если вы настроили высокий уровень доступности и потеряли связь с основным серверным сервером, то функция группы ответа не влияет на использование зеркального серверного резервного сервера.</span><span class="sxs-lookup"><span data-stu-id="64786-113">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="64786-114">Поддержка зеркального отображения SQL Server для группы ответа не может быть включена или настроена отдельно для всей конфигурации Lync Server 2013 с высокой степенью доступности.</span><span class="sxs-lookup"><span data-stu-id="64786-114">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="64786-115">**Аварийное восстановление**</span><span class="sxs-lookup"><span data-stu-id="64786-115">**Disaster recovery**</span></span>
    
    <span data-ttu-id="64786-116">Поддержка аварийного восстановления для приложения группы ответа включена как часть конфигурации и развертывания подключенных групп переднего плана, которые являются частью общей конфигурации сервера Lync Server 2013 с аварийным восстановлением.</span><span class="sxs-lookup"><span data-stu-id="64786-116">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="64786-117">Кроме того, командлеты импорта и экспорта группы ответа поддерживают процесс отработки отказа в пуле резервных копий и процесс восстановления размещения для основного пула или для нового пула.</span><span class="sxs-lookup"><span data-stu-id="64786-117">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="64786-118">При возникновении сбоя в основном пуле группы ответа можно не отменять в пуле резервных копий, а затем отпустить в основном пуле или в новом пуле, когда переход на другой план завершился.</span><span class="sxs-lookup"><span data-stu-id="64786-118">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="64786-119">См. также</span><span class="sxs-lookup"><span data-stu-id="64786-119">See Also</span></span>


[<span data-ttu-id="64786-120">Планирование групп ответа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="64786-120">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

