---
title: Назначение лицензий Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
audience: ITPro
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
search.appverid: MET150
ms.reviewer: mikedav
description: Сведения о назначении лицензий для таких функций, как голосовая конференция, телефонная система и планы звонков.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e5783a2fa0c6479d59e563b9001b736015f20fa
ms.sourcegitcommit: 5695ce88d4a6a8fb9594df8dd1c207e45be067be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/15/2019
ms.locfileid: "37515784"
---
# <a name="assign-microsoft-teams-licenses"></a>Назначение лицензий Microsoft Teams

Вы можете назначать лицензии пользователям для таких функций, как голосовая конференция, телефонная система и планы звонков. В этой статье объясняется, как добавить эти лицензии в массовый и для отдельного пользователя. 

> [!IMPORTANT]
> Сведения о лицензиях на [надстройки Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) , которые нужно приобрести, и о том, как их приобрести, в зависимости от вашего плана Office 365, чтобы пользователи могли получать видеоконференции, бесплатные номера и возможность звонить на телефонные номера за пределами вашего бизнеса.

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Телефонные системы и планы звонков. Советы и сценарии по назначению лицензий

Ниже приведены сведения, которые необходимо знать перед назначением лицензий на голосовую конференцию, телефонную систему и план звонков.

- **Используете локальную сеть PSTN для гибридных пользователей?** Если да, вам нужно назначить лицензию на телефонную систему. НЕ следует назначать план звонков.

- **Задержка после назначения лицензий**. из-за задержки между Office 365 и Microsoft Teams для назначения абоненту плана после назначения лицензии может потребоваться до 24 часов. Если по истечении 24 часов пользователь не назначил план звонков, [обратитесь в службу поддержки для бизнес-продуктов — Справка для администраторов](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Сообщения об ошибках**. Если приобретено неправильное число лицензий, выдается сообщение об ошибке. Если требуется приобрести дополнительные лицензии на планы звонков, щелкните **Купить еще**.

- **Дальнейшие действия**: после назначения пользователям лицензий на план звонков вам потребуется получить номера телефонов для своей организации, а затем назначить эти номера сотрудникам Организации. Пошаговые инструкции см. в статье [Настройка планов звонков](set-up-calling-plans.md).

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Назначение лицензии на телефонную систему и план звонков для одного пользователя

Эти действия такие же, как назначение лицензии на Office 365. Ознакомьтесь с [Разназначением и удалением лицензий для Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Массовое Назначение лицензий на телефонную систему и план звонков

1. Установка помощника по входу в Microsoft Online Services для ИТ-специалистов RTW. Не установлен модуль? Загрузите его со страницы [Помощника по входу в Microsoft Online Services для ИТ-специалистов, версия RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Установите модуль Windows Azure Active Directory. Не установлен модуль? Перейдите в раздел [Управление Azure AD с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) для ознакомления с инструкцией по загрузки и синтаксисом командлета.

3. После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.

В этом примере лицензия "Корпоративный E3" назначается вместе с лицензией на телефонную систему и план внутренних звонков.

Названия лицензий и названий продуктов в сценарии выводятся курсивом (в этом примере [используются названия продуктов и номера SKU, используемые для создания сценариев, в телефонной системе и в планах звонков](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting)).

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
## <a name="phone-system-and-calling-plans-product-names-or-skus-used-for-scripting"></a>Названия продуктов и номера SKU для телефонной системы и плана звонков, использующиеся для сценариев

| Наименование товара | Наименование товарной единицы |
|--------------|---------------|
| Корпоративный E5 (с телефонной системой) | ENTERPRISEPREMIUM |
| Корпоративный E3 | ENTERPRISEPACK | 
| Корпоративный E1 | STANDARDPACK | 
| Телефонная система | MCOEV |
| План международных звонков на внутренние & | MCOPSTN2 |
| План внутренних вызовов (3000 минут на пользователя/месяц для US/PR/CA, 1200 минут на пользователя/месяц для стран ЕС) | MCOPSTN1 |
| План внутренних вызовов (120 минут на пользователя/месяц для каждой страны) </br>*Примечание. Этот план недоступен в США*. | MCOPSTN5 |
| План внутренних вызовов (240 минут на пользователя/месяц для каждой страны) </br>*Примечание. Этот план недоступен в США*. | MCOPSTN6 |
| Кредиты на связь | MCOPSTNPP | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Аудио-конференции: советы и сценарии для назначения лицензий

Ниже приведены сведения, которые необходимо знать перед назначением лицензий на голосовую конференцию.

- **Сторонние поставщики видеоконференций**: если кто-то уже настроен на использование стороннего поставщика видеоконференций, при назначении лицензии на голосовую конференцию, она будет изменена на использование Microsoft в качестве поставщика голосовой связи. Если для пользователя уже настроено использование стороннего поставщика аудиоконференций, при назначении ему лицензии на аудиоконференцию поставщиком аудиоконференций автоматически назначается Майкрософт, но вы можете снова задать стороннего поставщика.

- **Дальнейшие действия**: после назначения лицензий на голосовую конференцию необходимо назначить поставщика услуг голосовой связи. [В разделе Назначение Microsoft в качестве поставщика звуковых конференций](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>Назначение лицензии на голосовую конференцию для одного пользователя

Эти действия такие же, как назначение лицензии на Office 365. Ознакомьтесь с [Разназначением и удалением лицензий для Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>Массовое Назначение лицензий на голосовую конференцию

1. Скачайте и установите [Помощник по входу в Microsoft Online Services для ИТ-специалистов, версия RTW ](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Скачайте и установите модуль Windows Azure Active Directory. Перейдите в раздел [Управление Azure AD с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) для ознакомления с инструкцией по загрузки и синтаксисом командлета.

После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.

Названия лицензий и названий продуктов в сценарии выводятся курсивом. Посмотрите [названия продуктов и SKU для голосовой связи, которые используются для создания сценариев](#audio-conferencing-product-names-or-skus-used-for-scripting) для всех названий продуктов.

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Названия и номера продуктов для голосовой конференции, используемые для создания сценариев

| Наименование товара | Наименование товарной единицы |
|--------------|---------------|
| Голосовая конференция (подписка) | MCOMEETADV | 
| Оплата для голосовой конференции за минуту (оплата за один звонок)</br>*Примечание. требует настройки и включения кредитов на связь*. | мкомитакпеа |
| Корпоративный E1 | STANDARDPACK | 
| Корпоративный E3 | ENTERPRISEPACK |
| Корпоративный E5 (без аудиоконференции) |  ENTERPRISEPREMIUM_NOPSTNCONF |
| Корпоративный E5 (с аудиоконференцией) | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>Кредиты на связь

Вот что нужно знать перед назначением лицензий на кредиты на связь.

- **Клиенты с корпоративным**энергообщением: даже если вашим пользователям назначены лицензии на ресурсы в корпоративной среде, мы по-прежнему рекомендуем назначать им лицензии на передачу данных.

- **Дальнейшие действия**: после назначения этих лицензий вам потребуется получить номера телефонов для своей организации, а затем назначить эти номера сотрудникам Организации. Пошаговые инструкции см. в статье [Настройка планов звонков](set-up-calling-plans.md).

## <a name="assign-a-communications-credits-license-to-one-user"></a>Назначение лицензии на пересылаемые баллы для одного пользователя

Эти действия такие же, как назначение лицензии на Office 365. Ознакомьтесь с [Разназначением и удалением лицензий для Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-communications-credits-licenses-in-bulk"></a>Массовое Назначение лицензий на кредиты на связь

Ознакомьтесь с примером сценария для назначения лицензий на аудиоконференции. Обновите сведения для назначения лицензий на кредиты на связь.

## <a name="related-topics"></a>Статьи по теме

[Настройка планов звонков](set-up-calling-plans.md)
</br>
[Пополнение средств и управление кредитами на связь](add-funds-and-manage-communications-credits.md)
