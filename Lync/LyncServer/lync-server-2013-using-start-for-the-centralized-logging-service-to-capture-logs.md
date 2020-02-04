---
title: Использование команды "Запуск" для централизованной службы ведения журналов для захвата журналов
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Start for the Centralized Logging Service to capture logs
ms:assetid: 0512b9ce-7f5b-48eb-a79e-f3498bacf2de
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687958(v=OCS.15)
ms:contentKeyID: 49733543
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75090036b7120c8af7cda132c26d5b4fb02d3dab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743999"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-start-for-the-centralized-logging-service-to-capture-logs-in-lync-server-2013"></a>Использование команды Start для централизованной службы ведения журналов для захвата журналов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

Для сбора журналов трассировки с помощью централизованной службы ведения журналов вы можете выполнить команду для начала ведения журнала на одном или нескольких компьютерах и пулах. Кроме того, вы можете настроить параметры, определяющие, какие компьютеры или пулы, какие сценарии необходимо выполнить (например, AlwaysOn, другой предопределенный сценарий или созданный вами сценарий), какие компоненты Lync Server (например, S4, Сипстакк) нужно отслеживать.

To capture the right information, you need to make sure you use the right scenario to collect information that is relevant to the problem. В централизованной службе ведения журналов сценарий — это концепция, с помощью которой можно выполнять ведение журнала на основе коллекции серверных компонентов, уровней ведения журнала и флагов, что значительно сложнее, чем определять эти элементы отдельно для каждого сервера. You define and specify a scenario to run and the scenario is run consistently across all servers and pools in the scope of the infrastructure.

Сценарий по умолчанию называется **AlwaysOn**. Сценарий AlwaysOn, в соответствии со своим названием, предназначен для постоянного выполнения. Сценарий AlwaysOn собирает данные на уровне Info (обратите внимание, что помимо информационных сообщений при ведении журнала на уровне Info также регистрируются сообщения Fatal (неустранимо), Error (ошибка) и Warning (предупреждение)) для многих из наиболее типичных серверных компонентов. AlwaysOn собирает сведения до, во время и после возникновения проблемы. Это резко отличается от поведения предыдущих средств ведения журнала, таких как OCSLogger. OCSLogger запускается уже после появления проблемы, что затрудняет поиск и устранение неисправностей, так как данные собираются как реакция на событие, а не упреждающе. Если AlwaysOn не содержит данных, нужных для определения проблемного компонента, и не указывает направление действий для исправления проблемы (что, скорее всего, связано с недостаточной шириной и глубиной поставщиков в AlwaysOn), будет указан разумный уровень данных для определения дальнейших действий, таких как создание нового сценария, сбор других данных, выполнение другого поиска для сбора более подробных сведений и т. д.

Служба централизованного ведения журналов предлагает два способа выполнения команд. Использование Windows PowerShell в среде Lync Server Management Shell заключается на несколько разделов. Возможность использовать множество сложных конфигураций и команд — это использование Windows PowerShell для централизованного ведения журнала. Поскольку Windows PowerShell с помощью командной консоли Lync Server Management Shell используется практически повсеместно для всех функций в Lync Server, обсуждаются только команды Windows PowerShell.

<div>


> [!NOTE]
> Если вы решили использовать набор команд с ограниченными возможностями в командной строке, вы можете получить помощь по работе с Клсконтроллер. exe, <CODE>ClsController.exe</CODE>введя текст. По умолчанию <STRONG>клсконтроллер. exe</STRONG> устанавливается в каталог C:\Program Files\Microsoft Lync Server 2013 \ клсажент.



</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-basic-commands"></a>Запуск команды Start-Ксклслоггинг с Windows PowerShell с помощью основных команд

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Начните ведение журнала с помощью централизованной службы ведения журналов, введя следующее:
    
        Start-CsClsLogging -Scenario <name of scenario>
    
    Например для запуска сценария **AlwaysOn** введите:
    
        Start-CsClsLogging -Scenario AlwaysOn
    
    <div>
    

    > [!NOTE]
    > У сценария AlwaysOn нет длительности по умолчанию. Этот сценарий будет выполняться, пока он не будет явно остановлен с помощью командлета <STRONG>Stop-CsClsLogging</STRONG>. Подробные сведения см. в статье <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-CsClsLogging</A>. Для всех остальных сценариев длительность по умолчанию составляет 4 часа.

    
    </div>

3.  Для выполнения команды нажмите клавишу ВВОД.
    
    <div>
    

    > [!NOTE]
    > Для выполнения команд и возвращения состояния от компьютеров среды может потребоваться некоторое небольшое время (от 30 до 60 секунд).

    
    </div>
    
    ![Запуск Start-CsClsLogging.](images/JJ687958.c5be7413-8cef-4de7-9712-944d20cc2fa4(OCS.15).jpg "Запуск Start-CsClsLogging.")

4.  Чтобы выполнить другой сценарий, используйте командлет **Start-CsClsLogging** с именем выполняемого дополнительного сценария (например, сценария **Authentication**):
    
        Start-CsClsLogging -Scenario Authentication
    
    <div>
    

    > [!IMPORTANT]
    > В любой момент времени на любом конкретном компьютере может работать не более двух сценариев. Если область применения команды является глобальной, этот сценарий или сценарии будут выполняться на всех компьютерах среды. Для запуска третьего сценария необходимо остановить ведение журнала для области применения (компьютер, пул, сайт, глобальная), в которой нужно запустить новый сценарий. Если сценарии запущены в глобальной области применения, можно остановить ведение журнала в одном или обоих сценариях для одного или нескольких компьютеров и пулов. Подробнее об управлении тем, какие сценарии выполняются, можно узнать <A href="lync-server-2013-using-stop-for-the-centralized-logging-service.md">в разделе Использование функции "остановить" для централизованной службы ведения журналов в Lync Server 2013</A> и <A href="https://technet.microsoft.com/en-us/library/JJ619180(v=OCS.15)">Stop-ксклслоггинг</A>.

    
    </div>

</div>

<div>

## <a name="to-run-start-csclslogging-with-windows-powershell-using-advanced-commands"></a>Запуск команды Start-Ксклслоггинг с Windows PowerShell с помощью расширенных команд

1.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

2.  Для управления командами ведения журнала доступны дополнительные параметры. Можно использовать параметр – Duration, чтобы задать длительность времени выполнения сценария. Также можно с помощью параметра – Computers определить разделяемый запятыми список полных доменных имен компьютеров, а с помощью параметра – Pools определить разделяемый запятыми список полных доменных имен пулов, на которых нужно вести журнал.
    
    Пусть нужно запустить сеанс ведения журнала с помощью сценария *UserReplicator* для пула "pool01.contoso.net". При этом длительность сеанса ведения журнала определяется равной 8 часам. Для этого введите следующую команду:
    
        Start-CsClsLogging -Scenario UserReplicator -Duration 8:00 -Pools "pool01.contoso.net"
    
    При успешном выполнении этого сценария возвращается результат, подобный следующему:
    
    ![Запуск Start-CsClsLogging.](images/JJ687958.399f0c2e-c08c-40ab-b6c6-381dddc12fe9(OCS.15).jpg "Запуск Start-CsClsLogging.")
    
    Обратите внимание, что в этом примере выполняются сценарий AlwaysOn и сценарий UserReplicator.

</div>

<div>

## <a name="see-also"></a>См. также


[Общие сведения об централизованной службе ведения журналов в Lync Server 2013](lync-server-2013-overview-of-the-centralized-logging-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

