---
title: Проверка параметров конфигурации
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 51c2d1d9-63f7-43ab-88ca-b8913da7cede
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204885(v=OCS.15)
ms:contentKeyID: 48184111
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5055f9ce77c5f1ad8b717af50ea621f37392ce0d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147912"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="80676-102">Проверка параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="80676-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80676-103">_**Последнее изменение темы:** 2012-09-06_</span><span class="sxs-lookup"><span data-stu-id="80676-103">_**Topic Last Modified:** 2012-09-06_</span></span>

<span data-ttu-id="80676-104">Можно проверить репликацию сведений о конфигурации на пограничный сервер, выполнив командлет Lync Server 2013 **Get-CsManagementStoreReplicationStatus** на внутреннем компьютере, на котором расположено центральное хранилище управления, или на любом компьютере, присоединенном к домену, на котором установлен основной компонент lync Server 2013 (OcsCore. msi).</span><span class="sxs-lookup"><span data-stu-id="80676-104">You can validate the replication of configuration information to the Edge server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located, or on any domain joined computer on which Lync Server 2013 Core Components (OcsCore.msi) is installed.</span></span>

<span data-ttu-id="80676-105">В начальных результатах для репликации может быть указано состояние "False" вместо "True".</span><span class="sxs-lookup"><span data-stu-id="80676-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="80676-106">В этом случае запустите командлет **Invoke-CsManagementStoreReplication** и дайте некоторое время для завершения репликации, прежде чем повторно запускать командлет **Get-CsManagementStoreReplicationStatus**.</span><span class="sxs-lookup"><span data-stu-id="80676-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

