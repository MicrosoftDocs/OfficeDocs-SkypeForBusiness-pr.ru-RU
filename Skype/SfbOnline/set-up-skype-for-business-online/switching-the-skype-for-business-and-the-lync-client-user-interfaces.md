---
title: Переключение между пользовательскими интерфейсами клиентов Skype для бизнеса и Lync
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: a2394a4c-7522-484c-a047-7b3289742be0
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Узнайте, как переключаться между пользовательскими интерфейсами Skype для бизнеса и Lync с помощью PowerShell в Microsoft 365 или Office 365 '
ms.openlocfilehash: ecb494ea274a9652024056c1b0725159565d22af
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2021
ms.locfileid: "60014993"
---
# <a name="switching-between-the-skype-for-business-and-the-lync-client-user-interfaces"></a>Переключение между пользовательскими интерфейсами клиентов Skype для бизнеса и Lync

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Для организаций Skype для бизнеса Online можно использовать удаленную powerShell в Microsoft 365 или Office 365, чтобы пользователи Skype для бизнеса могли использовать клиент Skype для бизнеса или пользовательский интерфейс Skype для бизнеса (Lync). По умолчанию пользователи могут использовать пользовательский интерфейс Skype для бизнеса клиента. Если вы хотите использовать интерфейс клиента Lync, вы можете управлять поведением клиента первого запуска, чтобы отобразить пользовательский интерфейс Lync. Для этого следуя этим шагам ниже.
  
> [!NOTE]
> Интерфейс клиента Lync 2013 недоступен для версий Skype для бизнеса 2016. Перед настройкой клиентской среды на использование клиента Lync 2013 убедитесь, что версия клиента не начинается с цифр "16" (например: 16.x.x.x). 
  
> [!TIP]
> Если вы хотите легко переключить пользовательский интерфейс и не хотите делать это вручную, см. в центре загрузки [Майкрософт](https://go.microsoft.com/fwlink/?LinkId=532431) сценарий PowerShell, чтобы упростить его.
  
## <a name="switching-the-skype-for-business-user-interface-for-users"></a>Переключение пользовательского интерфейса Skype для бизнеса для пользователей

Модуль Windows PowerShell для Skype для бизнеса online позволяет запускать удаленные сеансы Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-битных компьютерах, можно скачать из Центра загрузки Майкрософт по ссылке Скачивание и установка Teams [PowerShell.](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md) Другие сведения см. в настройках компьютера для [управления Skype для бизнеса Online.](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
> [!IMPORTANT]
> Параметр политики  _Global_ для переключения пользовательского интерфейса не применяется, если пользователь уже применил настраиваемую политику. Чтобы изменить пользовательский интерфейс, необходимо выполнить следующую команду для каждого пользователя, применившего настраиваемую политику:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

> [!CAUTION]
> Политика  _ClientPolicyEnableSkypeUI_ заменит действующую настраиваемую политику пользователя.
  
Чтобы включить клиент Skype для бизнеса для всех пользователей в вашей организации, откройте Remote PowerShell и введите следующую команду:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Если политика настроена правильно, появится следующая запись:
  
![PowerShell: SkypeUIEnabled.](../images/b6b9d2e1-1a37-46df-9757-f81c6054e93b.png)
  
Чтобы включить клиент Skype для бизнеса (Lync) для всех пользователей в вашей организации, откройте Remote PowerShell и введите следующую команду: 
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

Если политика настроена правильно, появится следующая запись:
  
![PowerShell: SkypeUIDisabled.](../images/f14ec3ce-4eb8-4a11-826e-6029043ed054.png)
  
Чтобы включить клиент Skype для бизнеса для одного пользователя в вашей организации, откройте Remote PowerShell и введите следующую команду:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>
```

Если политика настроена правильно, появится следующая запись:
  
![Skype для бизнеса В сети : включить пользовательский интерфейс.](../images/596aef69-41dc-4e1e-b689-2b7009ae58a1.png)
  
Чтобы включить клиент Skype для бизнеса (Lync) для одного пользователя в вашей организации, откройте Remote PowerShell и введите следующую команду:
  
```PowerShell
Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI -Identity <username>
```

Если политика настроена правильно, появится следующая запись:
  
![Skype для бизнеса Интернет — пользовательский интерфейс отключен.](../images/61c645e0-67fc-4e03-803c-b7028a47dae3.png)
  
Чтобы включить клиент Skype для бизнеса для нескольких пользователей в вашей организации, откройте Remote PowerShell и введите следующую команду:
  

```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com") 

$users | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Чтобы включить клиент Skype для бизнеса (Lync) для нескольких пользователя в вашей организации, откройте Remote PowerShell и введите следующую команду:
  
```PowerShell
$users = @("sip:bob@contoso.com","sip:fred@contoso.com")

$users | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

Чтобы включить клиент Skype для бизнеса для группы пользователей в вашей организации, откройте Remote PowerShell и введите следующую команду:
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI
```

Чтобы включить клиент Skype для бизнеса (Lync) для группы пользователей в вашей организации, откройте Remote PowerShell и введите следующую команду:
  
```PowerShell
Get-CsOnlineUser -Filter {Department -eq "Sales"} | Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI
```

> [!NOTE]
>  Имя пользователя  это имя учетной записи пользователя, для которой необходимо назначить политику. Имя учетной записи пользователя может быть указано в следующих форматах:>  Адрес SIP пользователя>  Имя участника-пользователя (UPN)>  Домен пользователя\\имя пользователя>  Отображаемое имя Active Directory пользователя
  
[Использование Windows PowerShell для управления Lync Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  
## <a name="skype-for-business-online-policy-settings"></a>Параметры политики Skype для бизнеса Online

Эта таблица содержит информацию о взаимодействии с пользователем при первом применении политики.
  
|**Параметр политики администратора**|**Пользовательский интерфейс**|
|:-----|:-----|
|Политика не установлена. |Пользователь продолжает работать в пользовательском интерфейсе клиента Skype для бизнеса.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`<br/>|Пользователь продолжает работать в пользовательском интерфейсе клиента Skype для бизнеса.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`<br/>|Пользователю будет предложено переключиться на пользовательский интерфейс Skype для бизнеса (Lync). Пользователь может переключиться позже.|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI -Identity <username>`|Пользователь будет использовать пользовательский интерфейс Skype для бизнеса клиента. |
`Grant-CsClientPolicy-PolicyName ClientPolicyDisableSkypeUI -Identity <username>`|Пользователю будет предложено переключиться на пользовательский интерфейс Skype для бизнеса (Lync). В дальнейшем администратор может изменить этот параметр и переключить пользователя на пользовательский интерфейс клиента Skype для бизнеса. |
   
Эта таблица содержит информацию о взаимодействии с пользователем при изменении политики.
  
|**Параметр политики администратора**|**Пользовательский интерфейс Skype для бизнеса (Lync)**|**Пользовательский интерфейс Skype для бизнеса**|
|:-----|:-----|:-----|
|`Grant-CsClientPolicy -PolicyName ClientPolicyEnableSkypeUI`|Пользователю будет предложено переключиться на пользовательский интерфейс Skype для бизнеса клиента.  <br/> |Пользователь продолжит использовать пользовательский интерфейс Skype для бизнеса клиента.  <br/> |
|`Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI`|Пользователь продолжит использовать интерфейс Skype для бизнеса (Lync).  <br/> |Пользователю будет предложено переключиться на пользовательский интерфейс Skype для бизнеса (Lync).  <br/> |
|Политика не установлена.  <br/> |Пользователи не увидят пользовательский интерфейс Skype для бизнеса (Lync), если политика не настроена. Пользователь будет работать только в пользовательском интерфейсе клиента Skype для бизнеса.  <br/> |Пользователь продолжит использовать пользовательский интерфейс Skype для бизнеса клиента.  <br/> |
   
В этой таблице приводятся все настраиваемые политики, доступные для Online. Эти новые политики были созданы для того, чтобы предоставить администраторам гибкость и сохранить прежнюю настраиваемую политику при переключении флагов EnableSkypeUI. Чтобы назначить пользователям одну из приведенных ниже политик, используйте указанные выше командлеты.
  
|**Название политики**|**EnableSkypeUI**|
|:-----|:-----|
`ClientPolicyDefaultPhoto`||
`ClientPolicyDefaultPhotoDisableSkypeUI` |False|
`ClientPolicyNoIMURL`||
`ClientPolicyNoIMURLDisableSkypeUI` |False|
`ClientPolicyNoIMURLPhoto`||
`ClientPolicyNoIMURLPhotoDisableSkypeUI` |False|
`ClientPolicyNoSaveIMNoArchivingI`||
`ClientPolicyNoSaveIMNoArchivingDisableSkypeUI` |False|
`ClientPolicyNoSaveIMNoArchivingNoIMURL`||
`ClientPolicyNoSaveIMNoArchivingNoIMURLDisableSkypeUI` |False|
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhoto` ||
`ClientPolicyNoSaveIMNoArchivingNoIMURLPhotoDisableSkypeUI`|False|
`ClientPolicyNoSaveIMNoArchivingPhoto`||
`ClientPolicyNoSaveIMNoArchivingPhotoDisableSkypeUI` |False|

   
Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
  
- [Зачем нужна Microsoft 365 или Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
## <a name="first-launch-client-behaviors"></a>Режим работы клиента при первом запуске

По умолчанию при первом запуске Skype для бизнеса пользователи всегда будут видеть пользовательский интерфейс Skype для бизнеса, даже если вы выбрали интерфейс клиента Lync путем настройки клиентской политики Lync (), как описано `Grant-CsClientPolicy -PolicyName ClientPolicyDisableSkypeUI` выше. Через несколько минут пользователям будет предложено переключиться в режим Lync.
  
Чтобы отобразить интерфейс Lync при первом запуске клиента Skype для бизнеса, выполните следующие действия до того, как клиент будет запущен в первый раз после обновления.
  
1. Выполните действия, описанные выше в этом разделе, и подтвердите, что политика клиента настроена на отключение интерфейса Skype для бизнеса.
    
2. Обновите системный реестр на компьютере пользователя. Это необходимо сделать до первого запуска клиента Skype для бизнеса. Действие выполняется всего один раз. Сведения о создании объекта групповой политики для обновления реестра на присоединенном к домену компьютере см. далее в этом разделе.
    
    В строке **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]** создайте новое **бинарное** значение.
    
    **Имя значения** должно быть **EnableSkypeUI**. Для **данных значения** задайте **00 00 00 00**.
    
    Строка должна выглядеть следующим образом:
    
    [HKEY_CURRENT_USER \\ Программное \\ обеспечение Microsoft Office \\ \\ Lync]
    
    "CanSharePptInCollab"=dword:00000001
    
    "CanShareOneNoteInCollab"=dword:00000001
    
    "CanAppShareInCollab"=dword:00000001
    
    "EnableSkypeUI"=hex:00,00,00,00,00
    
Теперь интерфейс Lync будет отображаться при первом запуске клиента Skype для бизнеса пользователями.
  
### <a name="control-the-display-of-the-welcome-screen-tutorial"></a>Руководство по управлению отображением экрана приветствия

Когда пользователи открывают клиент Skype для бизнеса, по умолчанию отображается экран приветствия, который содержит *7* кратких советов, которые большинство людей просят . Вы можете отключить отображение экрана приветствия, но при этом разрешить пользователям получать доступ к учебнику, добавив на клиентский компьютер следующее значение реестра:
  
В строке **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** создайте новое **значение DWORD (32-разрядное)**. **Имя значения** должно быть **IsBasicTutorialSeenByUser**. Для **данных значения** задайте **1**.
  
Строка должна выглядеть следующим образом:
  
`"IsBasicTutorialSeenByUser"=dword:00000001`

### <a name="turn-off-the-client-tutorial"></a>Отключение руководства в клиенте

Чтобы не показывать пользователям руководство, задайте в реестре следующее значение.
  
В строке **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\15.0\\Lync]** создайте новое **значение DWORD (32-разрядное)**. **Имя значения** должно быть **TutorialFeatureEnabled**. Для **данных значения** задайте **0**.
  
```PowerShell
"TutorialFeatureEnabled"=dword:00000000
```

Чтобы снова включить руководство, задайте для параметра **Данные значения** значение **1**.
  
## <a name="create-a-group-policy-object-to-modify-the-registry-on-a-domain-joined-computer"></a>Создание объекта групповой политики для изменения реестра на компьютере, присоединенном к домену

Для отображения интерфейса Lync при первом запуске клиента Skype для бизнеса необходимо только один раз обновить реестр. Если для обновления реестра используется объект групповой политики (GPO), необходимо определить объект для создания нового значения, а не обновлять данные значения. Если при применении GPO новое значение не существует, оно будет создано, а для данных значения будет задано значение 0.
  
В процедуре ниже описывается изменение реестра таким образом, чтобы при первом запуске Skype для бизнеса пользователем отображался интерфейс Lync. С помощью этой процедуры можно также обновить реестр и отключить показ учебного пособия на экране приветствия, как описано выше.
  
 **Создание GPO**
  
1. Запустите **Консоль управления групповыми политиками**.
    
    Сведения о работе с консолью управления групповыми политиками см. в разделе [Консоль управления групповыми политиками](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/dn265969(v=ws.11)).
    
2. Щелкните правой кнопкой мыши узел **Объекты групповой политики** и выберите в меню пункт **Создать**.
    
3. В диалоговом окне **Новый объект групповой политики** введите название объекта, напримерMakeLyncDefaultUI, затем нажмите кнопку **OK**.
    
4. Щелкните правой кнопкой мыши только что созданный объект групповой политики и выберите в меню пункт **Редактировать**.
    
5. В **Редакторе управления групповыми политиками** разверните папки **Конфигурация пользователя**, **Параметры**, **Параметры Windows** и выберите узел **Реестр**.
    
6. Щелкните правой кнопкой мыши на узле **Реестр** и выберите **Создать** > **Элемент реестра**.
    
7. В диалоговом окне **Новые свойства реестра** обновите следующие поля.
    
|**Поле**|**Значение для выбора или ввода**|
|:-----|:-----|
|**Описание** <br/> |**Создание** <br/> |
|**Куст** <br/> | HKEY_CURRENT_USER <br/> |
|**Путь к разделу** <br/> |Программное \\ обеспечение Microsoft Office \\ \\ Lync  <br/> |
|**Имя значения** <br/> |EnableSkypeUI  <br/> |
|**Тип значения** <br/> |REG_BINARY  <br/> |
|**Данные значения** <br/> |00000000  <br/> |
   
Нажмите кнопку **OK**, чтобы сохранить изменения, затем закройте объект групповой политики.
    
Далее следует связать созданный объект групповой политики с группой пользователей, которым необходимо назначить политику, например, с подразделением.
  
 **Назначение политики с помощью GPO**
  
1. В консоли управления групповыми политиками щелкните правой кнопкой мыши на подразделении, которому необходимо назначить групповую политику, и выберите **Связать с существующим объектом групповой политики**.
    
2. В диалоговом окне **Выбор объекта групповой политики** выберите созданный объект групповой политики и нажмите кнопку **OK**.
    
3. На целевом компьютере пользователя откройте командную строку и введите следующую команду:
    
    **gpupdate /target:user**
    
    При применении объекта групповой политики отобразится сообщение "Обновление политики...". После завершения обновления отобразится сообщение "Обновление политики пользователя завершено успешно".
    
4. В командной строке введите следующую команду:
    
    **gpresult /r**
    
    Ниже отобразится список назначенных объектов групповой политики с именем созданного объекта групповой политики.
    
Также можно проверить успешное обновление реестра объектом групповой политики на компьютере пользователя, изучив реестр. Откройте редактор реестра и найдите строку **[HKEY_CURRENT_USER\\Software\\Microsoft\\Office\\Lync]**. Если объект групповой политики успешно обновил реестр, будет отображаться значение с именем EnableSkypeUI и значением 0.
  
## <a name="related-topics"></a>Статьи по теме
[Настройка Skype для бизнеса Online](set-up-skype-for-business-online.md)

[Разрешение на добавление контактов Skype пользователям Skype для бизнеса](let-skype-for-business-users-add-skype-contacts.md)

  
