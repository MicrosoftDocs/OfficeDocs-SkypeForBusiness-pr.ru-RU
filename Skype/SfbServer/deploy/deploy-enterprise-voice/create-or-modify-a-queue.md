---
title: Создание и изменение очереди в Skype для бизнеса
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Создание или изменение очереди групп ответов в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 8cd306e849eeddd8a11b76604826084c0eb9b41d
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767872"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a>Создание и изменение очереди в Skype для бизнеса
 
Создание или изменение очереди групп ответов в Skype для бизнеса Server Enterprise.
  
Queues hold callers until an agent answers the call. Когда приложение группы ответа осуществляет поиск доступного агента, он выполняет поиск групп агента в том порядке, в котором они перечислены. You can select the agent groups that are assigned to the queue and specify queue behavior, such as limiting the number of calls that the queue can hold and the period of time that a call waits until an agent answers the call.
  
Чтобы создать или изменить очередь, используйте одну из следующих процедур.
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>Создание и изменение очереди с помощью панели управления Skype для бизнеса Server

1. Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.
    
    > [!NOTE]
    > Если вы являетесь одним из делегированных менеджеров группы ответа для управляемого рабочего процесса, вы можете создавать или изменять очереди группы ответа и назначать их рабочим процессам, которыми вы управляете. 
  
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.  
    
3. В левой панели навигации щелкните **Группы ответа**, затем щелкните **Очередь**.
    
4. На странице **Очередь** выполните одно из следующих действий.
    
   - Чтобы создать очередь, нажмите кнопку **Создать**. В окне **Выбор службы** в поле поиска введите имя службы **ApplicationServer**, для которой необходимо добавить очередь, или часть имени. В полученном списке служб выберите требуемую службу и затем нажмите кнопку **ОК**.
    
   - Чтобы изменить существующую очередь, введите в поле поиска ее имя или его часть. В полученном списке очередей выберите требуемую очередь, нажмите кнопку **Изменить**, а затем кнопку **Подробнее**.
    
5. В поле **Имя** введите понятное имя очереди.
    
6. В поле **Описание** введите описание очереди.
    
7. В поле **Группы** укажите группы, которые вы хотите назначить очереди. Выполните одно из следующих действий: 
    
   - Чтобы добавить группу в очередь, нажмите кнопку **Выбрать**. В поле поиска **Выбор групп** введите имя группы агентов, которую необходимо назначить очереди, или часть имени, выберите требуемую группу агентов и нажмите кнопку **ОК**.
    
   - Чтобы удалить группу из очереди, в списке групп агентов выберите требуемую группу и нажмите кнопку **Удалить**.
    
   - Чтобы изменить порядок поиска агентов, в списке групп агентов выберите группу и нажмите стрелку вверх или стрелку вниз.
    
     > [!NOTE]
     > При поиске доступного агента в очереди сервер использует порядковый номер группы, т. е. сначала сервер выбирает первую группу в списке, затем вторую и т. д. 
  
8. Чтобы задать максимальный период ожидания ответа агента (период удержания звонящего), установите флажок **Включить время ожидания очереди** и затем выполните следующие действия:
    
    a) В поле **Время ожидания (сек)** укажите максимальное время ожидания ответа агента на звонок.
    
    б) В **Действие вызова** выберите действие, выполняемое после завершения периода ожидания:
    
   - Чтобы разъединить звонок после завершения периода ожидания, установите переключатель **Отключить**.
    
   - Чтобы перенаправить звонок на голосовую почту, выберите команду **Переслать на голосовую почту**, а затем в поле **адрес SIP** введите адрес голосовой почты в формате SIP * \<:\>имя_пользователя*@ *\<DomainName\> * (например, SIP:Bob@contoso.com).
    
   - Чтобы перенаправить звонок на другой номер телефона, нажмите кнопку **Переслать на номер телефона**, а затем в поле **адрес SIP** введите номер телефона в формате SIP: * \<номер\>*@ *\<DomainName\> * (например, SIP:+14255550121@contoso.com).
    
   - Чтобы перенаправить звонок на другого пользователя, нажмите кнопку **Переслать на адрес SIP**, а затем введите в поле **SIP Address** (универсальный код ресурса) URI для пользователя в формате SIP: _ \<username\>_@ _\<имя_домена\>_.
    
   - Чтобы переадресовать звонок в другую очередь, установите переключатель **Переадресовывать в другую очередь**, затем выберите требуемую очередь.
    
9. Чтобы указать максимальное число звонков в очереди, установите флажок **Разрешить переполнение очереди**, затем выполните следующие действия:
    
    a) В поле **Максимальное число звонков** выберите максимальное число звонков, находящихся в очереди. 
    
    б) В поле **Переадресация звонка** выберите звонок, который будет переадресован при переполнении очереди (**Последний звонок** или **Первый звонок**).
    
    в. В поле **Действие при звонке** выберите действие, выполняемое при превышении максимального числа звонков:
    
   - Чтобы разъединить звонок после завершения периода ожидания, установите переключатель **Отключить**.
    
   - Чтобы перенаправить звонок на голосовую почту, выберите команду **Переслать на голосовую почту**, а затем в поле **адрес SIP** введите адрес голосовой почты в формате SIP * \<:\>имя_пользователя*@ *\<DomainName\> * (например, SIP:Bob@contoso.com).
    
   - Чтобы перенаправить звонок на другой номер телефона, нажмите кнопку **Переслать на номер телефона**, а затем в поле **адрес SIP** введите номер телефона в формате SIP: * \<номер\>*@ *\<DomainName\> * (например, SIP:+14255550121@contoso.com).
    
   - Чтобы перенаправить звонок на другого пользователя, нажмите кнопку **Переслать на адрес SIP**, а затем введите в поле **SIP Address** (универсальный код ресурса) URI для пользователя в формате SIP: _ \<username\>_@ _\<имя_домена\>_.
    
   - Чтобы переадресовать звонок в другую очередь, установите переключатель **Переадресовывать в другую очередь**, затем выберите требуемую очередь.
    
10. Нажмите **Исполнить**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>Создание и изменение очереди с помощью среды управления Skype для бизнеса Server

1. Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.
    
    > [!NOTE]
    > Если вы являетесь одним из делегированных диспетчеров группы ответа для управляемого рабочего процесса, вы можете создавать группы агентов и очереди и назначать группы агентов очередям. 
  
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. Создайте сообщение, которое будет воспроизводиться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке выполните следующую команду.
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Например:
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > Чтобы использовать аудиофайл для этой подсказки, воспользуйтесь командлетом **Import-CsRgsAudioFile**. Подробности можно найти в разделе [Import-ксргсаудиофиле](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
4. Определите действие, которое должно выполняться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке введите следующую команду.
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > Дополнительные сведения о возможностях и их синтаксисе: [New-ксргскаллактион](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Например:
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. Создайте сообщение, которое будет воспроизводиться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке выполните следующую команду.
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Например:
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > Чтобы использовать аудиофайл для этой подсказки, воспользуйтесь командлетом **Import-CsRgsAudioFile**. Подробности можно найти в разделе [Import-ксргсаудиофиле](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
6. Определите действие, которое должно выполняться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке введите следующую команду.
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > Дополнительные сведения о возможностях и их синтаксисе: [New-ксргскаллактион](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Например:
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. Извлеките имя службы из службы группы ответа и назначьте его переменной. В командной строке выполните следующую команду:
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. Получите идентификатор группы агентов, которую нужно назначить очереди. В командной строке выполните следующую команду.
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > Дополнительные сведения о создании группы агента: [New-ксргсажентграуп](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
9. Создайте очередь. В командной строке выполните следующую команду.
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   Например:
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. Убедитесь в том, что очередь создана. Выполните следующую команду.
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a>См. также

[New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[New-Ксргскаллактион](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[Remove-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)
