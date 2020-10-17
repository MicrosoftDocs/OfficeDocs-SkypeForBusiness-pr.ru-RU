---
title: Проверка подключения между внутренними и пограничными серверами
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Verify connectivity between internal servers and Edge Servers
ms:assetid: 219f706e-2b8a-46c5-b394-c384240eef50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398292(v=OCS.15)
ms:contentKeyID: 48183602
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1a170ac21c89bd405ad0406830c00feabbde5434
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518656"
---
# <a name="verify-connectivity-between-internal-servers-and-edge-servers-in-lync-server-2013"></a><span data-ttu-id="3dcf3-102">Проверка подключения между внутренними и пограничными серверами в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3dcf3-102">Verify connectivity between internal servers and Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3dcf3-103">_**Последнее изменение темы:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="3dcf3-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="3dcf3-104">В Lync Server 2013 был доступен отдельный мастер проверки для проверки связи между пограничными серверами и внутренними серверами.</span><span class="sxs-lookup"><span data-stu-id="3dcf3-104">In Lync Server 2013, a separate validation wizard was available to help validate connectivity between Edge Servers and internal servers.</span></span> <span data-ttu-id="3dcf3-105">При установке пограничных серверов в Lync Server 2013 проверка подключения выполняется автоматически.</span><span class="sxs-lookup"><span data-stu-id="3dcf3-105">In Lync Server 2013 validation of connectivity is done automatically when you install your Edge Servers.</span></span>

<span data-ttu-id="3dcf3-106">Можно проверить репликацию сведений о конфигурации на пограничный сервер, выполнив командлет Windows PowerShell **Get-CsManagementStoreReplicationStatus** на внутреннем компьютере, на котором размещается центральное хранилище управления (или на любом присоединенном к домену компьютере, на котором установлен компонент Lync Server 2013 Core Components (OcsCore.msi).</span><span class="sxs-lookup"><span data-stu-id="3dcf3-106">You can validate the replication of configuration information to the edge by running the Windows PowerShell **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located (or any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span> <span data-ttu-id="3dcf3-107">В начальных результатах для репликации может быть указано состояние "False" вместо "True".</span><span class="sxs-lookup"><span data-stu-id="3dcf3-107">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="3dcf3-108">В этом случае выполните командлет **Invoke-CsManagementStoreReplication** и дождитесь завершения репликации перед повторным выполнением **Get-CsManagementStoreReplicationStatus**.</span><span class="sxs-lookup"><span data-stu-id="3dcf3-108">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

<span data-ttu-id="3dcf3-109">Можно проверить подключение внешних пользователей отдельно, в том числе с помощью анализатора удаленных подключений Office Communications Server.</span><span class="sxs-lookup"><span data-stu-id="3dcf3-109">You can verify external user connectivity separately, including using the Office Communications Server Remote Connectivity Analyzer to verify remote user connectivity.</span></span> <span data-ttu-id="3dcf3-110">Дополнительные сведения см. [в статье Проверка подключения для внешних пользователей в Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span><span class="sxs-lookup"><span data-stu-id="3dcf3-110">For details, see [Verify connectivity for external users in Lync Server 2013](lync-server-2013-verify-connectivity-for-external-users.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

