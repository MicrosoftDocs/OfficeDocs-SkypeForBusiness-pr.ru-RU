---
title: 'Lync Server 2013: отработка отказа для зеркальной базы данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over a mirrored database
ms:assetid: 70185476-e3d4-440a-9316-fa24b226343e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204991(v=OCS.15)
ms:contentKeyID: 48184450
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24aa85ea7dfdd76b20af30954ea2480fba2f21f5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204285"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>Отработка отказа для зеркальной базы данных в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-03-14_

Если вы настроили для серверной базы данных синхронизированное зеркальное отображение с ресурсом-свидетелем, отработка отказа выполняется автоматически. Если вы настроили синхронизированное зеркальное отображение без ресурса-свидетеля, то чтобы обеспечить отработку отказа, можно воспользоваться следующими процедурами. С их помощью можно также выполнить отработку отказа баз данных вручную в том случае, если ресурс-свидетель настроен.

<div>

## <a name="to-fail-over-your-back-end-database"></a>Отработка отказа серверной базы данных

1.  Перед отработкой отказа определите, какая база данных является основной, а какая — зеркальной, выполнив следующий командлет.
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  Если центральное хранилище управления размещено в этом пуле, введите следующий командлет, чтобы определить, какой экземпляр является субъектом и зеркалом для центрального хранилища управления:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  Выполните отработку отказа базы данных пользователей.
    
      - Если произошел отказ основной базы данных и необходимо переключиться на зеркальную, введите следующую команду.
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - Если произошел отказ зеркальной базы данных и необходимо переключиться на основную, введите следующую команду.
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  Если в пуле размещается Центральный сервер управления, выполните отработку отказа центрального хранилища управления.
    
      - Если произошел отказ основной базы данных и необходимо переключиться на зеркальную, введите следующую команду.
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - Если произошел отказ зеркальной базы данных и необходимо переключиться на основную, введите следующую команду.
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

