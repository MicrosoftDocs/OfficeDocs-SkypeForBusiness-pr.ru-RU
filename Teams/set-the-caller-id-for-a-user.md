---
title: Настройка идентификатора абонента для пользователя
ms.author: mikeplum
author: MikePlumleyMSFT
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
description: Узнайте о microsoft 365 и стандартном номере звоня в Office 365 (который назначен пользователю), который также называется ИД линии звонков. Вы можете изменить или заблокировать ИД вызываемой точки пользователя.
ms.openlocfilehash: 1cc6221c0f4ca1642cc9422ed81e0e07ae1bfc91
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569421"
---
# <a name="set-the-caller-id-for-a-user"></a>Настройка идентификатора абонента для пользователя
Телефонная система в Microsoft 365 и Office 365 предоставляет номер телефона, который назначен пользователю по умолчанию. Можно изменить или заблокировать идентификатор абонента (также называемый идентификатором вызывающей линии) для пользователя. Дополнительные сведения об использовании идентификатора абонента в своей организации можно получить, перейдя к статье [Использование идентификатора абонента в организации](how-can-caller-id-be-used-in-your-organization.md).
  
> [!TIP]
> В настоящее время в Skype для бизнеса Online невозможно заблокировать входящие вызовы. 
  
Для изменения доступны следующие настройки:
  
> [!NOTE]
> Эта функция **не предназначена** для организаций с локальными развертываниями Lync или Skype для бизнеса Server.
  
- **Изменить идентификатор исходящего абонента**. Вы можете заменить идентификатор абонента (по умолчанию соответствует номеру телефона, назначенному пользователю) другим номером. Например, вы можете заменить идентификатор абонента основным рабочим номером вашей организации или юридического отдела. В качестве идентификатора абонента можно указать любой номер **службы** в Интернете (как платный, так и бесплатный).
    
    > [!NOTE]
    > Чтобы использовать параметр  _Service_, необходимо указать допустимый номер службы.
  
- **Блокировать ИД исходящие вызываемой вызовы** Вы можете заблокировать отправление исходя из этой службы ИД звонив пользователю при исходяющих звонках по ННР. В этом случае номер телефона не будет отображаться на телефоне звонимого.
    
- **Блокировать его ИД входящих вызовов** Вы можете заблокировать получение ИД вызываемой службы во всех входящих звонках по ДНР.
    
> [!IMPORTANT]
> При звонках в экстренные службы номер телефона пользователя (идентификатор абонента) передается всегда. 
  
По умолчанию все параметры идентификатора абонента **отключены**. Это означает, что при звонке по телефону через ТСОП будет отображаться номер телефона пользователя в Skype для бизнеса Online.
  
Дополнительные сведения об этих параметрах и их использовании см. [Как можно использовать идентификатор абонента в организации?](how-can-caller-id-be-used-in-your-organization.md).
  
## <a name="set-your-caller-id-policy-settings"></a>Задание настроек политики идентификатора абонента

> [!NOTE]
> Для всех параметров , задав параметры "ИД звоня" в  Skype для бизнеса Online, необходимо использовать Windows PowerShell и не использовать Центр администрирования **Skype для бизнеса.** 
  
### <a name="start-powershell"></a>Запуск PowerShell

- Откройте Windows PowerShell и запустите следующие команды:

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
    
### <a name="see-all-of-the-caller-id-policy-settings-in-your-organization"></a>Просмотр всех настроек политики идентификатора абонента в организации

- Чтобы просмотреть все параметры политики ИД звоня в организации, запустите 365 параметров политики.

  ```PowerShell
  Get-CsCallingLineIdentity |fl
  ```
  См. другие примеры и подробные сведения о [Get-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793856.aspx)
    
### <a name="create-a-new-caller-id-policy-for-your-organization"></a>Создание политики идентификатора абонента для организации


- Чтобы создать новую политику, которая задает анонимный ИД звоня, запустите 4.
    
  ```PowerShell
  New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
  ```
  > [!NOTE]  
  > Во всех случаях поле «Номер службы» не должно содержать начальный символ «+».

  См. другие примеры и подробные сведения о [New-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793855.aspx)
    
- Чтобы применить новую политику, созданную для amos Marble, запустите 365:
    
  ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
  ```
  Дополнительные сведения о командлете [Grant-CsCallingLineIdentity](https://technet.microsoft.com/library/mt793857.aspx).
    
Если вы уже создали политику, вы можете внести изменения в существующую политику с помощью [cmdlet Set-CsCallingLineIdentity,](https://technet.microsoft.com/library/mt793854.aspx) а затем применить параметры к пользователям с помощью cmdletentity [Grant-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793857.aspx)
  
### <a name="set-it-so-the-incoming-caller-id-is-blocked"></a>Блокировка идентификатора входящего абонента

- Чтобы заблокировать ИД входящих зовите звонок, запустите 365.
    
  ```PowerShell
  Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true -EnableUserOverride $true
  ```
  См. другие примеры и подробные сведения о [Set-CsCallingLineIdentity.](https://technet.microsoft.com/library/mt793854.aspx)
    
- Чтобы применить параметр политики, созданный для пользователя в организации, запустите 3
    
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

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365, Office 365 и Skype для бизнеса Online, используя единый пункт администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин, по которым может потребоваться использовать Windows PowerShell для управления Microsoft 365 или Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Microsoft 365 или Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
  
 ## <a name="related-topics"></a>См. также:
[Общие вопросы по передаче номеров телефонов](/microsoftteams/transferring-phone-numbers-common-questions)

[Типы номеров телефонов, используемые в планах звонков](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)

[Дополнительные сведения об идентификаторе вызывающей линии и имени вызывающего абонента](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Условия и положения, распространяющиеся на экстренные вызовы](/microsoftteams/emergency-calling-terms-and-conditions)

[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
 
