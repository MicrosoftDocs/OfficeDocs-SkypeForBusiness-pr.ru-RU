---
title: Настройка идентификатора абонента для пользователя
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: Телефонная система в Office 365 предоставляет идентификатор абонента по умолчанию, который является назначенным пользователю номером телефона. Вы можете изменить или заблокировать идентификатор абонента (также называемый идентификатором вызывающей линии) для пользователя. Дополнительные сведения об использовании идентификатора абонента в организации см. в разделе «Использование идентификатора абонента в организации».
ms.openlocfilehash: cf6f1aab6f865a87186b7acb793e5aa7829907aa
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780820"
---
# <a name="set-the-caller-id-for-a-user"></a>Настройка идентификатора абонента для пользователя
Телефонная система в Office 365 предоставляет идентификатор вызывающего абонента по умолчанию, который является назначенным пользователю номером телефона. Вы можете изменить или заблокировать идентификатор вызывающего абонента (также называемый идентификатором вызывающей линии) для пользователя. Дополнительные сведения об использовании идентификатора вызывающего абонента в организации см. в разделе [Использование идентификатора абонента в организации](how-can-caller-id-be-used-in-your-organization.md).
  
> [!TIP]
> В настоящее время в Skype для бизнеса Online невозможно заблокировать входящие вызовы. 
  
Для изменения доступны следующие параметры.
  
> [!NOTE]
> Эта функция **не предназначена** для организаций с локальными развертываниями Lync или Skype для бизнеса Server.
  
- **Изменить идентификатор исходящего абонента**. Вы можете заменить идентификатор абонента (по умолчанию соответствует номеру телефона, назначенному пользователю) другим номером. Например, вы можете заменить идентификатор абонента основным рабочим номером вашей организации или юридического отдела. В качестве идентификатора абонента можно указать любой номер **службы** в Интернете (как платный, так и бесплатный).
    
    > [!NOTE]
    > Чтобы использовать параметр  _Service_, необходимо указать допустимый номер службы.
  
- **Блокировать идентификатор исходящего абонента**. Вы можете заблокировать отправку исходящего идентификатора абонента при звонках по ТСОП. В этом случае номер телефона не будет отображаться на телефоне вызываемого абонента.
    
- **Блокировать идентификатор входящего абонента**. Вы можете заблокировать получение идентификатора абонента в любых входящих звонках по ТСОП.
    
> [!IMPORTANT]
> При звонках в экстренные службы номер телефона пользователя (идентификатор абонента) передается всегда. 
  
По умолчанию все параметры идентификатора абонента **отключены**. Это означает, что при звонке по телефону через ТСОП будет отображаться номер телефона пользователя в Skype для бизнеса Online.
  
Дополнительные сведения об этих параметрах и их использовании см. [Как можно использовать идентификатор абонента в организации?](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Задание настроек политики идентификатора абонента

> [!NOTE]
> Для всех настроек идентификатора абонента в Skype для бизнеса Online нужно использовать Windows PowerShell. **Не удастся использовать** **центр администрирования Skype для бизнеса**. 
  
### <a name="verify-and-start-windows-powershell"></a>Проверка и запуск Windows PowerShell

- **Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**
    
1. Чтобы убедиться, что запущена версия 3.0 или более поздняя версия: **Меню "Пуск"** > **Windows PowerShell**.
    
2. Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.
    
3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.
    
4. Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.
    
    Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
    
- **Запуск сеанса Windows PowerShell**
    
1. Из **меню "Пуск"** > **Windows PowerShell**.
    
2. В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:
    
    > [!NOTE]
    > Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.
> 
  ```
Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
  ```
> 
  ```
  $credential = Get-Credential
  ```
> 
  ```
  $session = New-CsOnlineSession -Credential $credential
  ```
> 
  ```
  Import-PSSession $session
  ```

Если вы желаете получить больше информации по запуску Windows PowerShell см.[Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или[Подключение к Skype для бизнеса Online с использованием Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Просмотр всех настроек политики идентификатора абонента в организации

- Чтобы просмотреть все параметры политики идентификатора абонента в вашей организации, выполните следующую команду:

  ```
  Get-CsCallingLineIdentity |fl
  ```
Другие примеры [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx) и дополнительные сведения.
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Создание политики идентификатора абонента для организации


- Чтобы создать новую политику идентификатора абонента, которая устанавливает идентификатор абонента в качестве анонимного, выполните следующую команду:
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > Во всех случаях поле «Номер службы» не должно содержать начальный символ «+».

  Другие примеры [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx) и дополнительные сведения.
    
- Чтобы применить созданную политику к Amos Marble, выполните следующую команду:
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  Дополнительные сведения о командлете [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).
    
Если политика уже создана, используйте командлет [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx), чтобы внести в нее изменения. Затем используйте командлет [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx), чтобы применить настройки к пользователям.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Блокировка идентификатора вызывающего абонента

- Чтобы заблокировать идентификатор вызывающего абонента, выполните следующую команду:
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  Другие примеры [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) и дополнительные сведения.
    
- Чтобы применить созданную настройку политики к пользователю вашей организации, выполните следующую команду:
    
  ```
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    Дополнительные сведения о командлете [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).
    
### <a name="remove-a-caller-id-policy"></a>Удаление политики идентификатора абонента

Чтобы удалить политику организации, запустите следующую команду:
  
```
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Чтобы удалить политику пользователя, запустите следующую команду:
  
```
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell предназначена для управления пользователями и их правами. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>Похожие темы
[Общие вопросы по передаче номеров телефонов](/microsoftteams/transferring-phone-numbers-common-questions)

[Типы номеров телефонов, используемые в планах звонков](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)

[Дополнительные сведения об идентификаторе вызывающей линии и имени вызывающего абонента](../what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name.md)

[Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
