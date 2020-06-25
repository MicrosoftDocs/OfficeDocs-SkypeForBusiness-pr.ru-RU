---
title: Назначение лицензий на надстройки Teams пользователям
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
search.appverid: MET150
f1.keywords:
- NOCSH
ms.reviewer: mikedav
description: Сведения о назначении пользователям лицензий на надстройки Teams, таких как голосовые конференции, телефонная система и планы звонков.
appliesto:
- Microsoft Teams
ms.openlocfilehash: c7faaf2e65330aafd809872ed19b5f2f16afc668
ms.sourcegitcommit: 6a4bd155e73ab21944dd5f4f0c776e4cd0508147
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/24/2020
ms.locfileid: "44868586"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Назначение лицензий на надстройки Teams пользователям

Лицензии на надстройки — это лицензии для конкретных функций групп, таких как голосовая конференция, телефонная система и планы звонков. В этой статье описано, как назначать лицензии для отдельных пользователей и больших наборов пользователей.

> [!NOTE]
> Ознакомьтесь с возможностями [лицензирования надстроек Teams](microsoft-teams-add-on-licensing.md) для Teams, которые доступны при использовании лицензий на надстройки. Вы также найдете сведения о лицензиях, которые нужно приобрести, и о том, как их приобрести (в зависимости от вашего плана), чтобы пользователи могли получать такие функции, как голосовые конференции, бесплатные номера и возможность звонить на телефонные номера за пределами вашей организации. После того как вы решите, какие функции вы хотите использовать для ваших пользователей, назначьте им лицензии.

Вы можете назначать лицензии пользователям в Организации с помощью центра администрирования Microsoft 365 или оболочки PowerShell. Для управления лицензиями необходимо быть глобальным администратором или администратором управления пользователями.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Что нужно знать перед назначением лицензий на телефонную систему, план звонков и кредиты на связь

Прежде чем приступить к работе, ознакомьтесь со следующими статьями:

- Если вы используете локальную телефонную сеть общего коммутируемого подключения (PSTN) для гибридных пользователей, вам нужно назначить лицензию на телефонную систему. Не назначайте лицензию на план звонков.

- Из-за задержки между Microsoft 365 и Microsoft Teams пользователю может потребоваться до 24 часов, после того как пользователь сможет назначить план звонков после того, как вы настроили лицензию. Если пользователь не назначил план звонков через 24 часа, обратитесь в [службу поддержки для бизнес-продуктов — Справка для администраторов](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Если вы не приобрели правильное количество лицензий, вы получите сообщение об ошибке. Если вам нужно приобрести дополнительные лицензии на план звонков, выберите вариант "Купить".

- Даже если пользователям назначены лицензии на "Корпоративное" + +, вам по-прежнему [необходимо назначать лицензии](../what-are-communications-credits.md) на получение абонентов, если они хотят совершать и принимать звонки от КТСОП.

- После назначения пользователям лицензий на тарифные планы или кредиты на связь с пользователями необходимо получить номера телефонов для своей организации, а затем назначить их пользователям. Пошаговые инструкции см. в статье [Настройка планов звонков](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Использование центра администрирования Microsoft 365

С помощью центра администрирования Microsoft 365 вы можете назначать лицензии отдельным пользователям или небольшим наборам пользователей за один раз. Вы можете назначать лицензии на странице **лицензий** (до 20 пользователей одновременно) или на странице " **Активные пользователи** ". Выбор метода зависит от того, хотите ли вы управлять лицензиями на продукты для конкретных пользователей или управлять лицензиями пользователей для конкретных продуктов.

Пошаговые инструкции приведены [в статье Назначение лицензий пользователям](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

Если необходимо назначить лицензии для большого числа пользователей, например сотни или тысячи пользователей, используйте PowerShell или [Лицензирование на основе групп в Azure Active Directory (Azure AD)](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).  

## <a name="using-powershell"></a>Использование PowerShell

С помощью PowerShell можно назначать пользователям лицензии для массовых операций.  Дополнительные сведения можно найти в статье [Назначение лицензий для учетных записей пользователей с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Пример сценария

Ниже приведен пример использования сценария для назначения лицензий пользователям.

1. Установите 64-разрядную версию [помощника по входу в Microsoft Online Services для ИТ-специалистов RTW](https://go.microsoft.com/fwlink/p/?LinkId=286152).
2. Установите модуль Microsoft Azure Active Directory для Windows PowerShell.
    1. Откройте командную команду Windows PowerShell с повышенными привилегиями (запустите Windows PowerShell от имени администратора).
    2. Выполните следующую команду.
        ```powershell
        Install-Module MSOnline
        ```
    3. Если вам будет предложено установить поставщик NuGet, введите **Y**и нажмите клавишу ВВОД.
    4. Если вам будет предложено установить модуль из PSGallery, введите **Y**и нажмите клавишу ВВОД.
3. В командной строке Windows PowerShell выполните следующий сценарий для назначения лицензий пользователям, где указаны \<CompanyName:License> название организации и идентификатор для лицензии, которую вы хотите назначить. Например, плана litwareinc: MCOMEETADV.

    Идентификатор отличается от понятного имени лицензии. Например, идентификатором для голосовой конференции является MCOMEETADV. Дополнительные сведения можно найти в разделе [наименования продуктов и идентификаторы SKU для лицензирования](#product-names-and-sku-identifiers-for-licensing).

    ```powershell
    #Create a text file with a single column that lists the user principal names (UPNs) of users to assign licenses to. The MSOL service uses the UPN to license user accounts.
    #Example of text file:''
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
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:<CompanyName:License>" -ErrorAction SilentlyContinue
        }
    ```

    Например, для назначения лицензий Microsoft 365 Enterprise 1 и голосовой связи в сценарии используется следующий синтаксис:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Чтобы назначить лицензию Microsoft Business Voice (без плана звонков), используйте в сценарии следующий синтаксис:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Названия продуктов и идентификаторы SKU для лицензирования

Ниже приводится частичный список названий продуктов и соответствующих им названий частей SKU, которые можно использовать в качестве справочных данных при использовании PowerShell для управления лицензиями в Teams.

Дополнительные сведения можно найти в статье [Просмотр лицензий и служб с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell), [названий продуктов и идентификаторов планов обслуживания для лицензирования](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)и [справочника по образованиям на образовательных SKU](../sku-reference-edu.md).

| Наименование товара| Наименование товарной единицы |
|--------------|---------------|
| Microsoft Enterprise ~ (с телефонной системой) | ENTERPRISEPREMIUM |
| Microsoft корпоративный + ~ (без голосовой конференции) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Корпоративный текст для корпоративных клиентов (с голосовой Конференцией) | ENTERPRISEPREMIUM |
| Microsoft корпоративный E3 | ENTERPRISEPACK |
| Microsoft корпоративный E1 | STANDARDPACK |
| Microsoft 365 бизнес базовый | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 бизнес стандарт | O365_BUSINESS_PREMIUM|
| Microsoft 365 бизнес | SPB|
| Microsoft Business Voice (Канада)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice (Соединенное Королевство) | BUSINESS_VOICE  |
| Microsoft Business Voice (США) | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice (без тарифного плана) | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business Voice (без тарифного плана) для Соединенных Штатов Америки| BUSINESS_VOICE_DIRECTROUTING _MED |
| Аудиоконференция | MCOMEETADV | 
| Оплата для голосовой конференции за минуту (оплата за один звонок)</br>*Требует настройки и включения кредитов на связь.* | MCOMEETACPEA |
| Телефонная система | MCOEV |
| План внутренних и международных звонков | MCOPSTN2 |
| План внутренних вызовов (3000 минут на пользователя/месяц для US/PR/CA, 1200 минут на пользователя/месяц для стран ЕС) | MCOPSTN1 |
| План внутренних вызовов (120 минут на пользователя/месяц для каждой страны) </br>*Этот план недоступен в Соединенных Штатах.* | MCOPSTN5 |
| План внутренних вызовов (240 минут на пользователя/месяц для каждой страны) </br>*Этот план недоступен в Соединенных Штатах.* | MCOPSTN6 |
| Кредиты на связь | MCOPSTNPP |

## <a name="related-topics"></a>Статьи по теме

- [Лицензирование надстроек Teams](microsoft-teams-add-on-licensing.md)
- [Управление доступом пользователей к Teams](../user-access.md)
- [Просмотр лицензий и служб с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Названия продуктов и идентификаторы планов служб для лицензирования](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Справочник по образовательной конфигурации](../sku-reference-edu.md)