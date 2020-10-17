---
title: 'Lync Server 2013: развертывание подключенных пулов переднего плана для аварийного восстановления'
description: 'Lync Server 2013: развертывание подключенных пулов переднего плана для аварийного восстановления.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying paired Front End pools for disaster recovery
ms:assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204773(v=OCS.15)
ms:contentKeyID: 48183727
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4846121f301d2bc7be1af9b58f0a0fef3f88e6d6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555905"
---
# <a name="deploying-paired-front-end-pools-for-disaster-recovery-in-lync-server-2013"></a>Развертывание подключенных пулов переднего плана для аварийного восстановления в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Топологию аварийного восстановления в связанных пулах переднего плана можно легко развернуть с помощью построителя топологий.

<div>

## <a name="to-deploy-a-pair-of-front-end-pools"></a>Развертывание пары интерфейсных пулов

1.  Если пулы новые и еще не определены, используйте построитель топологий для создания пулов.

2.  В построителе топологий щелкните правой кнопкой мыши один из двух пулов и выберите команду **изменить свойства**.

3.  Щелкните элемент **Resiliency** (Устойчивость) на левой панели и выберите **Associated Backup Pool** (Сопоставленный резервный пул) на правой панели.

4.  В расположенном ниже поле **Associated Backup Pool** (Сопоставленный резервный пул) выберите пул, который вы хотите связать с данным пулом. Для выбора будут доступны только существующие пулы, которые еще не связаны с другим пулом.
    
    ![36080581 — db76 — 497d — bf9e – f02b39574d0e](images/JJ204773.36080581-db76-497d-bf9e-f02b39574d0e(OCS.15).png "36080581 — db76 — 497d — bf9e – f02b39574d0e")  

5.  Выберите **Automatic failover and failback for Voice** (Автоматическая отработка отказа и восстановление размещения для голосовой связи) и нажмите кнопку **OK** (ОК).
    
    Теперь при просмотре сведений о данном пуле связанный с ним пул отображается на правой панели в области **Resiliency** (Устойчивость).

6.  Опубликуйте топологию с помощью построителя топологий.

7.  Если два эти пула еще не были развернуты, разверните их для завершения настройки. Вы можете пропустить два последних действия данной процедуры.
    
    Однако если на момент определения связанного отношения пулы были уже развернуты, следует выполнить два последних действия.

8.  Выполните следующую команду на каждом сервере переднего плана в обоих пулах:
    ```console
    <system drive>\Program Files\Microsoft Lync Server 2013\Deployment\Bootstrapper.exe 
    ```
    Это позволяет настроить остальные службы, необходимые для правильной работы резервного связывания.

9.  В командной строке Командная консоль Lync Server выполните следующие действия:
    ```powershell
    Start-CsWindowsService -Name LYNCBACKUP
    ```
10. Выполните принудительную синхронизацию данных о пользователях и конференциях между двумя пулами с помощью следующих командлетов:
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
       ```
    
    Синхронизация данных может занять некоторое время. Можно использовать следующие командлеты для проверки состояния. Убедитесь, что состояние в обоих направлениях находится в стабильном состоянии.
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
       ```
    
       ```powershell
        Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
       ```

<div class="">


> [!NOTE]  
> Параметры <STRONG>автоматической отработки отказа и восстановления размещения для голосовой связи</STRONG> , а также соответствующие интервалы времени в построителе топологий применяются только к функциям устойчивости голосовой связи, которые были представлены в Lync Server 2010. Выбор данного параметра не подразумевает, что отработка отказа пулом, описанная в настоящем документе, является автоматической. Отработка отказа и восстановление размещения пула всегда требуют от администратора ручного вызова соответствующих командлетов.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

