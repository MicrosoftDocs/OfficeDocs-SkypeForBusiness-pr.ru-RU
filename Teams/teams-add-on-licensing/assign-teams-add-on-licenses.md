---
title: Назначение Teams надстройки пользователям
author: SerdarSoysal
ms.author: serdars
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
description: Узнайте, как назначать Teams надстройки пользователям для таких возможностей, как аудиоконференция, телефонная система и планы звонков.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8668b31caf0dc10e8585a518a9c4c9be890d1d0d
ms.sourcegitcommit: ff975c21725e1812e6db8fc9fe37de1362f168c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2022
ms.locfileid: "63435843"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Назначение Teams надстройки пользователям

Лицензии на надстройки — это лицензии на определенные Teams, такие как аудиоконференция, телефонная система и планы звонков. В этой статье описано, как массово назначить лицензии на надстройки отдельным пользователям и большим наборам пользователей.

> [!NOTE]
> [Дополнительные Teams надстройки](./microsoft-teams-add-on-licensing.md) см. в Teams, доступных с лицензиями на надстройки. Вы также найдете сведения о том, какие лицензии необходимо приобрести, и как их приобрести в зависимости от плана. После того как вы решите, какие возможности вам нужны, назначьте им лицензии.

Вы можете использовать Центр администрирования Microsoft 365 или PowerShell для назначения лицензий пользователям в организации. Для управления лицензиями необходимо быть глобальным администратором или администратором управления пользователями.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Что необходимо знать перед назначением лицензий на телефонная система, плана звонков и кредитов на связь

Перед началом работы просмотрите следующие требования:

- Если вы используете для пользователей локальное подключение к телефонной сети общего перейти на телефонную сеть (STN), необходимо назначить только Teams Телефон стандартную лицензию. Не назначать лицензию на план звонков.

- После назначения пользователю плана звонков Майкрософт может занять до 24 часов, прежде чем он увидит панель набора номера в Teams клиенте. Если панель набора номера не отображается в течение 24 часов, проверьте [конфигурацию панели набора номера](../dial-pad-configuration.md). При необходимости вы также можете обратиться в [службу поддержки](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Если вы приобрели неправильное количество лицензий, вы получите сообщение об ошибке. Если вам нужно приобрести дополнительные лицензии на план звонков, выберите нужный вариант.

- Даже если пользователям назначены лицензии Enterprise E5, их все равно нужно подключить к STN. У [вас есть несколько](../pstn-connectivity.md) параметров подключения к ПСОП, в том числе Microsoft Teams планов звонков, прямой маршрут и операторов Подключение.

- После назначения пользователям лицензий на план звонков или кредиты на связь необходимо получить номера телефонов для организации, а затем назначить их пользователям. Пошаговые инструкции см. в статье [Настройка планов звонков](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Использование Центр администрирования Microsoft 365

Используйте Центр администрирования Microsoft 365 для назначения лицензий отдельным пользователям или небольшим наборам пользователей одновременно.

Лицензии назначаются на странице  Лицензии (не более 20 пользователей одновременно) или На странице Активные пользователи (до 40 пользователей одновременно). Выбор метода зависит от того, хотите ли вы управлять лицензиями на продукты для определенных пользователей или лицензиями пользователей для определенных продуктов.

Пошаговую инструкцию см. в инструкциях по [назначению лицензий пользователям](/microsoft-365/admin/manage/assign-licenses-to-users).

Если вам нужно назначить лицензии большому количеству пользователей, например сотням или тысячам пользователей, используйте Powershell или групповое лицензирование в Azure Active Directory [(Azure AD).](/azure/active-directory/users-groups-roles/licensing-groups-assign).

## <a name="using-powershell"></a>С помощью PowerShell

Используйте PowerShell для массовой назначения лицензий пользователям. Дополнительные данные см. в этом отчете о назначении лицензий учетным записям пользователей [с помощью PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Пример сценария

Вот пример использования сценария для назначения лицензий пользователям.

1. Установите 64-битную версию помощника по входу в [Microsoft Online Services для ИТ-специалистов RTW](/collaborate/connect-redirect?DownloadID=59185).
2. Установите модуль Microsoft Azure Active Directory для Windows PowerShell:
    1. Откройте командную Windows PowerShell с повышенными Windows PowerShell (запустите Windows PowerShell от имени администратора).
    2. Выполните следующую команду.
        ```powershell
        Install-Module MSOnline
        ```
    3. Если вам будет предложено установить поставщика NuGet, введите **Y** и нажмите ввод.
    4. Если вам будет предложено установить модуль из PSGallery, введите **Y** и нажмите ввод.
3. В командной Windows PowerShell запустите следующий сценарий, чтобы назначить лицензии пользователям, \<CompanyName:License> где указаны название организации и идентификатор лицензии, которую вы хотите назначить. Например, litwareinc:MCOMEETADV.

    Идентификатор отличается от удобного имени лицензии. Например, идентификатором аудиоконференции является MCOMEETADV. Дополнительные см. в [документе Названия продуктов и идентификаторы SKU для лицензирования](#product-names-and-sku-identifiers-for-licensing).

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

    Например, чтобы назначить Microsoft 365 корпоративный лицензии на аудиоконференцию E1 и Аудиоконференцию, используйте следующий синтаксис в сценарии:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Чтобы назначить Teams Телефон с лицензией на план звонков, используйте следующий синтаксис в сценарии:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Названия продуктов и идентификаторы SKU для лицензирования

Вот неполный список названий продуктов и соответствующих названий их продуктов, на которые можно ссылаться при использовании PowerShell для управления лицензиями в Teams.

Дополнительные данные см. в ссылках Просмотр лицензий и служб с помощью [PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)[,](/azure/active-directory/users-groups-roles/licensing-service-plan-reference) Названий продуктов и идентификаторов планов обслуживания для лицензирования и Справка по [SKU для образования](../sku-reference-edu.md).

| Наименование товара| Наименование товарной единицы |
|--------------|---------------|
| Microsoft Enterprise E5 (с телефонная система) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (без аудиоконференции) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (с аудиоконференцией) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 бизнес базовый | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 бизнес стандарт | O365_BUSINESS_PREMIUM|
| Microsoft 365 бизнес | SPB|
| Аудиоконференция | MCOMEETADV |
| Оплата аудиоконференции поминутно (оплата по мере входа) Требуется настроить и включить кредиты на связь.* | MCOMEETACPEA |
| Teams Телефон стандартный | MCOEV |
| Телефонная система Teams с тарифным планом | MCOTEAMS_ESSENTIALS |
| План внутренних и международных звонков | MCOPSTN2 |
| План внутренних звонков (3000 минут на пользователя в месяц для США/ PR/CA, 1200 минут на пользователя в месяц для стран ЕС) | MCOPSTN1 |
| План внутренних звонков (120 минут на пользователя в месяц для каждой страны) </br>*Этот план не доступен в США.* | MCOPSTN5 |
| План внутренних звонков (240 минут на пользователя в месяц для каждой страны) </br>*Этот план не доступен в США.* | MCOPSTN6 |
| Кредиты на связь | MCOPSTNPP |

## <a name="related-content"></a>Связанное содержимое

- [Лицензирование надстроек Teams](./microsoft-teams-add-on-licensing.md)
- [Управление доступом пользователей к Teams](../user-access.md)
- [Просмотр лицензий и служб с помощью PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Названия продуктов и идентификаторы планов служб для лицензирования](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Справка по SKU для образования](../sku-reference-edu.md)
