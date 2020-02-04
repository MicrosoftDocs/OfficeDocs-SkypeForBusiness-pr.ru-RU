---
title: 'Lync Server 2013: отработка отказа с использованием зеркальной базы данных'
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
ms.openlocfilehash: 822a7a2fa13ce444bbaf590ee0d8ba2144debcc7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756153"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-a-mirrored-database-in-lync-server-2013"></a>Отработка отказа с использованием зеркальной базы данных в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2014-03-14_

Если вы настроили серверную базу данных для использования синхронизированного отражения с следящим сервером, переход на другой ресурс выполняется автоматически. Если вы настроили синхронизацию зеркального отображения без следящего сервера, вы можете использовать следующие процедуры для перемещения по резервной копии и восстановления базы данных. Вы также можете использовать эти процедуры для перемещения по резервной конфигурации вручную и восстановления баз данных, даже если вы настроили следящий сервер.

<div>

## <a name="to-fail-over-your-back-end-database"></a>Переключение на серверную базу данных

1.  Прежде чем переходить, определите, какая серверная база данных является участником и что является зеркалом, введя следующий командлет:
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType User

2.  Если хранилище Central Management размещено в этом пуле, введите следующий командлет, чтобы определить, какой из них является основным и зеркалом для центрального хранилища.
    
        Get-CsDatabaseMirrorState -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt

3.  Выполнение отработки отказа базы данных пользователей.
    
      - Если основной сервер завершился сбоем и вы перейдете на зеркало, введите:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal mirror -Verbose
    
      - Если зеркало завершилось сбоем и вы перейдете на основной, введите:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType User -NewPrincipal primary -Verbose

4.  Если в пуле размещается Центральный сервер управления, выполните отработку отказа центрального хранилища управления.
    
      - Если основной сервер завершился сбоем и вы перейдете на зеркало, введите:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal mirror -Verbose
    
      - Если зеркало завершилось сбоем и вы перейдете на основной, введите:
        
            Invoke-CsDatabaseFailover -PoolFqdn <poolFQDN> -DatabaseType CentralMgmt -NewPrincipal primary -Verbose

</div>

</div>

<span> </span>

</div>

</div>

</div>

