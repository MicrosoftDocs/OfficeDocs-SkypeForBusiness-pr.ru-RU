---
title: Проверка репликации параметров конфигурации
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Validate replication of configuration settings
ms:assetid: 81a3c21d-b28a-4287-adac-11791e8db56d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205042(v=OCS.15)
ms:contentKeyID: 48184663
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698686dd217bf16457e4c3f4ebe6867566dcf49d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738579"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-replication-of-configuration-settings"></a><span data-ttu-id="60127-102">Проверка репликации параметров конфигурации</span><span class="sxs-lookup"><span data-stu-id="60127-102">Validate replication of configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="60127-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="60127-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="60127-104">Вы можете проверить репликацию сведений о конфигурации на пограничном сервере, запустив командлет Lync Server 2013 **Get-ксманажементсторерепликатионстатус** на внутреннем компьютере, на котором находится корневой центр управления, или на любом компьютере, подключенном к домену, на котором установлен компонент lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="60127-104">You can validate the replication of configuration information to the Edge Server by running the Lync Server 2013 **Get-CsManagementStoreReplicationStatus** cmdlet on the internal computer on which the Central Management store is located or any domain joined computer on which Lync Server 2013 Core Components is installed.</span></span>

<span data-ttu-id="60127-105">Начальные результаты могут содержать состояние "false", а не "истина" для репликации.</span><span class="sxs-lookup"><span data-stu-id="60127-105">Initial results may indicate the status as "False" instead of "True" for replication.</span></span> <span data-ttu-id="60127-106">Если это так, выполните командлет **Invoke-ксманажементсторерепликатион** и разрешите время завершения репликации, прежде чем запускать командлет **Get-ксманажементсторерепликатионстатус** еще раз.</span><span class="sxs-lookup"><span data-stu-id="60127-106">If so, run the **Invoke-CsManagementStoreReplication** cmdlet and allow time for the replication to complete before running the **Get-CsManagementStoreReplicationStatus** cmdlet again.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

