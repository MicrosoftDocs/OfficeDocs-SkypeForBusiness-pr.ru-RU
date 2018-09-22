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
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Calling Plans
description: Телефонная система в Office 365 предоставляет стандартный идентификатор абонента. Он же является номером телефона, назначенным пользователю. Можно изменить или заблокировать идентификатор абонента (также называемый идентификатором вызывающей линии) для пользователя. Дополнительные сведения об использовании идентификатора абонента в своей организации можно получить, перейдя к статье «Использование идентификатора абонента в организации».
ms.openlocfilehash: 6b224addfcbc18ec3faad27e8369996647b51b03
ms.sourcegitcommit: c5940ef2674a00281604045baf8b2a320c4b189d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/21/2018
ms.locfileid: "24958194"
---
# <a name="set-the-caller-id-for-a-user"></a>Настройка идентификатора абонента для пользователя
Телефонная система в Office 365 предоставляет стандартный идентификатор абонента. Он же является номером телефона, назначенным пользователю. Можно изменить или заблокировать идентификатор абонента (также называемый идентификатором вызывающей линии) для пользователя. Дополнительные сведения об использовании идентификатора абонента в своей организации можно получить, перейдя к статье [Использование идентификатора абонента в организации](how-can-caller-id-be-used-in-your-organization.md).
  
> [!TIP]
> В настоящее время в Skype для бизнеса Online невозможно заблокировать входящие вызовы. 
  
Для изменения доступны следующие настройки:
  
> [!NOTE]
> Эта функция **не предназначена** для организаций с локальными развертываниями Lync или Skype для бизнеса Server.
  
- **Изменить идентификатор исходящего абонента**. Вы можете заменить идентификатор абонента (по умолчанию соответствует номеру телефона, назначенному пользователю) другим номером. Например, вы можете заменить идентификатор абонента основным рабочим номером вашей организации или юридического отдела. В качестве идентификатора абонента можно указать любой номер **службы** в Интернете (как платный, так и бесплатный).
    
    > [!NOTE]
    > Чтобы использовать параметр  _Service_, необходимо указать допустимый номер службы.
  
- **Блокировать их исходящих Звонящего** Можно заблокировать исходящей Звонящего отправки для исходящих вызовов ТСОП пользователя. При этом будет блокировать телефонный номер из показа на телефоне вызываемого пользователя.
    
- **Блокировать их входящих идентификатора звонящего** Можно запретить пользователю получение идентификатора звонящего на входящие вызовы ТСОП.
    
> [!IMPORTANT]
> При звонках в экстренные службы номер телефона пользователя (идентификатор абонента) передается всегда. 
  
По умолчанию все параметры идентификатора абонента **отключены**. Это означает, что при звонке по телефону через ТСОП будет отображаться номер телефона пользователя в Skype для бизнеса Online.
  
Дополнительные сведения об этих параметрах и их использовании см. [Как можно использовать идентификатор абонента в организации?](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Задание настроек политики идентификатора абонента

> [!NOTE]
> Для всех параметров идентификатора звонящего в Скайп для бизнеса в Интернет необходимо использовать Windows PowerShell и **нельзя использовать** **Скайп по центру администрирования бизнеса**. 
  
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

Дополнительные сведения о запуске Windows PowerShell, см [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или [подключение к Скайп для бизнеса в Интернет с помощью Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Просмотр всех настроек политики идентификатора абонента в организации

- Чтобы просмотреть все параметры политики идентификатор звонящего в вашей организации, выполните следующую команду:

  ```
  Get-CsCallingLineIdentity |fl
  ```
Просмотрите Дополнительные сведения и примеры для [Get-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793856.aspx).
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Создание политики идентификатора абонента для организации


- Чтобы создать новую политику идентификатор звонящего, который задает идентификатор звонящего для анонимного, выполните следующую команду:
    
  ```
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > Во всех случаях поле «Номер службы» не должно содержать начальный символ «+».

  Просмотрите дополнительные примеры и подробные сведения для [New-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793855.aspx).
    
- Чтобы применить новую политику, которую вы создали мрамор Amos, выполните следующую команду:
    
  ```
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  Дополнительные сведения о командлете [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx).
    
Если вы уже создали политику, можно использовать командлет [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx) внесение изменений в существующую политику и затем используйте командлет [Grant-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793857.aspx) для применения параметров для пользователей.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Блокировка идентификатора входящего абонента

- Чтобы блокировать входящие идентификатора звонящего, выполните следующую команду:
    
  ```
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  Просмотрите Дополнительные сведения и примеры для [Set-CsCallingLineIdentity](https://technet.microsoft.com/en-us/library/mt793854.aspx).
    
- Чтобы применить политику, которую вы создали для пользователей в вашей организации, выполните следующую команду:
    
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

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365 ](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>См. также:
[Общие вопросы по передаче номеров телефонов](/microsoftteams/transferring-phone-numbers-common-questions)

[Типы номеров телефонов, используемые в планах звонков](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)

[Дополнительные сведения об идентификаторе вызывающей линии и имени вызывающего абонента](../what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name.md)

[Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
