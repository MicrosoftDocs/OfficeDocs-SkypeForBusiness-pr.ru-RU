---
title: 'Lync Server 2013: требования к публикации топологии'
description: 'Lync Server 2013: требования к публикации топологии.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Requirements to publish a topology
ms:assetid: 841cdf5d-d884-414d-ab50-3bb681b622ed
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195733(v=OCS.15)
ms:contentKeyID: 48184688
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5699657e680b78587b8ba354e9dc538f2e280c56
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577865"
---
# <a name="requirements-to-publish-a-topology-in-lync-server-2013"></a><span data-ttu-id="18587-103">Требования к публикации топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18587-103">Requirements to publish a topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="18587-104">_**Последнее изменение темы:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="18587-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="18587-105">В этом разделе описываются требования к инфраструктуре и программному обеспечению, характерные для публикации топологии, независимо от того, использует ли построитель топологий или интерфейс командной строки командной консоли Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18587-105">This topic describes the infrastructure and software requirements that are specific to publishing a topology, whether by using Topology Builder or the Lync Server 2013 Management Shell command-line interface.</span></span> <span data-ttu-id="18587-106">Эти требования относятся к общим требованиям операционной системы, программного обеспечения и разрешений, которые применяются ко всем административным средствам Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="18587-106">These requirements are in addition to the general operating system, software, and permissions requirements applicable to all Lync Server 2013 administrative tools.</span></span> <span data-ttu-id="18587-107">Перед публикацией топологии убедитесь, что все требования к средствам администрирования соблюдены.</span><span class="sxs-lookup"><span data-stu-id="18587-107">Make sure that you satisfy all administrative tools requirements before you publish a topology.</span></span>

  - <span data-ttu-id="18587-108">Построитель топологий необходимо запускать на компьютере, присоединенном к тому же домену или лесу сервера Lync Server 2013, который вы создаете, чтобы действия по подготовке доменных служб Active Directory были выполнены, позволяя использовать средства администрирования на этом компьютере для успешной публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="18587-108">You must run Topology Builder on a computer that is joined to the same domain or forest of the Lync Server 2013 deployment you are creating so that Active Directory Domain Services preparation steps are already completed, enabling you to use the administrative tools on that computer to successfully publish your topology.</span></span>

  - <span data-ttu-id="18587-p102">Компьютеры, определенные в топологии, должны быть присоединены к домену, за исключением пограничных серверов, и AD DS. Однако компьютеры необязательно должны быть в сети при публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="18587-p102">The computers defined in the topology must be joined to the domain, except for Edge Servers, and in AD DS. However, the computers do not need to be online when you publish the topology.</span></span>

  - <span data-ttu-id="18587-111">Необходимо создать общий файловый ресурс для пула, который должен быть доступен для удаленных пользователей.</span><span class="sxs-lookup"><span data-stu-id="18587-111">The file share for the pool must be created and available to remote users.</span></span>

  - <span data-ttu-id="18587-112">Чтобы опубликовать пул переднего плана Enterprise Edition, сервер переднего плана, основанный на SQL Server, должен быть присоединен к домену, в котором развертываются серверы, в сети и настроены соответствующие правила брандмауэра, чтобы сделать его доступным удаленным пользователям.</span><span class="sxs-lookup"><span data-stu-id="18587-112">In order to publish an Enterprise Edition Front End pool, the SQL Server-based Back End Server must be joined to the domain in which you are deploying the servers, online, and configured with the appropriate firewall rules to make it available to remote users.</span></span> <span data-ttu-id="18587-113">Дополнительные сведения об указании исключений брандмауэра приведены [в статье Общие сведения о требованиях к брандмауэру для SQL Server с Lync server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="18587-113">For details about specifying firewall exceptions, see [Understanding firewall requirements for SQL Server with Lync Server 2013](lync-server-2013-understanding-firewall-requirements-for-sql-server.md).</span></span> <span data-ttu-id="18587-114">Дополнительные сведения о настройке SQL Server можно найти в статье [Настройка SQL Server для Lync server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span><span class="sxs-lookup"><span data-stu-id="18587-114">For other details about configuring SQL Server, see [Configure SQL Server for Lync Server 2013](lync-server-2013-configure-sql-server-for-lync-server.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="18587-115">Сервер Standard Edition имеет размещенную базу данных, которая будет принимать опубликованную конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="18587-115">Standard Edition server has a collocated database that will accept the published configuration.</span></span> <span data-ttu-id="18587-116">Сначала необходимо запустить задачу " <STRONG>Подготовка первого сервера Standard Edition</STRONG> " в мастере развертывания Lync Server.</span><span class="sxs-lookup"><span data-stu-id="18587-116">You must first run the <STRONG>Prepare first Standard Edition server</STRONG> setup task in the Lync Server Deployment Wizard.</span></span>

    
    </div>

<div>

## <a name="see-also"></a><span data-ttu-id="18587-117">См. также</span><span class="sxs-lookup"><span data-stu-id="18587-117">See Also</span></span>


[<span data-ttu-id="18587-118">Публикация топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18587-118">Publish the topology in Lync Server 2013</span></span>](lync-server-2013-publish-the-topology.md)  
[<span data-ttu-id="18587-119">Делегирование разрешений на установку в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18587-119">Delegate setup permissions in Lync Server 2013</span></span>](lync-server-2013-delegate-setup-permissions.md)  


[<span data-ttu-id="18587-120">Требования к программному обеспечению для средств администрирования в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18587-120">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
[<span data-ttu-id="18587-121">Поддержка серверов и средств операционной системы в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18587-121">Server and tools operating system support in Lync Server 2013</span></span>](lync-server-2013-server-and-tools-operating-system-support.md)  


[<span data-ttu-id="18587-122">Права и разрешения администратора, необходимые для установки и администрирования Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="18587-122">Administrator rights and permissions required for setup and administration of Lync Server 2013</span></span>](lync-server-2013-administrator-rights-and-permissions-required-for-setup-and-administration.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

