---
title: 'Lync Server 2013: развертывание сопоставленных пулов переднего плана для аварийного восстановления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78c0d6b266f6401c9ba48bfe38ee54b7b4281717
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a>Развертывание сопоставленных пулов переднего плана для аварийного восстановления в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

Топологию аварийного восстановления для сопряженных пулов переднего плана можно легко развернуть с помощью построителя топологии.

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a>Развертывание пары интерфейсных пулов

1.  Если вы еще не определили пулы, используйте построитель топологии для создания пулов.

2.  В построителе топологии щелкните правой кнопкой мыши один из двух пулов и выберите команду **изменить свойства**.

3.  Щелкните элемент **Устойчивость** на левой панели и выберите **Связанный резервный пул** на правой панели.

4.  В расположенном ниже поле **Связанный резервный пул** выберите пул, который вы хотите связать с данным пулом. Для выбора будут доступны только существующие пулы, которые еще не связаны с другим пулом.
    
    ![36080581-db76-497d-bf9e-f02b39574d0e] (images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581-db76-497d-bf9e-f02b39574d0e")  

5.  Выберите **Автоматическая обработка отказов и восстановление после отказа для голосовой связи** и нажмите кнопку **ОК**.
    
    Теперь при просмотре сведений о данном пуле связанный с ним пул отображается на правой панели в области **Устойчивость**. 

6.  Опубликуйте топологию с помощью построителя топологии.

7.  Если два эти пула еще не были развернуты, разверните их для завершения настройки. Вы можете пропустить два последних действия данной процедуры.
    
    Однако если на момент определения связанного отношения пулы были уже развернуты, следует выполнить два последних действия.

8.  Выполните следующую команду на каждом сервере переднего плана в обоих пулах:
    
        <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    
    Это позволяет настроить остальные службы, необходимые для правильной работы резервного сопряжения.

9.  В командной строке оболочки Lync Server Management Shell выполните указанные ниже действия.
    
        Start-CsWindowsService -Name LYNCBACKUP

10. Выполните принудительную синхронизацию данных о пользователях и конференциях между двумя пулами с помощью следующих командлетов:
    
       ```
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    Синхронизация данных может занять некоторое время. Можно использовать следующие командлеты для проверки состояния. Убедитесь, что для обоих направлений состояние является стационарным.
    
       ```
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> Параметры <STRONG>автоматического перехода на другой ресурс и восстановление при сбое для голосовой связи</STRONG> , а также соответствующие интервалы времени в построителе топологии применяются только к функциям устойчивости голоса, которые появились в Lync Server 2010. Selecting this option does not imply that the pool failover discussed in this document is automatic. Pool failover and failback always require an administrator to manually invoke the failover and failback cmdlets, respectively.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

