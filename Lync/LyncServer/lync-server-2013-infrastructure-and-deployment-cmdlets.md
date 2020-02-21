---
title: 'Lync Server 2013: командлеты инфраструктуры и развертывания'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Infrastructure and deployment cmdlets
ms:assetid: 0a6e872a-9f70-4f23-a4a5-8820dbf55370
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398153(v=OCS.15)
ms:contentKeyID: 48183364
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f0aa515e290e6000564fe8eeaae5aaeb381284d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42204295"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="infrastructure-and-deployment-cmdlets-in-lync-server-2013"></a>Командлеты инфраструктуры и развертывания в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-09_

Командлеты инфраструктуры и развертывания, включенные в Microsoft Lync Server 2013, могут быть полезны при первоначальной установке и развертывании продукта; После развертывания Lync Server эти командлеты можно использовать для выполнения таких действий, как проверка правильности работы компонентов. Управление параметрами репликации; Резервное копирование и восстановление топологии, политик и параметров конфигурации Lync Server.

<div>

## <a name="infrastructure-and-deployment-cmdlets"></a>Командлеты инфраструктуры и развертывания

Администраторам редко требуется непосредственно вызывать большое количество командлетов инфраструктуры и развертывания. Это связано с тем, что при запуске программы установки или построителя топологий автоматически вызываются эти командлеты. (Одно из них может быть командлетом **Export-CsConfiguration** , которое позволяет создать резервную копию топологии Lync Server, политик и параметров конфигурации). Тем не менее, и при необходимости командлеты инфраструктуры и развертывания также можно запускать из командной консоли Lync Server или из скрипта; Использование сценария позволяет автоматизировать некоторые задачи. Ниже приведен список командлетов, которые относятся непосредственно к инфраструктуре и развертыванию:

**[Командлеты Active Directory в Lync Server 2013](lync-server-2013-active-directory-cmdlets.md)**

  - <span></span>  
    [Disable — CsAdDomain](https://technet.microsoft.com/library/Gg398785(v=OCS.15))

  - <span></span>  
    [Enable — CsAdDomain](https://technet.microsoft.com/library/Gg412764(v=OCS.15))

  - <span></span>  
    [Get — CsAdDomain](https://technet.microsoft.com/library/Gg398453(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable — CsAdForest](https://technet.microsoft.com/library/Gg398122(v=OCS.15))

  - <span></span>  
    [Enable — CsAdForest](https://technet.microsoft.com/library/Gg425713(v=OCS.15))

  - <span></span>  
    [Get — CsAdForest](https://technet.microsoft.com/library/Gg412995(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsAdServerSchema](https://technet.microsoft.com/library/Gg413070(v=OCS.15))

  - <span></span>  
    [Install — CsAdServerSchema](https://technet.microsoft.com/library/Gg398681(v=OCS.15))

**[Командлеты репликации в Lync Server 2013](lync-server-2013-replication-cmdlets.md)**

  - <span></span>  
    [Debug — Ксинтерпулрепликатион](https://technet.microsoft.com/library/JJ619185(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Invoke — CsManagementStoreReplication](https://technet.microsoft.com/library/Gg413060(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsManagementStoreReplicationStatus](https://technet.microsoft.com/library/Gg399052(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable — CsReplica](https://technet.microsoft.com/library/Gg425965(v=OCS.15))

  - <span></span>  
    [Test-CsReplica](https://technet.microsoft.com/library/JJ205289(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398548(v=OCS.15))

  - <span></span>  
    [New — CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg399059(v=OCS.15))

  - <span></span>  
    [Remove — CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg425738(v=OCS.15))

  - <span></span>  
    [Set — CsUserReplicatorConfiguration](https://technet.microsoft.com/library/Gg398540(v=OCS.15))

**[Командлеты топологии ЖН Lync Server 2013](lync-server-2013-topology-cmdlets.md)**

  - <span></span>  
    [Get — CsPool](https://technet.microsoft.com/library/Gg398992(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsSite](https://technet.microsoft.com/library/Gg398185(v=OCS.15))

  - <span></span>  
    [Set — CsSite](https://technet.microsoft.com/library/Gg413023(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Enable — CsTopology](https://technet.microsoft.com/library/Gg398398(v=OCS.15))

  - <span></span>  
    [Get — CsTopology](https://technet.microsoft.com/library/Gg412824(v=OCS.15))

  - <span></span>  
    [Publish — CsTopology](https://technet.microsoft.com/library/Gg398953(v=OCS.15))

  - <span></span>  
    [Test-CsTopology](https://technet.microsoft.com/library/Gg398127(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Export — CsConfiguration](https://technet.microsoft.com/library/Gg398627(v=OCS.15))

  - <span></span>  
    [Import — CsConfiguration](https://technet.microsoft.com/library/Gg398800(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — Кссерверверсион](https://technet.microsoft.com/library/Gg398470(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Disable — CsComputer](https://technet.microsoft.com/library/Gg399023(v=OCS.15))

  - <span></span>  
    [Enable — CsComputer](https://technet.microsoft.com/library/Gg412815(v=OCS.15))

  - <span></span>  
    [Get — CsComputer](https://technet.microsoft.com/library/Gg425959(v=OCS.15))

  - <span></span>  
    [Test-CsComputer](https://technet.microsoft.com/library/Gg398162(v=OCS.15))

<!-- end list -->

  - <span></span>  
    [Get — CsNetworkInterface](https://technet.microsoft.com/library/Gg398121(v=OCS.15))

**[Командлеты резервного копирования и высокой доступности в Lync Server 2013](lync-server-2013-backup-and-high-availability-cmdlets.md)**

  - [Get — CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205087(v=OCS.15))

  - [Remove — CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ204903(v=OCS.15))

  - [Set — CsBackupServiceConfiguration](https://technet.microsoft.com/library/JJ205006(v=OCS.15))

<!-- end list -->

  - [Get — Ксбаккупсервицестатус](https://technet.microsoft.com/library/JJ205032(v=OCS.15))

<!-- end list -->

  - [Invoke — Ксбаккупсервицесинк](https://technet.microsoft.com/library/JJ205374(v=OCS.15))

<!-- end list -->

  - [Debug — CsIntraPoolReplication](https://technet.microsoft.com/library/JJ205103(v=OCS.15))

<!-- end list -->

  - [Backup — CsPool](https://technet.microsoft.com/library/JJ204955(v=OCS.15))

<!-- end list -->

  - [Get — CsPoolBackupRelationship](https://technet.microsoft.com/library/JJ204745(v=OCS.15))

<!-- end list -->

  - [Get — CsPoolFabricState](https://technet.microsoft.com/library/JJ619188(v=OCS.15))

<!-- end list -->

  - [Invoke — CsPoolFailBack](https://technet.microsoft.com/library/JJ204873(v=OCS.15))

<!-- end list -->

  - [Invoke — CsPoolFailOver](https://technet.microsoft.com/library/JJ205189(v=OCS.15))

<!-- end list -->

  - [Get — CsPoolUpgradeReadinessState](https://technet.microsoft.com/library/JJ204689(v=OCS.15))

<!-- end list -->

  - [Invoke — Кссторажесервицефлуш](https://technet.microsoft.com/library/JJ619175(v=OCS.15))

<!-- end list -->

  - [Sync — CsUserData](https://technet.microsoft.com/library/JJ205242(v=OCS.15))

<!-- end list -->

  - [Remove — Ксусерсторебаккупдата](https://technet.microsoft.com/library/JJ205003(v=OCS.15))

</div>

<div>

## <a name="see-also"></a>См. также


[Блог Lync Server PowerShell](https://go.microsoft.com/fwlink/p/?linkid=203150)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

