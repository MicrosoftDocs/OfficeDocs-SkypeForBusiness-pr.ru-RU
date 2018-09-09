---
title: Создание или изменение очереди в Скайп для бизнеса
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Создание или изменение очереди группы ответа, в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: cdddb57c3f0e06e851f39cba4b6f8322a28fd3fa
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23888153"
---
# <a name="create-or-modify-a-queue-in-skype-for-business"></a>Создание или изменение очереди в Скайп для бизнеса
 
Создание или изменение очереди группы ответа, в Скайп Business Server корпоративной голосовой связи.
  
Очереди содержат абонентов, пока агент отвечает на звонок. Когда приложение группы ответа выполняет поиск доступного агента, будет выполняться поиск группы агентов в порядке их список. Можно выбрать группы агентов, назначенные в очередь и задать поведение очереди, такие как ограничивать количество вызовов, в очереди и период времени, что вызов ожидает ответы агента вызова.
  
Чтобы создать или изменить очередь, используйте одну из следующих процедур.
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>Чтобы использовать Скайп для панели управления Business Server для создания или изменения очереди

1. Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.
    
    > [!NOTE]
    > Если вы являетесь одним из делегированных менеджеров группы ответа для управляемого рабочего процесса, вы можете создавать или изменять очереди группы ответа и назначать их рабочим процессам, которыми вы управляете. 
  
2. Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.  
    
3. В левой панели навигации щелкните **Группы ответа**, затем щелкните **Очередь**.
    
4. На странице **Очередь** выполните одно из следующих действий.
    
   - Чтобы создать очередь, нажмите кнопку **Создать**. В **поле выбора службы**введите часть имени или полное имя службы **ApplicationServer** , где вы хотите добавить очереди в поле поиска. В полученном списке служб выберите требуемую службу и затем нажмите кнопку **ОК**.
    
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
    
    а. В поле **Время ожидания (сек)** укажите максимальное время ожидания ответа агента на звонок.
    
    б. В **Действие вызова** выберите действие, выполняемое после завершения периода ожидания:
    
     - Чтобы разъединить звонок после завершения периода ожидания, установите переключатель **Отключить**.
    
     - Переадресация звонков на голосовую почту, нажмите кнопку **переадресация на голосовую почту**и затем в поле **SIP-адрес** введите адрес голосовой почты в формате sip: _ \<username\>_@ _\<domainname\> _ (для Например, sip:bob@contoso.com).
    
     - Переадресация звонков на другой номер телефона, нажмите кнопку **переадресация на номер телефона**и затем в поле **SIP-адрес** введите номер телефона в формате sip: _ \<номер\>_@ _\<domainname\>_ (например, sip:+14255550121@contoso.com).
    
     - Чтобы переадресовать звонок на другого пользователя, нажмите кнопку **переадресация на SIP-адрес**, а затем в поле **SIP-адрес** введите URI для пользователя в формате sip: _ \<username\>_@ _\<domainname\>_.
    
     - Чтобы переадресовать звонок в другую очередь, установите переключатель **Переадресовывать в другую очередь**, затем выберите требуемую очередь.
    
9. Чтобы указать максимальное число звонков в очереди, установите флажок **Разрешить переполнение очереди**, затем выполните следующие действия:
    
    а. В поле **Максимальное число звонков** выберите максимальное число звонков, находящихся в очереди. 
    
    б. В поле **Переадресация звонка** выберите звонок, который будет переадресован при переполнении очереди (**Последний звонок** или **Первый звонок**).
    
    в. В поле **Действие при звонке** выберите действие, выполняемое при превышении максимального числа звонков:
    
     - Чтобы разъединить звонок после завершения периода ожидания, установите переключатель **Отключить**.
    
     - Переадресация звонков на голосовую почту, нажмите кнопку **переадресация на голосовую почту**и затем в поле **SIP-адрес** введите адрес голосовой почты в формате sip: _ \<username\>_@ _\<domainname\> _ (для Например, sip:bob@contoso.com).
    
     - Переадресация звонков на другой номер телефона, нажмите кнопку **переадресация на номер телефона**и затем в поле **SIP-адрес** введите номер телефона в формате sip: _ \<номер\>_@ _\<domainname\>_ (например, sip:+14255550121@contoso.com).
    
     - Чтобы переадресовать звонок на другого пользователя, нажмите кнопку **переадресация на SIP-адрес**, а затем в поле **SIP-адрес** введите URI для пользователя в формате sip: _ \<username\>_@ _\<domainname\>_.
    
     - Чтобы переадресовать звонок в другую очередь, установите переключатель **Переадресовывать в другую очередь**, затем выберите требуемую очередь.
    
10. Нажмите **Исполнить**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>Чтобы использовать Скайп для консоли Business Server для создания или изменения очереди

1. Выполните вход как член группы RTCUniversalServerAdmins или одной из предварительно заданных административных ролей, поддерживающих группу ответа.
    
    > [!NOTE]
    > Если вы являетесь одним из делегированных диспетчеров группы ответа для управляемого рабочего процесса, вы можете создавать группы агентов и очереди и назначать группы агентов очередям. 
  
2. Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.
    
3. Создайте сообщение, которое будет воспроизводиться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке выполните следующую команду.
    
   ```
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Например:
    
   ```
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > Чтобы использовать звукового файла в строке, используйте командлет **Import-CsRgsAudioFile** . Дополнительные сведения см [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
4. Определите действие, которое должно выполняться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке введите следующую команду.
    
   ```
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > Для получения дополнительных сведений о возможных действий и их синтаксисе см [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Например:
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. Создайте сообщение, которое будет воспроизводиться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке выполните следующую команду.
    
  ```
  $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
  ```

   Например:
    
  ```
  $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
  ```

      > [!NOTE]
      > Чтобы использовать звукового файла в строке, используйте командлет **Import-CsRgsAudioFile** . Дополнительные сведения см [Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
6. Определите действие, которое должно выполняться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке введите следующую команду.
    
  ```
  $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
  ```

    > [!NOTE]
    > Для получения дополнительных сведений о возможных действий и их синтаксисе см [New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Например:
    
   ```
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. Извлеките имя службы из службы группы ответа и назначьте его переменной. В командной строке выполните следующую команду:
    
   ```
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. Получите идентификатор группы агентов, которую нужно назначить очереди. В командной строке выполните следующую команду.
    
   ```
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > Сведения о создании группы агентов в разделе [New-CsRgsAgentGroup](https://docs.microsoft.com/powershell/module/skype/new-csrgsagentgroup?view=skype-ps)
  
9. Создайте очередь. В командной строке выполните следующую команду.
    
   ```
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   Например:
    
   ```
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. Убедитесь в том, что очередь создана. Выполните следующую команду.
    
   ```
   Get-CsRgsQueue -Name "Help Desk"
   ```

## <a name="see-also"></a>См. также

[Командлет New-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Командлет Set-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[Командлет New-CsRgsPrompt](https://docs.microsoft.com/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[Командлет New-CsRgsCallAction](https://docs.microsoft.com/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[Командлет Get-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[Import-CsRgsAudioFile](https://docs.microsoft.com/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[Командлет remove-CsRgsQueue](https://docs.microsoft.com/powershell/module/skype/remove-csrgsqueue?view=skype-ps)