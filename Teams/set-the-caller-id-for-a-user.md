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
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Узнайте о Microsoft 365 и Office 365 ID вызывающего абонента по умолчанию (назначенный пользователю номер телефона), также называемый ИДЕНТИФИКАТОРом телефонной строки. Вы можете изменить или заблокировать идентификатор звонящего пользователя.
ms.openlocfilehash: 059e92f04f3d4a5df73ed9201f1f784f2bd01f30
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691125"
---
# <a name="set-the-caller-id-for-a-user"></a>Настройка идентификатора абонента для пользователя
Телефонная система в Microsoft 365 и Office 365 предоставляет идентификатор вызывающего абонента по умолчанию, который является назначенным пользователем номером телефона. Можно изменить или заблокировать идентификатор абонента (также называемый идентификатором вызывающей линии) для пользователя. Дополнительные сведения об использовании идентификатора абонента в своей организации можно получить, перейдя к статье [Использование идентификатора абонента в организации](how-can-caller-id-be-used-in-your-organization.md).
  
> [!TIP]
> В настоящее время в Skype для бизнеса Online невозможно заблокировать входящие вызовы. 
  
Для изменения доступны следующие настройки:
  
> [!NOTE]
> Эта функция **не предназначена** для организаций с локальными развертываниями Lync или Skype для бизнеса Server.
  
- **Изменить идентификатор исходящего абонента**. Вы можете заменить идентификатор абонента (по умолчанию соответствует номеру телефона, назначенному пользователю) другим номером. Например, вы можете заменить идентификатор абонента основным рабочим номером вашей организации или юридического отдела. В качестве идентификатора абонента можно указать любой номер **службы** в Интернете (как платный, так и бесплатный).
    
    > [!NOTE]
    > Чтобы использовать параметр  _Service_, необходимо указать допустимый номер службы.
  
- **Блокировка идентификатора исходящего вызывающего абонента** Вы можете заблокировать поступающий идентификатор вызывающего абонента при исходящих звонках с помощью КТСОП пользователя. Это заблокирует отображение номера телефона на телефоне вызываемого абонента.
    
- **Блокировка идентификатора входящего вызывающего абонента** Вы можете запретить пользователю получать идентификатор вызывающего абонента во всех входящих звонках по сети PSTN.
    
> [!IMPORTANT]
> При звонках в экстренные службы номер телефона пользователя (идентификатор абонента) передается всегда. 
  
По умолчанию все параметры идентификатора абонента **отключены**. Это означает, что при звонке по телефону через ТСОП будет отображаться номер телефона пользователя в Skype для бизнеса Online.
  
Дополнительные сведения об этих параметрах и их использовании см. [Как можно использовать идентификатор абонента в организации?](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Задание настроек политики идентификатора абонента

> [!NOTE]
> Для всех параметров идентификации вызывающего абонента в Skype для бизнеса Online необходимо использовать Windows PowerShell и **нельзя использовать** **центр администрирования Skype для бизнеса**. 
  
### <a name="verify-and-start-windows-powershell"></a>Проверка и запуск Windows PowerShell

- **Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**
    
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.
    
3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . При появлении запроса перезагрузите компьютер.
    
4. Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.
    
    Дополнительные сведения можно найти в разделе [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx).
    
- **Запуск сеанса Windows PowerShell**
    
1. From the **Start Menu** > **Windows PowerShell**.
    
2. В окне **Windows PowerShell** подключитесь к службе Microsoft 365 или Office 365, выполнив следующие действия:
    
   > [!NOTE]
   > Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.
   > 
   ```PowerShell
    Import-Module -Name SkypeOnlineConnector
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
   ```

Если вы хотите получить дополнительные сведения о запуске Windows PowerShell, ознакомьтесь со статьей [подключение ко всем службам Microsoft 365 или Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/library/dn568015.aspx) или [Настройка компьютера для Windows PowerShell](/skypeforbusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Просмотр всех настроек политики идентификатора абонента в организации

- Чтобы просмотреть все параметры политики идентификации вызывающего абонента в Организации, выполните следующие действия:

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  Ознакомьтесь с дополнительными примерами и подробными сведениями о [Get-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793856.aspx).
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Создание политики идентификатора абонента для организации


- Чтобы создать политику идентификации вызывающего абонента, которая устанавливает анонимный идентификатор вызывающего абонента, выполните следующие действия:
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > Во всех случаях поле «Номер службы» не должно содержать начальный символ «+».

  Ознакомьтесь с дополнительными примерами и подробными сведениями о [новых ВозCsCallingLineIdentityх](https://technet.microsoft.com/library/mt793855.aspx).
    
- Чтобы применить новую политику, созданную для Иван мрамора, выполните указанные ниже действия.
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  Дополнительные сведения о командлете [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).
    
Если вы уже создали политику, вы можете использовать командлет [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx) , чтобы внести изменения в существующую политику, а затем использовать командлет [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx) , чтобы применить параметры к вашим пользователям.
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Блокировка идентификатора входящего абонента

- Чтобы заблокировать входящий идентификатор вызывающего абонента, выполните следующие действия:
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  Ознакомьтесь с дополнительными примерами и подробными сведениями о [Set-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793854.aspx).
    
- Чтобы применить параметр политики, созданный для пользователя в Организации, выполните следующие действия:
    
  ```PowerShell
  Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
  ```
    Дополнительные сведения о командлете [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).
    
### <a name="remove-a-caller-id-policy"></a>Удаление политики идентификатора абонента

Чтобы удалить политику организации, запустите следующую команду:
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Чтобы удалить политику пользователя, запустите следующую команду:
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С помощью Windows PowerShell вы можете управлять Microsoft 365 или Office 365 и Skype для бизнеса Online, используя единую точку администрирования, которая позволяет упростить повседневную работу, если у вас есть несколько задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин, по которым вам может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell обладает многими преимуществами для ускорения, простоты и продуктивности с помощью центра администрирования Microsoft 365, например при одновременном изменении параметров для нескольких пользователей. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 и Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>См. также:
[Общие вопросы по передаче номеров телефонов](/microsoftteams/transferring-phone-numbers-common-questions)

[Типы номеров телефонов, используемые в планах звонков](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)

[Дополнительные сведения об идентификаторе вызывающей линии и имени вызывающего абонента](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
