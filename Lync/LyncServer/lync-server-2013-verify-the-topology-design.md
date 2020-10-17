---
title: 'Lync Server 2013: Проверка структуры топологии'
description: 'Lync Server 2013: Проверка структуры топологии.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify the topology design
ms:assetid: c1b61814-239e-4101-aab0-de3db1d8793c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412951(v=OCS.15)
ms:contentKeyID: 48185311
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cb1e65343aacddbc11d3b909dfdff715503cab93
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560195"
---
# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="72810-103">Проверка структуры топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72810-103">Verify the topology design in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72810-104">_**Последнее изменение темы:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="72810-104">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="72810-105">В построителе топологий автоматически проверяется топология.</span><span class="sxs-lookup"><span data-stu-id="72810-105">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="72810-106">Любая ошибка топологии считается ошибкой проверки и обозначается значком ошибки проверки рядом с ролью сервера.</span><span class="sxs-lookup"><span data-stu-id="72810-106">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="72810-107">Важно также проверить, что топология правильно представляет топологию вашего развертывания.</span><span class="sxs-lookup"><span data-stu-id="72810-107">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="72810-108">Проверка топологии до публикации</span><span class="sxs-lookup"><span data-stu-id="72810-108">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="72810-109">Проверьте, что все простые URL-адреса настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="72810-109">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="72810-110">Убедитесь, что сервер на основе SQL Server подключен к сети и доступен компьютеру, на котором установлен построитель топологий, включая все необходимые правила брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="72810-110">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="72810-111">Проверьте, что файловое хранилище доступно и для него заданы необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="72810-111">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="72810-112">Проверьте, что в топологии заданы правильные роли сервера, удовлетворяющие требованиям развертывания.</span><span class="sxs-lookup"><span data-stu-id="72810-112">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="72810-113">Убедитесь, что серверы существуют в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="72810-113">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="72810-114">Это осуществляется автоматически, если серверы присоединены к домену.</span><span class="sxs-lookup"><span data-stu-id="72810-114">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="72810-115">Когда топология проверена и ошибки проверки отсутствуют, все должно быть готово к публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="72810-115">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="72810-116">Если имеются ошибки проверки, то перед публикацией топологии их необходимо исправить.</span><span class="sxs-lookup"><span data-stu-id="72810-116">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="72810-117">Сведения о публикации топологии приведены [в статье публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="72810-117">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

