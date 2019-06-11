---
title: 'Lync Server 2013: создание или изменение очереди'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or modify a queue
ms:assetid: b9d6366a-839f-4651-a01d-9254546cadeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205207(v=OCS.15)
ms:contentKeyID: 48185247
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 96b6bc1e5f956b5b975e14f07a3c37f2802d1b39
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-queue-in-lync-server-2013"></a>Создание и изменение очереди в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Чтобы создать или изменить очередь, используйте одну из следующих процедур.

<div>

## <a name="to-use-lync-server-control-panel-to-create-or-modify-a-queue"></a>Создание и изменение очереди с помощью панели управления Lync Server

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.
    
    <div>
    

    > [!NOTE]  
    > Если вы являетесь одним из делегированных менеджеров группы ответа для управляемого рабочего процесса, вы можете создавать или изменять очереди группы ответа и назначать их рабочим процессам, которыми вы управляете.

    
    </div>

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Группы ответа**, затем щелкните **Очередь**.

4.  На странице **Очередь** выполните одно из следующих действий.
    
      - Чтобы создать очередь, нажмите кнопку **Создать**. В окне **Выбор службы** в поле поиска введите имя службы **ApplicationServer**, для которой необходимо добавить очередь, или часть имени. В полученном списке служб выберите требуемую службу и затем нажмите кнопку **ОК**.
    
      - Чтобы изменить существующую очередь, введите в поле поиска ее имя или его часть. В полученном списке очередей выберите требуемую очередь, нажмите кнопку **Изменить**, а затем кнопку **Подробнее**.

5.  В поле **Имя** введите понятное имя очереди.

6.  В поле **Описание** введите описание очереди.

7.  В поле **Группы** укажите группы, которые вы хотите назначить очереди. Выполните одно из следующих действий:
    
      - Чтобы добавить группу в очередь, нажмите кнопку **Выбрать**. В поле поиска **Выбор групп** введите имя группы агентов, которую необходимо назначить очереди, или часть имени, выберите требуемую группу агентов и нажмите кнопку **ОК**.
    
      - Чтобы удалить группу из очереди, в списке групп агентов выберите требуемую группу и нажмите кнопку **Удалить**.
    
      - Чтобы изменить порядок поиска агентов, в списке групп агентов выберите группу и нажмите стрелку вверх или стрелку вниз.
        
        <div>
        

        > [!NOTE]  
        > При поиске доступного агента в очереди сервер использует порядковый номер группы, т. е. сначала сервер выбирает первую группу в списке, затем вторую и т. д.

        
        </div>

8.  Чтобы задать максимальный период ожидания ответа агента (период удержания звонящего), установите флажок **Включить время ожидания очереди** и затем выполните следующие действия:
    
    1.  В поле **Время ожидания (сек)** укажите максимальное время ожидания ответа агента на звонок.
    
    2.  В **Действие вызова** выберите действие, выполняемое после завершения периода ожидания:
    
    <!-- end list -->
    
      - Чтобы разъединить звонок после завершения периода ожидания, установите переключатель **Отключить**.
    
      - Чтобы перенаправить звонок на голосовую почту, выберите команду\>@\< **Переслать на голосовую почту**, а затем в поле **адрес SIP** введите адрес голосовой почты в формате SIP\<: имя_пользователя\> DomainName (например, SIP: bob@contoso.com).
    
      - Чтобы перенаправить звонок на другой номер телефона, нажмите кнопку\>@\< **Переслать на номер телефона**, а затем в поле **адрес SIP** введите номер телефона в формате SIP:\<число имя_домена\> (для Например, sip:+14255550121@contoso.com).
    
      - Чтобы перенаправить звонок на другого пользователя, нажмите кнопку\>@\< **Переслать на адрес SIP**, а затем введите в поле **SIP Address** (универсальный код ресурса) URI для пользователя в\<формате SIP\>: username имя_домена.
    
      - Чтобы переадресовать звонок в другую очередь, установите переключатель **Переадресовывать в другую очередь**, затем выберите требуемую очередь.

9.  Чтобы указать максимальное число звонков в очереди, установите флажок **Разрешить переполнение очереди**, затем выполните следующие действия:
    
    1.  В поле **Максимальное число звонков** выберите максимальное число звонков, находящихся в очереди.
    
    2.  В поле **Переадресация звонка** выберите звонок, который будет переадресован при переполнении очереди (**Последний звонок** или **Первый звонок**).
    
    3.  В поле **Действие при звонке** выберите действие, выполняемое при превышении максимального числа звонков:
    
    <!-- end list -->
    
      - Чтобы разъединить звонок после завершения периода ожидания, установите переключатель **Отключить**.
    
      - Чтобы перенаправить звонок на голосовую почту, выберите команду\>@\< **Переслать на голосовую почту**, а затем в поле **адрес SIP** введите адрес голосовой почты в формате SIP\<: имя_пользователя\> DomainName (например, SIP: bob@contoso.com).
    
      - Чтобы перенаправить звонок на другой номер телефона, нажмите кнопку\>@\< **Переслать на номер телефона**, а затем в поле **адрес SIP** введите номер телефона в формате SIP:\<число имя_домена\> (для Например, sip:+14255550121@contoso.com).
    
      - Чтобы перенаправить звонок на другого пользователя, нажмите кнопку\>@\< **Переслать на адрес SIP**, а затем введите в поле **SIP Address** (универсальный код ресурса) URI для пользователя в\<формате SIP\>: username имя_домена.
    
      - Чтобы переадресовать звонок в другую очередь, установите переключатель **Переадресовывать в другую очередь**, затем выберите требуемую очередь.

10. Нажмите **Исполнить**.

</div>

<div>

## <a name="to-use-windows-powershell-to-create-or-modify-a-queue"></a>Использование Windows PowerShell для создания и изменения очереди

1.  Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.
    
    <div>
    

    > [!NOTE]  
    > Если вы являетесь одним из делегированных диспетчеров группы ответа для управляемого рабочего процесса, вы можете создавать группы агентов и очереди и назначать группы агентов очередям.

    
    </div>

2.  Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.

3.  Создайте сообщение, которое будет воспроизводиться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке выполните следующую команду.
    
        $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Например:
    
        "All agents are currently busy. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > Чтобы использовать аудиофайл для этой подсказки, воспользуйтесь командлетом <STRONG>Import-CsRgsAudioFile</STRONG>. Подробности можно найти в разделе <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-ксргсаудиофиле</A>.

    
    </div>

4.  Определите действие, которое должно выполняться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке введите следующую команду.
    
        $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > Дополнительные сведения о возможностях и их синтаксисе: <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-ксргскаллактион</A>.

    
    </div>
    
    Например:
    
        $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate

5.  Создайте сообщение, которое будет воспроизводиться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке выполните следующую команду.
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
    
    Например:
    
        $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
    
    <div>
    

    > [!NOTE]  
    > Чтобы использовать аудиофайл для этой подсказки, воспользуйтесь командлетом <STRONG>Import-CsRgsAudioFile</STRONG>. Подробности можно найти в разделе <A href="https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile">Import-ксргсаудиофиле</A>.

    
    </div>

6.  Определите действие, которое должно выполняться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке введите следующую команду.
    
        $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
    
    <div>
    

    > [!NOTE]  
    > Дополнительные сведения о возможностях и их синтаксисе: <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction">New-ксргскаллактион</A>.

    
    </div>
    
    Например:
    
        $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate

7.  Извлеките имя службы из службы группы ответа и назначьте его переменной. В командной строке выполните следующую команду:
    
        $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;

8.  Получите идентификатор группы агентов, которую нужно назначить очереди. В командной строке выполните следующую команду.
    
        $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
    
    <div>
    

    > [!NOTE]  
    > Дополнительные сведения о создании группы агента: <A href="https://docs.microsoft.com/powershell/module/skype/New-CsRgsAgentGroup">New-ксргсажентграуп</A>

    
    </div>

9.  Создайте очередь. В командной строке выполните следующую команду.
    
        $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
    
    Например:
    
        $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;

10. Убедитесь в том, что очередь создана. Выполните следующую команду.
    
        Get-CsRgsQueue -Name "Help Desk"

</div>

<div>

## <a name="see-also"></a>См. также


[New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/New-CsRgsQueue)  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Set-CsRgsQueue)  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/New-CsRgsPrompt)  
[New-Ксргскаллактион](https://docs.microsoft.com/powershell/module/skype/New-CsRgsCallAction)  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Get-CsRgsQueue)  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/Import-CsRgsAudioFile)  
[Remove-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/Remove-CsRgsQueue)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

