---
title: Настройка идентификатора абонента для пользователя
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: c7323490-d9b7-421a-aa76-5bd485f80583
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business Online
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-mar2020
description: Узнайте о Microsoft 365 и Office 365 по умолчанию (номер телефона, который назначен пользователю), который также называется ИД строки звонков. Вы можете изменить или заблокировать ИД вызываемой пользователем.
ms.openlocfilehash: dbbb48952264d82ca24bdd82dbb45538b0428368
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308338"
---
# <a name="set-the-caller-id-for-a-user"></a>Настройка идентификатора абонента для пользователя

телефонная система в Microsoft 365 предоставляется стандартный номер телефона, который назначен пользователю. Можно изменить или заблокировать идентификатор абонента (также называемый идентификатором вызывающей линии) для пользователя. Дополнительные сведения об использовании идентификатора абонента в своей организации можно получить, перейдя к статье [Использование идентификатора абонента в организации](how-can-caller-id-be-used-in-your-organization.md).
  
По умолчанию следующие параметры ИД вызываемой стороны **отключены.** Это означает, Teams номер телефона пользователя будет виден, когда этот пользователь звонит на телефон ЗВОНКОВ. Эти параметры можно изменить следующим образом:
  
- **ИД исходячего звоня** Вы можете заменить пользовательский номер телефона, который по умолчанию является его номером телефона, другим номером телефона. Например, можно изменить номер телефона пользователя с номера телефона на основной номер телефона для вашей компании или изменить номер телефона пользователя с номера телефона на основной номер для юридического отдела. Вы можете изменить номер для звонков на любой номер веб-службы (платный или бесплатный). Вы также можете изменить номер телефона локального телефона, перенаправив его на учетную запись ресурса, используемую автозаправщиком или очередью звонков.
    
  > [!NOTE]
  > Если вы хотите использовать параметр *Service,* необходимо указать действительный номер службы.
  
- **Блокировать ИД исходящие вызовы.** Вы можете заблокировать отправление исходяющих звонков по ДНР. Это позволит заблокировать отображение номера телефона на телефоне звонимого человека.
    
- **Блокировать ИД входящих звонит.** Вы можете заблокировать получение ИД вызываемой службы при любых входящих звонках по ННР.

- **Set Calling Party Name (CNAM).** Для ваших Microsoft Teams вы можете отправлять CNAM при исходящие звонки по ЗВОНКОВ по ННП.
    
> [!IMPORTANT]
> При звонках в экстренные службы номер телефона пользователя (идентификатор абонента) передается всегда. 
  

  
Дополнительные информацию об этих параметрах и их использовании см. в этой [статьи.](how-can-caller-id-be-used-in-your-organization.md)
  
## <a name="set-your-caller-id-policy-settings"></a>Задание настроек политики идентификатора абонента

> [!NOTE]
> Чтобы установить для ИД звонящая номер телефона учетной записи ресурса и имя вызываемой стороны, используйте командлеты PowerShell New-CsCallingLineIdentity или Set-CsCallingLineIdentity в модуле Teams PowerShell 2.3.1 или более поздней. (В настоящее время эти параметры недоступны в Центре Microsoft Teams администрирования.) 

Откройте Windows PowerShell командную команду и запустите следующие команды:

```PowerShell
# When using Teams PowerShell Module

Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
``` 

### <a name="view-create-and-apply-policy-settings"></a>Просмотр, создание и применение параметров политики

1. Чтобы просмотреть все параметры политики ИД вызываемого звоня в организации, запустите:

     ```PowerShell
     Get-CsCallingLineIdentity |fl
     ```
   Дополнительные сведения [см. в окне Get-CsCallingLineIdentity.](/powershell/module/skype/Get-CsCallingLineIdentity)
    
2. Чтобы создать политику кодов вызываемого звоня в организации, воспользуйтесь New-CsCallingIdentity управления:
    
     ```PowerShell
     New-CsCallingLineIdentity  -Identity Anonymous -Description "Anonymous policy" -CallingIDSubstitute Anonymous -EnableUserOverride $false
     ```
    Во всех случаях поле «Номер службы» не должно содержать начальный символ «+».

   Дополнительные сведения см. [в new-CsCallingLineIdentity.](/powershell/module/skype/New-CsCallingLineIdentity)
    
3. Применим новую политику, созданную с Grant-CsCallingIdentity управления. Например, в следующем примере новая политика применяется к пользователю Amos Marble.
    
     ```PowerShell
      Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName Anonymous
     ```
   Дополнительные сведения [см.](/powershell/module/skype/Grant-CsCallingLineIdentity) в этом окне.
    

4. Если вы хотите заблокировать ИД входящих вызовов, запустите:
    
   ```PowerShell
   Set-CsCallingLineIdentity  -Identity "Block Incoming" -BlockIncomingPstnCallerID $true
   ``` 

   Дополнительные сведения [см. в теме Set-CsCallingLineIdentity.](/powershell/module/skype/Set-CsCallingLineIdentity)
    
5. Чтобы применить параметр политики, созданный для пользователя в организации, запустите:
    
   ```PowerShell
   Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName "Block Incoming"
   ```
   Дополнительные сведения [см. в теме Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)

6. Чтобы создать политику "ИД звонящая", которая задает для имени вызываемого пользователя номер телефона указанной учетной записи ресурса и для имени вызываемой стороны — Contoso:

   ```PowerShell
   $ObjId = (Get-CsOnlineApplicationInstance -Identity dkcq@contoso.com).ObjectId
   New-CsCallingLineIdentity  -Identity DKCQ -CallingIDSubstitute Resource -EnableUserOverride $false -ResourceAccount $ObjId -CompanyName "Contoso"
   ```

Если вы уже создали политику, вы можете изменить существующую политику с помощью [cmdlet Set-CsCallingLineIdentity,](/powershell/module/skype/Set-CsCallingLineIdentity) а затем применить параметры к пользователям с помощью cmdlet [Grant-CsCallingLineIdentity.](/powershell/module/skype/Grant-CsCallingLineIdentity)
    
### <a name="remove-a-policy-setting"></a>Удаление параметра политики

Чтобы удалить политику организации, запустите следующую команду:
  
```PowerShell
Remove-CsCallingLineIdentity -Identity "My Caller ID Policy"
```
Чтобы удалить политику пользователя, запустите следующую команду:
  
```PowerShell
Grant-CsCallingLineIdentity -Identity "amos.marble@contoso.com" -PolicyName $null
```
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows PowerShell?

Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С Windows PowerShell вы можете управлять Microsoft 365 с помощью единого администрирования, который упростит вашу повседневную работу. Для начала работы с Windows PowerShell ознакомьтесь с приведенными ниже разделами.
    
- [Введение в Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [Шесть причин, по которым может потребоваться использовать Windows PowerShell управление Microsoft 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только центра администрирования Microsoft 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
- [Лучшие способы управления Microsoft 365 с помощью Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- [Использование Windows PowerShell для управления Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
- [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  
 ## <a name="related-topics"></a>См. также:
[Общие вопросы по передаче номеров телефонов](./phone-number-calling-plans/port-order-overview.md)

[Типы номеров телефонов, используемые в планах звонков](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Управление номерами телефонов организации](/microsoftteams/manage-phone-numbers-for-your-organization)

[Дополнительные сведения об идентификаторе вызывающей линии и имени вызывающего абонента](/skypeforbusiness/what-are-calling-plans-in-office-365/more-about-calling-line-ID-and-calling-party-name)

[Условия и положения, распространяющиеся на экстренные вызовы](./emergency-calling-terms-and-conditions.md)

[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
