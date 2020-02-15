---
title: 'Lync Server 2013: использование Stop для централизованной службы ведения журналов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Stop for the Centralized Logging Service
ms:assetid: 09ac093e-8f30-4874-84b4-12548ac8c898
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687964(v=OCS.15)
ms:contentKeyID: 49733549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1273d961c52b2b02ff90c83dc8f677f57196f2bb
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007528"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a>Использование Stop для централизованной службы ведения журналов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Остановить текущий работающий сеанс ведения журнала можно с помощью командлета Stop-CsClsLogging. Обычно ситуации, когда нужно остановить сеанс ведения журнала, возникают достаточно редко. Например, поиск в журналах и изменение конфигураций можно выполнять без обязательной предварительной остановки ведения журнала. Если выполняются два сценария, например AlwaysOn и UserReplicator, и нужно собирать сведения, связанные с проверкой подлинности (сценарий Authentication), понадобится остановить один из других сценариев (на глобальном уровне, уровне сайта, пула или компьютера), прежде чем можно будет запустить сценарий Authentication. Подробные сведения см. в статье [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).

<div>


> [!NOTE]  
> При определении сценариев, которые можно выполнять для данного развертывания, пула или компьютера, нужно помнить, что можно выполнять не более двух сценариев <STRONG>на компьютер</STRONG>. При ведении журнала действий для пула следует считать пул единым объектом. В большинстве случаев бессмысленно выполнять разные сценарии на каждом компьютере пула. Стоит взглянуть на проблему, для которой собираются данные, и поискать сценарий, который даст максимальный эффект для данного компьютера в общей среде. Например, если вы рассматриваете сценарий UserReplicator, в запуске UserReplicator на пограничном сервере или пограничном пуле было бы очень мало значений.<BR>Разобравшись в проблеме и оценив масштаб влияния, следует аккуратно выбрать, какие сценарии будут выполняться и на каких компьютерах и пулах. Хотя сценарий AlwaysOn имеет смысл для широкой области применения, так как он собирает данные для широкого множества поставщиков, определенные сценарии целесообразно применять только на конкретных компьютерах и пулах. Кроме того, следует соблюдать осторожность и не запускать сеанс ведения журнала случайным образом, не разобравшись сначала в эффективности данного сценария в конкретном случае. Использование неправильного сценария или сценария, не соответствующего задаче, либо запуск сценария в неправильной области применения (будь это глобальный уровень, уровень площадки, пула или компьютера), может привести к получению сомнительных и не слишком полезных данных — как если бы никакой сценарий вообще не запускался.



</div>

Для управления функциями централизованного ведения журналов с помощью Командная консоль Lync Server необходимо быть членом группы безопасности CsAdministrator или CsServerAdministrator с управлением доступом на основе ролей (RBAC) или настраиваемой роли RBAC, содержащей Любая из этих двух групп. Чтобы получить список всех ролей RBAC, которым назначен этот командлет (включая все самостоятельно созданные роли RBAC), выполните следующую команду в командной консоли Lync Server или в командной строке Windows PowerShell:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Пример:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Чтобы остановить запущенный в данный момент сеанс Службы централизованного ведения журнала

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Запросите службу централизованного ведения журналов, чтобы узнать, какие сценарии выполняются в данный момент, введя следующую команду:
    
        Show-CsClsLogging
    
    ![Консоль Windows PowerShell после вызова Show — Кскл](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Консоль Windows PowerShell после вызова Show — Кскл")
    
    Результатом выполнения Show-CsClsLogging являются сводные данные обо всех выполняемых сценариях и областях их выполнения. Подробные сведения см. в статье [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).

3.  Чтобы остановить выполняемый в данный момент сеанс ведения журнала, введите:
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    Пример:
    
        Stop-CsClsLogging -Scenario UserReplicator -Pools pool01.contoso.net
    
    Эта команда остановит ведение журнала с помощью сценария UserReplicatior для pool01.contoso.net.
    
    <div>
    

    > [!NOTE]  
    > Журналы, созданные в течение останавливаемого сеанса ведения журнала с помощью сценария UserReplicator, не удаляются. Журналы остаются доступными для выполнения поиска с помощью команды Search-CsClsLogging. Подробные сведения см. в статье <A href="https://docs.microsoft.com/powershell/module/skype/Search-CsClsLogging">Search-CsClsLogging</A>.

    
    </div>

Действуя в качестве команды-спутника для Start-CsClsLogging, командлет Stop-CsClsLogging завершает сеанс ведения журнала и сохраняет журналы, созданные в течение этого сеанса. Одновременно на данном компьютере может выполняться не более двух сценариев. Способ остановки одного сценария для сбора данных с помощью другого сценария является типовой задачей, часто выполняемой при устранении неполадок рабочих нагрузок.

</div>

<div>

## <a name="see-also"></a>См. также


[Использование Start для централизованной службы ведения журналов для захвата журналов в Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[Обзор централизованной службы ведения журналов в Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Show — CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[Start — CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[Stop — CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

