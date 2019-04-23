---
title: Назначение лицензий Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 12/14/2018
ms.topic: article
ms.service: msteams
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
ms.reviewer: mikedav
description: Узнайте, как для назначения лицензий для функции, такие как аудио конференц-связи, телефонной системой и планы вызова.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 46966b7cad855ef6336b501564cde89dffd6b2b2
ms.sourcegitcommit: 920a7dbdc2a0ede94d0a4bd573c01a1ccd838b7e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "31993631"
---
# <a name="assign-microsoft-teams-licenses"></a>Назначение лицензий группами Майкрософт

Можно назначить лицензий пользователей для таких функций, как аудиоконференции, телефонной системой и вызов планов. В этой статье объясняется, как добавить эти лицензии в пакетном режиме, а также для отдельных пользователей. 

> [!IMPORTANT]
> [Лицензирование дополнительный компонент группами Майкрософт](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) сведения о см что планирование лицензий, которые необходимо приобрести и как приобрести их, в зависимости от Office 365, так что пользователи получают аудиоконференции, обслуживание бесплатных номеров и возможность вызова телефонных номеров за пределами вашей организации.

## <a name="phone-system-and-calling-plans-tips-and-scripts-for-assigning-licenses"></a>Телефонные системы и планы звонков. Советы и сценарии по назначению лицензий

Вот что нужно знать, прежде чем назначения лицензий аудиоконференции, телефонной системой и вызов планирование.

- **С помощью локального подключения к ТСОП для гибридных пользователей?** Если Да, необходимо назначить лицензию телефонной системой. НЕ следует назначить вызов планирование.

- **Задержка после назначения лицензий**: из-за задержки между Office 365 и группами Майкрософт, может потребоваться до 24 часов для пользователя, чтобы назначить вызов планирование после назначении лицензии. Если после 24 часов пользователя не будет назначен вызов планирование, пожалуйста, [обратитесь в службу поддержки продуктов бизнес - admin справки](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- **Сообщения об ошибках**. Если приобретено неправильное число лицензий, выдается сообщение об ошибке. Если требуется приобрести дополнительные лицензии на планы звонков, щелкните **Купить еще**.

- **Дальнейшие действия**: после назначения лицензий на вызов планирование для пользователей, необходимо получить номера телефонов для вашей организации, а затем назначить эти номера для пользователей в вашей организации. Пошаговые инструкции см. в статье [Настройка планов звонков](set-up-calling-plans.md).

## <a name="assign-a-phone-system-and-calling-plan-license-to-one-user"></a>Назначить телефонной системой и вызов планирование лицензию для одного пользователя

Действия такие же, как назначение лицензии Office 365. Просмотрите [Назначение и удаление лицензий на Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-phone-system-and-calling-plan-licenses-in-bulk"></a>Назначение лицензий телефонной системой и вызов планирование в пакетном режиме

1. Установка Microsoft Online Services помощник по входу для ИТ-специалистов RTW. Не установлен модуль? Загрузите его со страницы [Помощника по входу в Microsoft Online Services для ИТ-специалистов, версия RTW](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Установите модуль Windows Azure Active Directory. Не установлен модуль? Перейдите в раздел [Управление Azure AD с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) для ознакомления с инструкцией по загрузки и синтаксисом командлета.

3. После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.

В этом примере лицензия "Корпоративный E3" назначается вместе с лицензией на телефонную систему и план внутренних звонков.

Имя лицензии или названия продуктов в скрипте, перечислены в курсив (см [телефонной системой и вызов планы названия продуктов или номера SKU, используемые для выполнения сценариев](#phone-system-and-calling-plans-product-names-or-skus-used-for-scripting), после примера).

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
| Планирование международных звонков внутри страны & | MCOPSTN2 |
| Внутренний вызов планирование (3000 минут на пользователя в месяц для США/связей с Общественностью/центра сертификации, 1200 минут в месяц пользователя для стран ЕС) | MCOPSTN1 |
| Внутренний вызов планирование (120 минут в месяц пользователя для каждой страны) </br>*Примечание: этот план не доступен в США*. | MCOPSTN5 |
| Внутренний вызов планирование (240 минут в месяц пользователя для каждой страны) </br>*Примечание: этот план не доступен в США*. | MCOPSTN6 |
| Кредиты на связь | MCOPSTNPP | 

## <a name="audio-conferencing-tips-and-scripts-for-assigning-licenses"></a>Конференции: советы и сценарии для назначения лицензий

Вот что нужно знать, прежде чем назначения лицензий звук конференц-связи.

- **Стороннего поставщика аудиоконференций**: Если кто-то уже настроен на использование поставщика аудиоконференций сторонних производителей, при их назначения лицензию на аудиоконференции, они будут изменены для использования Microsoft в качестве поставщика аудиоконференций. Если для пользователя уже настроено использование стороннего поставщика аудиоконференций, при назначении ему лицензии на аудиоконференцию поставщиком аудиоконференций автоматически назначается Майкрософт, но вы можете снова задать стороннего поставщика.

- **Дальнейшие действия**: после назначения лицензий аудиоконференций, им необходимо назначить поставщика аудиоконференций. В разделе [Назначение Microsoft в качестве поставщика аудиоконференций](https://docs.microsoft.com/skypeforbusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

## <a name="assign-an-audio-conferencing-license-to-one-user"></a>Назначение лицензии на аудиоконференции для одного пользователя

Действия такие же, как назначение лицензии Office 365. Просмотрите [Назначение и удаление лицензий на Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-audio-conferencing-licenses-in-bulk"></a>Назначение лицензий аудиоконференции в пакетном режиме

1. Скачайте и установите [Помощник по входу в Microsoft Online Services для ИТ-специалистов, версия RTW ](https://go.microsoft.com/fwlink/?LinkId=625123).

2. Загрузите и установите модуль Windows Azure Active Directory. Перейдите в раздел [Управление Azure AD с помощью Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=320628) для ознакомления с инструкцией по загрузки и синтаксисом командлета.

После установки модулей назначьте пользователям лицензии с помощью командной строки Windows PowerShell и следующего синтаксиса.

Имя лицензии или названия продуктов в скрипте, перечислены в курсив. В разделе [имена аудиоконференции продукта или номера SKU, используемый для скриптов](#audio-conferencing-product-names-or-skus-used-for-scripting) для всех названия продуктов.

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
## <a name="audio-conferencing-product-names-or-skus-used-for-scripting"></a>Названия продуктов звукового конференц-связи или номера SKU, используемый для скриптов

| Наименование товара | Наименование товарной единицы |
|--------------|---------------|
| Аудиоконференций (подписка) | MCOMEETADV | 
| Звукового конференц-связи оплаты за минуту (по мере пользования)</br>*Примечание: требуется кредитов коммуникаций для установки и поддержкой*. | MCOMEETACPEA |
| Корпоративный E1 | STANDARDPACK | 
| Корпоративный E3 | ENTERPRISEPACK |
| Корпоративный E5 (без аудиоконференции) |  ENTERPRISEPREMIUM_NOPSTNCONF |
| Корпоративный E5 (с аудиоконференцией) | ENTERPRISEPREMIUM |

##  <a name="communications-credits"></a>Кредиты на связь

Вот что нужно знать, прежде чем назначения лицензий кредитов коммуникаций.

- **E5 корпоративных клиентов**: даже в том случае, если пользователи назначаются E5 корпоративных лицензий, все же рекомендуется назначить их кредитов Communications лицензий.

- **Дальнейшие действия**: после назначить эти лицензии, необходимо получить номера телефонов для вашей организации, а затем назначить эти номера для пользователей в вашей организации. Пошаговые инструкции см. в статье [Настройка планов звонков](set-up-calling-plans.md).

## <a name="assign-a-communications-credits-license-to-one-user"></a>Назначение лицензии кредитов коммуникаций для одного пользователя

Действия такие же, как назначение лицензии Office 365. Просмотрите [Назначение и удаление лицензий на Office 365 для бизнеса](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

## <a name="assign-communications-credits-licenses-in-bulk"></a>Назначение лицензий кредитов коммуникаций в пакетном режиме

Ознакомьтесь с примером сценария для назначения лицензий на аудиоконференции. Обновите сведения для назначения лицензий на кредиты на связь.

## <a name="related-topics"></a>Статьи по теме

[Настройка планов звонков](set-up-calling-plans.md)
</br>
[Пополнение средств и управление кредитами на связь](add-funds-and-manage-communications-credits.md)
