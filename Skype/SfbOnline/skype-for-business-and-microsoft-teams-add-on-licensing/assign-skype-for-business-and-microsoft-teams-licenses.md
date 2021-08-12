---
title: Назначение лицензий Skype для бизнеса
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav
ms.topic: article
ms.assetid: fd41934d-f2eb-4a1b-89d8-32cb37702b33
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Licensing
description: 'Узнайте, как назначить лицензии Skype для бизнеса на телефонные системы, аудиоконференции, планы звонков и кредиты на связь. '
ms.openlocfilehash: 61d8eca21fec85f7f729e0d0de9cc5d43fd5ca96567e2abe49cf7b6b5f651500
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/05/2021
ms.locfileid: "54281332"
---
# <a name="assign-skype-for-business-licenses"></a>Назначение лицензий Skype для бизнеса

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

В этой статье представлены советы по назначению пользователям лицензий на такие функции, как аудиоконференция, телефонная система и планы звонков. Здесь также представлены сценарии для массового назначения лицензий.

> [!IMPORTANT]
> Сведения [о Skype для бизнеса](skype-for-business-and-microsoft-teams-add-on-licensing.md) лицензиях и их покупке в зависимости  от плана Microsoft 365 или Office 365 см. в Microsoft 365- или Office 365, чтобы пользователи могли получать аудиоконференцию, бесплатные номера и возможность звонить на номера телефонов за пределами вашей компании.


## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Телефонные системы и планы звонков. Советы и сценарии по назначению лицензий

Что необходимо знать перед назначением лицензий на аудиоконференцию, телефонная система и план звонков

- **При использовании локальных подключений ТСОП для пользователей в гибридных средах** необходимо назначить только лицензию на **телефонную систему**. Назначать план звонков **НЕ НУЖНО**.

- **Задержка** после назначения лицензий: из-за задержки между Microsoft 365 или Office 365 и Skype для бизнеса Online назначение пользователю плана звонков после назначения лицензии может занять до 24 часов. Если по прошествии 24 часов пользователю не назначен план звонков, пожалуйста, выполните [Обращение в службу поддержки Office 365 для бизнеса: справка для администраторов](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Сообщения об ошибках**. Если приобретено неправильное число лицензий, выдается сообщение об ошибке. Если требуется приобрести дополнительные лицензии на планы звонков, щелкните **Купить еще**.
    
- **Дальнейшие действия.** После назначения пользователям лицензий на план звонков вам потребуется получить номера телефонов для организации, а затем назначить их пользователям в организации. Пошаговые инструкции см. в статье [Настройка планов звонков](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Назначение лицензии на телефонную систему и план звонков одному пользователю

Действия такие же, как назначение лицензии Microsoft 365 или Office 365 лицензии. См. [назначение и удаление лицензий Microsoft 365 для бизнеса.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Массовое назначение лицензий на телефонную систему и план звонков

1. Установите **Microsoft Online Services Sign-In для ИТ-специалистов RTW.** Не установлен модуль? Загрузите его со страницы [Помощника по входу в Microsoft Online Services для ИТ-специалистов, версия RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Установите **модуль Windows Azure Active Directory.** Не установлен модуль? Перейдите в раздел [Управление Azure AD с помощью Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)) для ознакомления с инструкцией по загрузки и синтаксисом командлета.

3. После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.

   В этом примере **лицензия "Корпоративный E3"** назначается вместе с лицензией на **телефонную систему** и **план внутренних звонков**.

   Названия лицензий и наименования продуктов в сценарии выделены курсивом. См. раздел **Названия продуктов и номера SKU для телефонной системы и плана звонков, используемые для сценариев** после примера.

   ```powershell
   #Create a text file with a single row containing list of UserPrincipalName (UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.

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
|Корпоративный E3  <br/> |ENTERPRISEPACK  <br/> |
|Корпоративный E1  <br/> |STANDARDPACK  <br/> |
|Skype для бизнеса Online Standalone Plan 2  <br/> |MCOSTANDARD  <br/> |
|Телефонная система  <br/> |MCOEV  <br/> |
|План международных звонков  <br/> |MCOPSTN2  <br/> |
|План внутренних звонков (3000 мин США / 1200 мин планов ЕС)  <br/> |MCOPSTN1  <br/> |
|План внутренних звонков (план звонков на 120 минут)  <br/> |MCOPSTN5  <br/> |
|План внутренних звонков (план звонков на 240 минут)  <br/> |MCOPSTN6  <br/> |
|Кредиты на связь  <br/> |MCOPSTNC  <br/> |

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Аудиоконференция. Советы и сценарии для назначения лицензий

### <a name="what-you-need-to-know-before-assigning-audio-conferencing-licenses"></a>Что нужно знать перед назначением лицензий на аудиоконференцию

- **Сторонний поставщик аудиоконференций**. Если для пользователя уже настроено использование стороннего поставщика аудиоконференций, при назначении ему лицензии на **аудиоконференцию** поставщиком аудиоконференций автоматически назначается Майкрософт, но вы можете снова задать стороннего поставщика.

- Дальнейшие действия. После  назначения лицензий на аудиоконференцию необходимо назначить поставщика услуг аудиоконференций. См. [Назначение Майкрософт в качестве поставщика услуг аудиоконференций].

### <a name="how-to-assign-an-audio-conferencing-license-to-one-user"></a>Назначение лицензии на аудиоконференции одному пользователю

Действия такие же, как назначение лицензии Microsoft 365 или Office 365 лицензии. См. [назначение и удаление лицензий Microsoft 365 для бизнеса.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-audio-conferencing-licenses-in-bulk"></a>Массовое назначение лицензий на аудиоконференции

1. Скачайте и установите [Помощник по входу в Microsoft Online Services для ИТ-специалистов, версия RTW ](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Загрузите и установите **модуль Windows Azure Active Directory**. Инструкции по установке и синтаксис командлетов см. в разделе [Управление службой Azure AD с помощью Windows PowerShell](/previous-versions/azure/jj151815(v=azure.100)).

    После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.

    Названия лицензий или названий продуктов в сценарии указаны в тексте написания. Полный перечень названий продуктов см. в разделе [Названия продуктов и номера SKU для аудиоконференций, использующихся для сценариев](assign-skype-for-business-and-microsoft-teams-licenses.md#sku).

    В этом примере лицензия "Корпоративный E3" назначается вместе с лицензией на аудиоконференцию.

    ```powershell
    #Create a text file with a single row containing list of UserPrincipalName(UPN) of users to license. The MSOLservice uses UPN to license user accounts in Microsoft 365 or Office 365.
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
|Корпоративный E1  <br/> |STANDARDPACK  <br/> |
|Корпоративный E3  <br/> |ENTERPRISEPACK  <br/> |
|Корпоративный E5 (без аудиоконференции)  <br/> |ENTERPRISEPREMIUM_NOPSTNCONF  <br/> |
|Корпоративный E5 (с аудиоконференцией)  <br/> |ENTERPRISEPREMIUM  <br/> |

## <a name="communications-credits"></a>Кредиты на связь

### <a name="what-you-need-to-know-before-assigning-communications-credits-licenses"></a>Что нужно знать перед назначением лицензий на кредиты на связь

- **Enterprise E5:** даже если пользователям назначены лицензии на Enterprise E5, мы по-прежнему  рекомендуем назначать им лицензии на кредиты на связь.
    
- **Дальнейшие действия.** После назначения этих лицензий вам потребуется получить номера телефонов для организации, а затем назначить их людям в организации. Пошаговые инструкции см. в статье [Настройка планов звонков](/microsoftteams/set-up-calling-plans).
    
### <a name="how-to-assign-a-communications-credits-license-to-one-user"></a>Назначение лицензии на кредиты на связь одному пользователю

Действия такие же, как назначение лицензии Microsoft 365 или Office 365 лицензии. См. [назначение и удаление лицензий Microsoft 365 для бизнеса.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

### <a name="how-to-assign-communications-credits-licenses-in-bulk"></a>Массовое назначение лицензий на кредиты на связь

Ознакомьтесь с примером сценария для назначения лицензий на **аудиоконференции**. Обновите сведения для назначения лицензий на **кредиты на связь**.

## <a name="related-topics"></a>Статьи по теме
  
[Настройка планов звонков](/microsoftteams/set-up-calling-plans)
  
[Пополнение средств и управление кредитами на связь](/microsoftteams/add-funds-and-manage-communications-credits)
  
  
