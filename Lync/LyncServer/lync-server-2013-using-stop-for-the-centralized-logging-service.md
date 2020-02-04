---
title: 'Lync Server 2013: использование команды "остановить" для централизованной службы ведения журнала'
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
ms.openlocfilehash: 621d7c02530fea62b1601c1db755292c8f819a6e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-stop-for-the-centralized-logging-service-in-lync-server-2013"></a>Использование функции "остановить" для централизованной службы ведения журналов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Остановить текущий работающий сеанс ведения журнала можно с помощью командлета Stop-CsClsLogging. Обычно ситуации, когда нужно остановить сеанс ведения журнала, возникают достаточно редко. Например, поиск в журналах и изменение конфигураций можно выполнять без обязательной предварительной остановки ведения журнала. Если выполняются два сценария, например AlwaysOn и UserReplicator, и нужно собирать сведения, связанные с проверкой подлинности (сценарий Authentication), понадобится остановить один из других сценариев (на глобальном уровне, уровне сайта, пула или компьютера), прежде чем можно будет запустить сценарий Authentication. Подробные сведения см. в статье [Stop-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging).

<div>


> [!NOTE]  
> При определении сценариев, которые можно выполнять для определенного развертывания, пула или компьютера, необходимо помнить, что вы ограничены выполнение двух сценариев <STRONG>на компьютере</STRONG>. If you are logging activity on a pool, you should treat a pool as a single entity. In most cases, it would not make sense to run different scenarios on each computer in a pool. It does make sense to look at the problem that you are collecting data about and think about what scenario makes the most sense on a given computer in the overall deployment. Например, если вы просматриваете сценарий Усеррепликатор, то в процессе выполнения Усеррепликатор на пограничном сервере или пуле Edgeов было бы очень мало значений.<BR>Разобравшись в проблеме и оценив масштаб влияния, следует аккуратно выбрать, какие сценарии будут выполняться и на каких компьютерах и пулах. Хотя сценарий AlwaysOn имеет смысл для широкой области применения, так как он собирает данные для широкого множества поставщиков, определенные сценарии целесообразно применять только на конкретных компьютерах и пулах. Кроме того, следует соблюдать осторожность и не запускать сеанс ведения журнала случайным образом, не разобравшись сначала в эффективности данного сценария в конкретном случае. Использование неправильного сценария или сценария, не соответствующего задаче, либо запуск сценария в неправильной области применения (будь это глобальный уровень, уровень площадки, пула или компьютера), может привести к получению сомнительных и не слишком полезных данных — как если бы никакой сценарий вообще не запускался.



</div>

Для управления централизованными функциями ведения журналов с помощью командной консоли Lync Server вы должны быть членами либо группами безопасности Ксадминистратор или Кссерверадминистратор, либо настраиваемой роли RBAC, которая включает в себя Любая из этих двух групп. Чтобы возвратить список всех ролей RBAC, которым был назначен этот командлет (включая любые пользовательские роли RBAC, созданные пользователем), выполните следующую команду из командной консоли Lync Server Management Shell или Windows PowerShell.

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Lync Server 2013 cmdlet"}

Например:

    Get-CsAdminRole | Where-Object {$_.Cmdlets -match "Set-CsClsConfiguration"}

<div>

## <a name="to-stop-a-currently-running-centralized-logging-service-session"></a>Чтобы остановить запущенный в данный момент централизованный сеанс службы ведения журнала

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Запросите службу централизованного ведения журналов, чтобы узнать, какие сценарии в настоящее время выполняются, введя следующее:
    
        Show-CsClsLogging
    
    ![Консоль Windows PowerShell после вызова Show-CsCl](images/JJ687964.eb190c32-529c-4277-a731-52c47d22d8fa(OCS.15).jpg "Консоль Windows PowerShell после вызова Show-CsCl")
    
    Результатом выполнения Show-CsClsLogging являются сводные данные обо всех выполняемых сценариях и областях их выполнения. Подробные сведения см. в статье [Show-CsClsLogging](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging).

3.  Чтобы остановить выполняемый в данный момент сеанс ведения журнала, введите:
    
        Stop-CsClsLogging -Scenario <scenario name> -Computers <comma separated list of fully qualified computer names> -Pools <comma separated list of fully qualified pool names>
    
    Например:
    
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


[Использование команды Start для централизованной службы ведения журналов для захвата журналов в Lync Server 2013](lync-server-2013-using-start-for-the-centralized-logging-service-to-capture-logs.md)  


[Общие сведения об централизованной службе ведения журналов в Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  


[Show-Ксклслоггинг](https://docs.microsoft.com/powershell/module/skype/Show-CsClsLogging)  
[Start-Ксклслоггинг](https://docs.microsoft.com/powershell/module/skype/Start-CsClsLogging)  
[Остановить-Ксклслоггинг](https://docs.microsoft.com/powershell/module/skype/Stop-CsClsLogging)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

