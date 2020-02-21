---
title: 'Lync Server 2013: ежедневные задачи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Daily tasks
ms:assetid: f7a5f99e-5d2b-445d-9ba1-cbfcfeff16ae
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720351(v=OCS.15)
ms:contentKeyID: 63969666
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87653490036c55a5f8b60925c988775c881a7326
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="daily-tasks-in-lync-server-2013"></a><span data-ttu-id="dff70-102">Ежедневные задачи в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dff70-102">Daily tasks in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dff70-103">_**Последнее изменение темы:** 2015-01-26_</span><span class="sxs-lookup"><span data-stu-id="dff70-103">_**Topic Last Modified:** 2015-01-26_</span></span>

<span data-ttu-id="dff70-104">Чтобы обеспечить доступность и надежность развертывания Lync Server 2013, необходимо как часть ежедневных стандартных элементов мониторинга и тестирования, которые очень важны для функционирования системы, включая физическую платформу, операционную систему и все важные службы Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dff70-104">To help ensure the availability and reliability of the Lync Server 2013 deployment, you should as part of daily routine monitor and test elements that are very important to the functioning of the system, which includes the physical platform, the operating system, and all important Lync Server 2013 services.</span></span> <span data-ttu-id="dff70-105">Профилактическое обслуживание и профилактическое наблюдение помогут выявить потенциальные ошибки и проблемы, которые могут негативно повлиять на развертывание Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="dff70-105">Preventive maintenance and proactive monitoring will help you identify potential errors and issues that may adversely affect the Lync Server 2013 deployment.</span></span>

<span data-ttu-id="dff70-106">Мониторинг развертывания Lync Server 2013 включает в себя проверку на наличие проблем с подключениями, службами, ресурсами сервера и системными ресурсами.</span><span class="sxs-lookup"><span data-stu-id="dff70-106">Monitoring the Lync Server 2013 deployment involves checking for issues with connections, services, server resources, and system resources.</span></span> <span data-ttu-id="dff70-107">Операционные системы Windows Server вместе с System Center Operations Manager и Lync Server предоставляют множество средств и служб мониторинга, которые помогают обеспечить бесперебойную работу Организации Lync Server.</span><span class="sxs-lookup"><span data-stu-id="dff70-107">Windows Server operating systems, together with System Center Operations Manager, and Lync Server give you many monitoring tools and services to help ensure that the Lync Server organization is running smoothly.</span></span> <span data-ttu-id="dff70-108">Когда эти технологии реализуются вместе, администраторы могут получать оповещения при возникновении проблем или до них.</span><span class="sxs-lookup"><span data-stu-id="dff70-108">When these technologies are implemented together, administrators will be able to receive alerts when or before issues occur.</span></span>

<span data-ttu-id="dff70-109">Основные преимущества ежедневного наблюдения:</span><span class="sxs-lookup"><span data-stu-id="dff70-109">The key advantages to daily monitoring are as follows:</span></span>

  - <span data-ttu-id="dff70-110">Соблюдение требований к производительности и доступности определенного соглашения об уровне обслуживания.</span><span class="sxs-lookup"><span data-stu-id="dff70-110">Meeting the performance and availability requirements of defined SLAs.</span></span>

  - <span data-ttu-id="dff70-111">Выполнение определенных административных задач, таких как ежедневные операции резервного копирования и проверка работоспособности сервера, завершено успешно.</span><span class="sxs-lookup"><span data-stu-id="dff70-111">Successfully completing specific administrative tasks, such as daily backup operations, and checking server health.</span></span>

  - <span data-ttu-id="dff70-112">Обнаружение и устранение проблем, таких как узкие места в производительности сервера, или потребность в дополнительных ресурсах, прежде чем они повлияют на производительность.</span><span class="sxs-lookup"><span data-stu-id="dff70-112">Detecting and addressing issues, such as bottlenecks in the server performance, or need for additional resources before they affect productivity.</span></span>

<span data-ttu-id="dff70-113">Задачи ежедневного обслуживания помогают административной группе определять или устанавливать критерии или базовые показатели для нормальных системных операций в Организации, а также для обнаружения ненормальных действий.</span><span class="sxs-lookup"><span data-stu-id="dff70-113">Daily maintenance tasks help the administrative team to define or establish a criteria or baseline for normal systems operations within the organization, and to detect any abnormal activity.</span></span> <span data-ttu-id="dff70-114">Важно реализовать эти задачи ежедневного обслуживания, чтобы административная команда могла записывать и поддерживать данные о инфраструктуре Lync Server 2013, такие как уровни использования, возможные узкие места производительности и административные изменения.</span><span class="sxs-lookup"><span data-stu-id="dff70-114">It is important to implement these daily maintenance tasks so that the administrative team can capture and maintain data about the Lync Server 2013 infrastructure, such as usage levels, possible performance bottlenecks, and administrative changes.</span></span>

<span data-ttu-id="dff70-115">Чтобы помочь организовать производительность ежедневных задач, используйте [Контрольный список ежедневных задач](lync-server-2013-operations-checklists.md).</span><span class="sxs-lookup"><span data-stu-id="dff70-115">To help organize the performance of daily tasks, use the [Daily task checklist](lync-server-2013-operations-checklists.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="dff70-116">См. также</span><span class="sxs-lookup"><span data-stu-id="dff70-116">See Also</span></span>


[<span data-ttu-id="dff70-117">Контрольный список ежедневных задач</span><span class="sxs-lookup"><span data-stu-id="dff70-117">Daily task checklist</span></span>](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

