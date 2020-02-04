---
title: 'Lync Server 2013: проверка структуры топологии'
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
ms.openlocfilehash: 85266477df342c16ed69c0507813b905c608745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742149"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-the-topology-design-in-lync-server-2013"></a><span data-ttu-id="1c481-102">Проверка структуры топологии в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1c481-102">Verify the topology design in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1c481-103">_**Тема последнего изменения:** 2012-01-02_</span><span class="sxs-lookup"><span data-stu-id="1c481-103">_**Topic Last Modified:** 2012-01-02_</span></span>

<span data-ttu-id="1c481-104">Построитель топологии автоматически проверяет топологию.</span><span class="sxs-lookup"><span data-stu-id="1c481-104">Topology Builder automatically verifies the topology.</span></span> <span data-ttu-id="1c481-105">Любая ошибка топологии определяется как ошибка проверки, указанная значком ошибки проверки рядом с ролью сервера.</span><span class="sxs-lookup"><span data-stu-id="1c481-105">Any topology error is identified as a validation error, indicated by the validation error icon next to the server role.</span></span> <span data-ttu-id="1c481-106">Важно также убедиться, что топология правильно представляет топологию для развертывания.</span><span class="sxs-lookup"><span data-stu-id="1c481-106">It is important to also verify that the topology correctly represents the topology for your deployment.</span></span>

<div>

## <a name="to-verify-the-topology-prior-to-publication"></a><span data-ttu-id="1c481-107">Проверка топологии перед публикацией</span><span class="sxs-lookup"><span data-stu-id="1c481-107">To verify the topology prior to publication</span></span>

1.  <span data-ttu-id="1c481-108">Проверьте, что все простые URL-адреса настроены правильно.</span><span class="sxs-lookup"><span data-stu-id="1c481-108">Check that all simple URLs are configured correctly.</span></span>

2.  <span data-ttu-id="1c481-109">Проверьте, что сервер на основе SQL Server включен и доступен компьютеру, на котором установлен построитель топологий, включая все необходимые правила брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="1c481-109">Confirm that the SQL Server-based server is online and available to the computer where Topology Builder is installed, including any necessary firewall rules.</span></span>

3.  <span data-ttu-id="1c481-110">Убедитесь в том, что общий доступ к файлам доступен, и у него есть соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="1c481-110">Confirm that the file share is available and has the proper permissions defined.</span></span>

4.  <span data-ttu-id="1c481-111">Проверьте, что в топологии заданы правильные роли сервера, удовлетворяющие требованиям развертывания.</span><span class="sxs-lookup"><span data-stu-id="1c481-111">Confirm that the correct server roles that meet the deployment requirements are defined in the topology.</span></span>

5.  <span data-ttu-id="1c481-112">Убедитесь в том, что серверы находятся в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="1c481-112">Verify that the servers exist in Active Directory Domain Services.</span></span> <span data-ttu-id="1c481-113">Это происходит автоматически, если вы присоединили серверы к домену.</span><span class="sxs-lookup"><span data-stu-id="1c481-113">This will happen automatically if you have joined the servers to the domain.</span></span>

<span data-ttu-id="1c481-114">Когда топология проверена и ошибки проверки отсутствуют, все должно быть готово к публикации топологии.</span><span class="sxs-lookup"><span data-stu-id="1c481-114">When you have verified the topology and there are no validation errors, you should be ready to publish the topology.</span></span> <span data-ttu-id="1c481-115">Если обнаружены ошибки проверки, необходимо исправить эти значения, прежде чем можно будет опубликовать топологию.</span><span class="sxs-lookup"><span data-stu-id="1c481-115">If there are validation errors, you must correct these before you can publish the topology.</span></span> <span data-ttu-id="1c481-116">Подробнее о публикации топологии можно найти в разделе [Публикация топологии в Lync Server 2013](lync-server-2013-publish-the-topology.md).</span><span class="sxs-lookup"><span data-stu-id="1c481-116">For details about publishing your topology, see [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

