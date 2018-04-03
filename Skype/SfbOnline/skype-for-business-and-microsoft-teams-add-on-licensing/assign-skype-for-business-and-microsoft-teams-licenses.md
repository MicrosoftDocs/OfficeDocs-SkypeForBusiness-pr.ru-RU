---
title: Назначение лицензий Skype для бизнеса и Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.date: 01/22/2018
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
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
- Licensing
- Strat_SB_PSTN
description: 'Узнайте, как назначить Скайп для бизнеса лицензий для телефонной системой, звук конференц-связи, вызов планы и кредитов коммуникаций. '
ms.openlocfilehash: 12a26dc7b9ebd47ae10005afb66f23a8cb278237
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2018
---
# <a name="assign-skype-for-business-and-microsoft-teams-licenses"></a>Назначение лицензий Skype для бизнеса и Microsoft Teams

В этой статье приводятся советы назначение лицензий пользователям для таких функций, как аудиоконференции, телефонной системой и вызов планов. Он также предоставляет сценарии для назначения лицензий в пакетном режиме.
  
 **Важно**: см. [Скайп для бизнеса и группами Майкрософт дополнительный компонент лицензирования](skype-for-business-and-microsoft-teams-add-on-licensing.md) для получения сведений о что лицензируемые вам необходимо купить и **как приобрести** их - в зависимости от плана Office 365 — так что пользователи получают звук конференц-связи, обслуживание бесплатных номеров и возможность звонить по номерам за пределами вашей организации.
  
## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Телефонные системы и планы звонков. Советы и сценарии по назначению лицензий

Что нужно знать, прежде чем назначение аудиоконференции, телефонной системой и вызов планирование лицензий

- **При использовании локальных подключений ТСОП для пользователей в гибридных средах** необходимо назначить только лицензию на **телефонную систему**. Назначать план звонков **НЕ НУЖНО**.
    
- **Задержка после назначения лицензий**: из-за задержки между Office 365 и Скайп для бизнеса в Интернет, возможно может потребоваться до 24 часов для пользователя, чтобы назначить вызов планирование после назначении лицензии. Если после 24 часов пользователя не будет назначен вызов планирование, пожалуйста, [обращение в службу поддержки продуктов бизнес - Admin справки](http://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
    
- **Сообщения об ошибках**. Если приобретено неправильное число лицензий, выдается сообщение об ошибке. Если требуется приобрести дополнительные лицензии на планы звонков, щелкните **Купить еще**.
    
- **Дальнейшие действия**: после назначения лицензий на вызов планирование для пользователей, необходимо получить номера телефонов для вашей организации, а затем назначить эти номера для пользователей в вашей организации. Для получения пошаговых инструкций см [вызов планов](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Назначение лицензии на телефонную систему и план звонков одному пользователю

Шаги совпадают с шагами при назначении лицензии на Office 365. См. раздел [Управление лицензиями Office 365 бизнес](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Массовое назначение лицензий на телефонную систему и план звонков

1. Установка **Microsoft Online Services помощник по входу для ИТ-специалистов RTW**. Не установлен модуль? В разделе [Microsoft Online Services помощника по входу для RTW специалистам ИТ](https://go.microsoft.com/fwlink/?LinkId=625123) для его загрузки.
    
2. Установка **модуль Windows Azure Active Directory.** Не установлен модуль? В разделе [Управление Azure AD, с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) синтаксис командлета и инструкции по загрузке.
    
3. После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.
    
  В этом примере **лицензия "Корпоративный E3"** назначается вместе с лицензией на **телефонную систему** и **план внутренних звонков**.
    
  Названия лицензий и наименования продуктов в сценарии выделены курсивом. См. раздел **Названия продуктов и номера SKU для телефонной системы и плана звонков, используемые для сценариев** после примера.
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
  
  #Example of text file:
  #user1@domain.com
  #user2@domain.com
  
  #Import Module
  ipmo MSOnline
  #Authenticate to MSOLservice.
  Connect-MSOLService
  #File prompt to select the userlist txt file.
  [System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
  $OFD = New-Object System.Windows.Forms.OpenFileDialog
  $OFD.filter = "text files (*.*)| *.txt"
  $OFD.ShowDialog() | Out-Null
  $OFD.filename
  If ($OFD.filename -eq '')
  {
    Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
  }
  #Create a variable of all users.
  $users = Get-Content $OFD.filename
  #License each user in the $users variable.
  #Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and
  International Calling.
  for each ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    } 
  ```
### <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Названия продуктов и номера SKU для телефонной системы и плана звонков, использующиеся для сценариев

|**Наименование товара**|**Наименование товарной единицы**|
|:-----|:-----|
|Корпоративный E5 (с телефонной системой)  <br/> |ENTERPRISEPREMIUM  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Skype для бизнеса Online Standalone Plan 2  <br/> |MCOSTANDARD  <br/> |
|Телефонная система  <br/> |MCOEV  <br/> |
|План международных звонков  <br/> |MCOPSTN2  <br/> |
|План внутренних звонков  <br/> |MCOPSTN1  <br/> |
|Кредиты на связь  <br/> |MCOPSTNPP  <br/> |
   
## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Аудиоконференция. Советы и сценарии для назначения лицензий

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>Что нужно знать перед назначением лицензий на аудиоконференцию

- **Сторонний поставщик аудиоконференций**. Если для пользователя уже настроено использование стороннего поставщика аудиоконференций, при назначении ему лицензии на **аудиоконференцию** поставщиком аудиоконференций автоматически назначается Майкрософт, но вы можете снова задать стороннего поставщика.
    
- Дальнейшие действия: после назначения лицензий **Аудиоконференций** , им необходимо назначить поставщика аудиоконференций. В разделе [назначение Microsoft в качестве поставщика аудиоконференций].
    
### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Назначение лицензии на аудиоконференции одному пользователю

Шаги совпадают с шагами при назначении лицензии на Office 365. См. раздел [Управление лицензиями Office 365 бизнес](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Массовое назначение лицензий на аудиоконференции

1. Скачайте и установите [Помощник по входу в Microsoft Online Services для ИТ-специалистов, версия RTW ](https://go.microsoft.com/fwlink/?LinkId=625123).
    
2. Загрузите и установите **модуль Windows Azure Active Directory**. Инструкции по установке и синтаксис командлетов см. в разделе[Управление службой Azure AD с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).
    
    После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.
    
    Имя лицензии или названия продуктов в скрипте, перечислены в текста курсивом. В разделе [имена аудиоконференции продукта или номера SKU, используемый для скриптов](assign-skype-for-business-and-microsoft-teams-licenses.md#sku) для всех названия продуктов.
    
    В этом примере лицензия "Корпоративный E3" назначается вместе с лицензией на аудиоконференцию.
    
```
#Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
#Example of text file:
#user1@domain.com
#user2@domain.com

#Import Module
ipmo MSOnline

#Authenticate to MSOLservice
Connect-MSOLService
#File prompt to select the userlist txt file
[System.Reflection.Assembly]::LoadWithPartialName("System.windows.forms") | Out-Null
  $OFD = New-Object System.Windows.Forms.OpenFileDialog
  $OFD.filter = "text files (*.*)| *.txt"
  $OFD.ShowDialog() | Out-Null
  $OFD.filename

If ($OFD.filename -eq '')
{
Write-Host "You did not choose a file. Try again" -ForegroundColor White -BackgroundColor Red
}

#Create a variable of all users
$users = Get-Content $OFD.filename

#License each user in the $users variable
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOMEETADV " -ErrorAction SilentlyContinue
    } 
```

### <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Названия продуктов и номера SKU для аудиоконференций, использующихся для сценариев
<a name="sku"> </a>

|**Наименование товара**|**Наименование товарной единицы**|
|:-----|:-----|
|Аудиоконференция  <br/> |MCOMEETADV  <br/> |
|Skype для бизнеса Online Standalone Plan 2  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Корпоративный E5 (без аудиоконференции)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Корпоративный E5 (с аудиоконференцией)  <br/> |ENTERPRISEPREMIUM  <br/> |
   
## <a name="communications-credits"></a>Кредиты на связь

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>Что нужно знать перед назначением лицензий на кредиты на связь

- **E5 корпоративных клиентов**: даже в том случае, если пользователи назначаются E5 корпоративных лицензий, все же рекомендуется назначить их **Кредитов Communications** лицензий.
    
- **Дальнейшие действия**: после назначить эти лицензии, необходимо получить номера телефонов для вашей организации, а затем назначить эти номера для пользователей в вашей организации. Для получения пошаговых инструкций см [вызов планов](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Назначение лицензии на кредиты на связь одному пользователю

Шаги совпадают с шагами при назначении лицензии на Office 365. См. раздел [Управление лицензиями Office 365 бизнес](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Назначение лицензий кредитов коммуникаций в пакетном режиме

Ознакомьтесь с примером сценария для назначения лицензий на **аудиоконференции**. Обновите сведения для назначения лицензий на **кредиты на связь**.
  
## <a name="related-topics"></a>See also
  
[Настройка планов звонков](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[Добавление средств и управление кредитами на связь](add-funds-and-manage-communications-credits.md)
  
  
 