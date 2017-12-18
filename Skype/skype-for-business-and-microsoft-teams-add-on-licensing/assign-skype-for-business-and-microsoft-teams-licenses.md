---
title: "Назначение лицензий Skype для бизнеса и Microsoft Teams"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/20/2017
ms.audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom:
- Adm_O365_FullSet
- DianeF_Adm_Simplified
- Strat_SB_PSTN
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
description: "Learn how to assign Skype for Business licenses for Cloud PBX, PSTN Conferencing, PSTN Calling, and PSTN Consumption. "
---

# Назначение лицензий Skype для бизнеса и Microsoft Teams

> [!IMPORTANT]
> Данная статья переведена с помощью машинного перевода, см. Отказ от ответственности.  
  
В этой статье вы найдете советы о назначении лицензий пользователей для функции, такие как аудиоконференций телефонной системой и вызвав планы. Он также предоставляет сценарии для назначения лицензий в групповом режиме.
  
 **Важно**: см[Лицензирование надстроек Skype для бизнеса и Microsoft Teams](skype-for-business-and-microsoft-teams-add-on-licensing.md) сведения о что предоставляет лицензии нужно купить и **приобретение** ими, в зависимости от вашего плана Office 365  так что пользователи получают аудиоконференций, бесплатные номера и Вы можете звонить по номерам за пределами вашей организации.
  
## Телефонные системы и планы звонков. Советы и сценарии по назначению лицензий

### Что необходимо знать, прежде чем назначать аудиоконференций, телефонной системой и вызвав планирование лицензий

- **ВАЖНО!** Чтобы в левой области навигации Центра администрирования Skype для бизнеса появился элемент **Голосовая связь**, необходимо приобрести хотя бы одну **лицензию уровня корпоративный E5**, лицензию на надстройку **Телефонная система** либо лицензию на надстройку **Аудиоконференция**.
    
- **При использовании локальных подключений ТСОП для пользователей в гибридных средах** необходимо назначить только лицензию на **телефонную систему**. Назначать план звонков **НЕ НУЖНО**.
    
- **Задержка после назначения лицензии**: из-за задержки между Office 365 и Skype для бизнеса online, возможного может потребоваться до 24 часов для пользователя, чтобы назначить вызов планировать после назначения лицензии. Если через сутки пользователя не назначены вызов планировать, пожалуйста,[Обращение в службу поддержки Office 365 для бизнеса: справка для администраторов](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).
    
- **Сообщения об ошибках**. Если приобретено неправильное число лицензий, выдается сообщение об ошибке. Если требуется приобрести дополнительные лицензии на планы звонков, щелкните **Купить еще**.
    
- **Дальнейшие действия**. После назначения указанных лицензий на планы звонков вам потребуется получить номера телефонов для организации, а затем назначить их сотрудникам. Пошаговые инструкции по настройке см. в статье[Настройка планов звонков](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### Назначение лицензии на телефонную систему и план звонков одному пользователю

Действия будут так же, как назначения лицензии Office 365. Просмотреть [Управление лицензиями Office 365 бизнес](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### Массовое назначение лицензий на телефонную систему и план звонков

1. Установите **Помощник по входу в Microsoft Online Services для ИТ-специалистов, версия RTW**. Модуль не установлен? Инструкции по скачиванию см. в разделе[Помощник по входу в Microsoft Online Services для ИТ-специалистов, версия RTW](https://go.microsoft.com/fwlink/?LinkId=625123).
    
2. Установите **модуль Windows Azure Active Directory**. Модуль не установлен? Инструкции по установке и синтаксис командлетов см. в разделе[Управление службой Azure AD с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).
    
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
#Use MCOPSTN1 for PSTN Domestic Calling and MCOPSTN2 for Domestic and International Calling.
foreach ($user in $users)
    {
    Write-host "Assigning License: $user"
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:ENTERPRISEPACK " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOEV " -ErrorAction SilentlyContinue
    Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "companyname:MCOPSTN1 " -ErrorAction SilentlyContinue
    } 

  ```

### Названия продуктов и номера SKU для телефонной системы и плана звонков, использующиеся для сценариев

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
   
## Аудиоконференция. Советы и сценарии для назначения лицензий

### Что нужно знать перед назначением лицензий на аудиоконференцию

- **Сторонний поставщик аудиоконференций**. Если для пользователя уже настроено использование стороннего поставщика аудиоконференций, при назначении ему лицензии на **аудиоконференцию** поставщиком аудиоконференций автоматически назначается Майкрософт, но вы можете снова задать стороннего поставщика.
    
- Дальнейшие действия: после назначения лицензий **Аудиоконференций** необходимо назначить к поставщику услуг аудиоконференций. Выполните одно из указанных ниже действий.
    
  - [Назначение Майкрософт в качестве поставщика услуг аудиоконференций](../audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider.md)
    
  - Или [Назначение стороннего поставщика услуг аудиоконференций](../audio-conferencing-in-office-365/assign-a-third-party-as-the-audio-conferencing-provider.md)
    
### Назначение лицензии на аудиоконференции одному пользователю

Действия будут так же, как назначения лицензии Office 365. Просмотреть [Управление лицензиями Office 365 бизнес](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### Массовое назначение лицензий на аудиоконференции

1. Скачайте и установите [Помощник по входу в Microsoft Online Services для ИТ-специалистов, версия RTW ](https://go.microsoft.com/fwlink/?LinkId=625123).
    
2. Загрузите и установите **модуль Windows Azure Active Directory**. Инструкции по установке и синтаксис командлетов см. в разделе[Управление службой Azure AD с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628).
    
    После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.
    
    Имя лицензий или названия продуктов в сценарии будут включены в текст курсивом. В разделе [Названия продуктов и номера SKU для аудиоконференций, использующихся для сценариев](fd41934d-f2eb-4a1b-89d8-32cb37702b33.md#sku) для всех названий продуктов.
    
    В этом примере лицензия "Корпоративный E3" назначается вместе с лицензией на аудиоконференцию.
    
  ```
  #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Office 365.
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

### Названия продуктов и номера SKU для аудиоконференций, использующихся для сценариев
<a name="sku"> </a>

|**Наименование товара**|**Наименование товарной единицы**|
|:-----|:-----|
|Аудиоконференция  <br/> |MCOMEETADV  <br/> |
|Skype для бизнеса Online Standalone Plan 2  <br/> |MCOSTANDARD  <br/> |
|Enterprise E1  <br/> |STANDARDPACK  <br/> |
|Enterprise E3  <br/> |ENTERPRISEPACK  <br/> |
|Корпоративный E5 (без аудиоконференции)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Корпоративный E5 (с аудиоконференцией)  <br/> |ENTERPRISEPREMIUM  <br/> |
   
## Кредиты на связь

### Что нужно знать перед назначением лицензий на кредиты на связь

- **E5 корпоративных клиентов**: даже если пользователей назначаются E5 корпоративные лицензии, по-прежнему рекомендуется назначить им лицензии **Кредиты связи**.
    
- **Дальнейшие действия**. После назначения указанных лицензий вам потребуется получить номера телефонов для организации, а затем назначить их сотрудникам. Пошаговые инструкции по настройке см. в статье[Настройка планов звонков](../what-are-calling-plans-in-office-365/set-up-calling-plans.md).
    
### Назначение лицензии на кредиты на связь одному пользователю

Действия будут так же, как назначения лицензии Office 365. Просмотреть [Управление лицензиями Office 365 бизнес](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
  
### Как назначить лицензии кредиты связи в групповом режиме

Ознакомьтесь с примером сценария для назначения лицензий на **аудиоконференции**. Обновите сведения для назначения лицензий на **кредиты на связь**.
  
## Статьи по теме

[Настройка аудиоконференций в Skype для бизнеса и Microsoft Teams](../audio-conferencing-in-office-365/set-up-audio-conferencing-for-skype-for-business-and-microsoft-teams.md)
  
[Настройка планов звонков](../what-are-calling-plans-in-office-365/set-up-calling-plans.md)
  
[Добавление фондов и управление ими кредиты связи](add-funds-and-manage-communications-credits.md)
  
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Отказ от ответственности относительно машинного перевода**. Данная статья была переведена с помощью компьютерной системы без участия человека. Microsoft предлагает эти машинные переводы, чтобы помочь пользователям, которые не знают английского языка, ознакомиться с материалами о продуктах, услугах и технологиях Microsoft. Поскольку статья была переведена с использованием машинного перевода, она может содержать лексические,синтаксические и грамматические ошибки. 
  

