---
title: Создание или изменение очереди в Skype для бизнеса
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection:
  - IT_Skype16
  - Strat_SB_Admin
ms.custom: null
ms.assetid: b9d6366a-839f-4651-a01d-9254546cadeb
description: Создание или изменение очереди группы ответов в Skype для бизнеса Server Корпоративная голосовая связь.
---

# <a name="create-or-modify-a-queue-in-skype-for-business"></a>Создание или изменение очереди в Skype для бизнеса
 
Создание или изменение очереди группы ответов в Skype для бизнеса Server Корпоративная голосовая связь.
  
Вызывающие абоненты размещаются в очередях, пока агент не ответит на вызов. При поиске доступного агента приложение Группы реагирования выполняет поиск групп агентов в порядке их списка. Можно выбрать группы агентов, назначенные очереди, и указать поведение очереди, такое как ограничение количества вызовов, которое может размещаться в очереди, и время, которое вызов ожидает ответа агента.
  
Чтобы создать или изменить очередь, используйте одну из следующих процедур.
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-queue"></a>Использование панели Skype для бизнеса Server для создания или изменения очереди

1. Войдите в группу RTCUniversalServerAdmins или в качестве члена одной из предопределяемой административной роли, поддерживаемой группой реагирования.
    
    > [!NOTE]
    > Если вы являетесь одним из делегированных менеджеров группы ответа для управляемого рабочего процесса, вы можете создавать или изменять очереди группы ответа и назначать их рабочим процессам, которыми вы управляете. 
  
2. Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель Skype для бизнеса Server управления.  
    
3. В левой панели навигации щелкните **Response Groups** (Группы ответа) и затем щелкните **Queue** (Очередь).
    
4. На странице **Очередь** выполните одно из следующих действий.
    
   - Чтобы создать очередь, нажмите кнопку **Создать**. в окне **Выбор службы** в поле поиска введите имя службы **ApplicationServer**, для которой необходимо добавить очередь, или часть имени. В полученном списке служб выберите требуемую службу и затем нажмите кнопку **ОК**.
    
   - Чтобы изменить существующую очередь, введите в поле поиска ее имя или его часть. В полученном списке очередей выберите требуемую очередь, нажмите кнопку **Изменить**, а затем кнопку **Подробнее**.
    
5. В поле **Имя** введите понятное имя очереди.
    
6. В поле **Description** (Описание) введите описание очереди.
    
7. В поле **Группы** укажите группы, которые вы хотите назначить очереди. Выполните одно из следующих действий: 
    
   - Чтобы добавить группу в очередь, нажмите кнопку **Выбрать**. В поле поиска **Выбор групп** введите имя группы агентов, которую необходимо назначить очереди, или часть имени, выберите требуемую группу агентов и нажмите кнопку **ОК**.
    
   - Чтобы удалить группу из очереди, в списке групп агентов выберите требуемую группу и нажмите кнопку **Удалить**.
    
   - Чтобы изменить порядок поиска агентов, в списке групп агентов выберите группу и нажмите стрелку вверх или стрелку вниз.
    
     > [!NOTE]
     > При поиске доступного агента в очереди сервер использует порядковый номер группы, т. е. сначала сервер выбирает первую группу в списке, затем вторую и т. д. 
  
8. Чтобы задать максимальный период ожидания ответа агента (период удержания звонящего), установите флажок **Enable queue time-out** (Включить время ожидания очереди) и затем выполните следующие действия:
    
    а. В поле **Time-out period (seconds)** (Время ожидания (сек)) укажите максимальное время ожидания ответа агента на звонок.
    
    б. В **Call Action** (Действие вызова) выберите действие, выполняемое после завершения периода ожидания:
    
   - Чтобы разъединить звонок после завершения периода ожидания, установите переключатель **Disconnect** (Разъединить).
    
   - Чтобы переадлить вызов на голосовую почту, нажмите кнопку Вперед к голосовой **почте, а** затем в поле **адресов SIP** введите адрес голосовой почты в формате SIP: *\<username\>*@ *\<domainname\>* (например, sip:bob@contoso.com).
    
   - Чтобы переададовать вызов на другой телефонный **номер, нажмите** кнопку Вперед к номеру телефона, а затем в поле **адресов SIP** введите номер телефона в формате SIP: *\<number\>*@ *\<domainname\>* (например, sip:+14255550121@contoso.com).
    
   - Чтобы переадлить вызов другому пользователю, нажмите кнопку **Вперед к SIP-адресу**, а затем в поле **адресов SIP** введите URI для пользователя в формате SIP: _\<username\>_@ _\<domainname\>_.
    
   - Чтобы переадресовать звонок в другую очередь, установите переключатель **Forward to another queue** (Переадресовать в другую очередь) и затем выберите требуемую очередь.
    
9. Чтобы указать максимальное число звонков в очереди, установите флажок **Enable queue overflow** (Разрешить переполнение очереди) и затем выполните следующие действия:
    
    а. В поле **Maximum number of calls** (Максимальное число звонков) выберите максимальное число звонков, находящихся в очереди. 
    
    б. В поле **Forward the call** (Переадресация звонка) выберите звонок, который будет переадресован при переполнении очереди (**Newest Call** (Последний звонок) или **Oldest Call** (Первый звонок)).
    
    в. В поле **Действие при звонке** выберите действие, выполняемое при превышении максимального числа звонков:
    
   - Чтобы разъединить звонок после завершения периода ожидания, установите переключатель **Disconnect** (Разъединить).
    
   - Чтобы переадлить вызов на голосовую почту, нажмите кнопку Вперед к голосовой **почте, а** затем в поле **адресов SIP** введите адрес голосовой почты в формате SIP: *\<username\>*@ *\<domainname\>* (например, sip:bob@contoso.com).
    
   - Чтобы переададовать вызов на другой телефонный **номер, нажмите** кнопку Вперед к номеру телефона, а затем в поле **адресов SIP** введите номер телефона в формате SIP: *\<number\>*@ *\<domainname\>* (например, sip:+14255550121@contoso.com).
    
   - Чтобы переадлить вызов другому пользователю, нажмите кнопку **Вперед к SIP-адресу**, а затем в поле **адресов SIP** введите URI для пользователя в формате SIP: _\<username\>_@ _\<domainname\>_.
    
   - Чтобы переадресовать звонок в другую очередь, установите переключатель **Forward to another queue** (Переадресовать в другую очередь) и затем выберите требуемую очередь.
    
10. Нажмите кнопку **Сохранить**.
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-queue"></a>Использование Skype для бизнеса Server для создания или изменения очереди

1. Войдите в группу RTCUniversalServerAdmins или в качестве члена одной из предопределяемой административной роли, поддерживаемой группой реагирования.
    
    > [!NOTE]
    > Если вы являетесь одним из делегированных диспетчеров группы ответа для управляемого рабочего процесса, вы можете создавать группы агентов и очереди и назначать группы агентов очередям. 
  
2. Запустите Skype для бизнеса Server: нажмите кнопку **Начните, нажмите** кнопку Все **программы, нажмите** кнопку Skype для бизнеса **2015**, а затем нажмите кнопку **Skype для бизнеса Server управленческой оболочки**.
    
3. Создайте сообщение, которое будет воспроизводиться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке выполните следующую команду.
    
   ```powershell
   $promptTO = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Пример:
    
   ```console
   "All agents are currently busy. Please call back later."
   ```

   > [!NOTE]
   > Чтобы использовать для сообщения звуковой файл, воспользуйтесь командлетом **Import-CsRgsAudioFile**. Подробные сведения см. [в материале Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
4. Определите действие, которое должно выполняться при достижении порогового времени ожидания очереди, и сохраните его в переменной. В командной строке введите следующую команду.
    
   ```powershell
   $actionTO = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

   > [!NOTE]
   > Сведения о возможных действиях и синтаксисах см. в [материале New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Пример:
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptTO -Action Terminate
   ```

5. Создайте сообщение, которое будет воспроизводиться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке выполните следующую команду.
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "<text for TTS prompt>"
   ```

   Пример:
    
   ```powershell
   $promptOV = New-CsRgsPrompt -TextToSpeechPrompt "Too many calls are waiting. Please call back later."
   ```

      > [!NOTE]
      > Чтобы использовать для сообщения звуковой файл, воспользуйтесь командлетом **Import-CsRgsAudioFile**. Подробные сведения см. [в материале Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps). 
  
6. Определите действие, которое должно выполняться при достижении максимального числа звонков в очереди, и сохраните его в переменной. В командной строке введите следующую команду.
    
   ```powershell
   $actionOV = New-CsRgsCallAction -Prompt <saved prompt from previous step> -Action <action to be taken>
   ```

    > [!NOTE]
    > Сведения о возможных действиях и синтаксисах см. в [материале New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps). 
  
    Например:
    
   ```powershell
   $action = New-CsRgsCallAction -Prompt $promptOV -Action Terminate
   ```

7. Извлеките имя службы для службы группы ответа и назначьте его переменной. В командной строке введите следующую команду:
    
   ```powershell
   $serviceId="service:"+(Get-CSService | ?{$_.Applications -Like "*RGS*"}).ServiceId;
   ```

8. Получите идентификатор группы агентов, которую нужно назначить очереди. В командной строке выполните следующую команду.
    
   ```powershell
   $agid = (Get-CsRgsAgentGroup -Name "Help Desk").Identity;
   ```

    > [!NOTE]
    > Дополнительные сведения о создании группы агентов см. в [материале New-CsRgsAgentGroup](/powershell/module/skype/new-csrgsagentgroup?view=skype-ps).
  
9. Создайте очередь. В командной строке выполните следующую команду.
    
   ```powershell
   $q = New-CsRgsQueue -Parent <saved service ID from previous step> -Name "<name of queue>" [-Description "<description for queue>"] [-TimeoutThreshold <# seconds before call times out>] [-TimeoutAction <saved timeout action>] [-OverflowThreshold <# calls queue can hold>] [-OverflowCandidate <call to be acted on when overflow threshold met>] [-OverflowAction <saved overflow action>] [-AgentGroupIDList(<agent group identity>)];
   ```

   Пример:
    
   ```powershell
   $q = New-CsRgsQueue -Parent $serviceId -Name "Help Desk" -Description "Contoso Help Desk" -TimeoutThreshold 300 -TimeoutAction $actionTO -OverflowThreshold 10 -OverflowCandidate NewestCall -OverflowAction $actionOV -AgentGroupIDList($agid.Identity;
   ```

10. Убедитесь в том, что очередь создана. Выполните следующую команду.
    
    ```powershell
    Get-CsRgsQueue -Name "Help Desk"
    ```

## <a name="see-also"></a>См. также

[New-CsRgsQueue](/powershell/module/skype/new-csrgsqueue?view=skype-ps)
  
[Set-CsRgsQueue](/powershell/module/skype/set-csrgsqueue?view=skype-ps)
  
[New-CsRgsPrompt](/powershell/module/skype/new-csrgsprompt?view=skype-ps)
  
[New-CsRgsCallAction](/powershell/module/skype/new-csrgscallaction?view=skype-ps)
  
[Get-CsRgsQueue](/powershell/module/skype/get-csrgsqueue?view=skype-ps)
  
[Import-CsRgsAudioFile](/powershell/module/skype/import-csrgsaudiofile?view=skype-ps)
  
[Remove-CsRgsQueue](/powershell/module/skype/remove-csrgsqueue?view=skype-ps)