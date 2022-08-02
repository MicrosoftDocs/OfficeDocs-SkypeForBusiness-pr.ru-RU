---
title: Назначение пользователям лицензий на надстройки Teams
author: DaniEASmith
ms.author: danismith
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
description: Узнайте, как назначать пользователям лицензии на надстройки Teams для таких возможностей, как аудиоконференции, телефонная система и планы звонков.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1bef1464b94f736a10cc184a2bdb88e2cdf6df88
ms.sourcegitcommit: 07761c26b53d92fc36b82cab7b3e38a6de4ff945
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2022
ms.locfileid: "67156977"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Назначение пользователям лицензий на надстройки Teams

Лицензии на надстройки — это лицензии для определенных возможностей Teams, таких как аудиоконференции, телефонная система и планы звонков. В этой статье описывается, как массово назначать лицензии на надстройки отдельным пользователям и большим наборам пользователей.

> [!NOTE]
> [Ознакомьтесь с лицензированием надстроек](./microsoft-teams-add-on-licensing.md) Teams для возможностей Teams, доступных с помощью лицензий на надстройки. Вы также найдете сведения о том, какие лицензии необходимо приобрести и как их приобрести в зависимости от плана. Когда вы решите, какие возможности вы хотите использовать для пользователей, назначьте им лицензии.

Вы можете использовать Центр администрирования Microsoft 365 powerShell для назначения лицензий пользователям в организации. Для управления лицензиями необходимо быть глобальным администратором или администратором управления пользователями.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Что необходимо знать перед назначением лицензий на телефонную систему, план звонков и кредиты на связь

Прежде чем приступить к работе, ознакомьтесь со следующими требованиями:

- Если вы используете для пользователей подключение к локальной телефонной сети общего пользования (ТСОП), вам нужно назначить Телефонная система стандартная Teams лицензию. Не назначайте лицензию плана звонков.

- После назначения пользователю плана звонков Майкрософт может потребоваться до 24 часов, прежде чем панель набора номера отобразится в клиенте Teams. Если панель набора номера не отображается в течение 24 часов, проверьте [конфигурацию панели набора номера](../dial-pad-configuration.md). При необходимости вы также можете обратиться [в службу поддержки](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b).

- Если вы не приобрели правильное количество лицензий, вы получите сообщение об ошибке. Если вам нужно приобрести дополнительные лицензии на план звонков, выберите вариант, чтобы приобрести дополнительные лицензии.

- Даже если пользователям назначены корпоративные лицензии E5, вам по-прежнему нужно подключить их к ТСОП. У вас есть [несколько вариантов](../pstn-connectivity.md) подключения по ТСОП, включая Microsoft Teams Тарифные планы, прямую маршрутизацию или подключение оператора.

- После назначения пользователям лицензий на план звонков или кредиты на связь необходимо получить номера телефонов для организации, а затем назначить эти номера пользователям. Пошаговые инструкции см. в статье [Настройка планов звонков](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Использование Центр администрирования Microsoft 365

Используйте Центр администрирования Microsoft 365 для одновременного назначения лицензий отдельным пользователям или небольшим наборам пользователей.

Лицензии назначаются на странице **"** Лицензии" (одновременно до 20 пользователей) или на странице "Активные  пользователи" (одновременно до 40 пользователей). Выбор метода зависит от того, хотите ли вы управлять лицензиями на продукты для определенных пользователей или управлять пользовательскими лицензиями для определенных продуктов.

Пошаговые инструкции см. в разделе ["Назначение лицензий пользователям"](/microsoft-365/admin/manage/assign-licenses-to-users).

Если необходимо назначить лицензии большому числу пользователей, например сотням или тысячам пользователей, используйте PowerShell или групповое [лицензирование в Azure Active Directory (Azure AD)](/azure/active-directory/users-groups-roles/licensing-groups-assign).

## <a name="using-powershell"></a>С помощью PowerShell

Используйте PowerShell для массового назначения лицензий пользователям. Дополнительные сведения см. в [статье "Назначение лицензий учетным записям пользователей с помощью PowerShell"](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell).

### <a name="example-script"></a>Пример скрипта

Ниже приведен пример использования скрипта для назначения лицензий пользователям.

1. [Установите модуль Microsoft Azure Active Directory для Windows PowerShell](/powershell/azure/active-directory/install-msonlinev1).
2. В командной Windows PowerShell выполните следующий сценарий, чтобы назначить лицензии пользователям, `CompanyName:License` где находится название вашей организации и идентификатор лицензии, которую вы хотите назначить. Например, `litwareinc:MCOMEETADV`.

    Идентификатор отличается от понятного имени лицензии. Например, идентификатором аудиоконференций является `MCOMEETADV`. Дополнительные сведения см. [в разделе "Названия продуктов и идентификаторы номеров SKU для лицензирования"](#product-names-and-sku-identifiers-for-licensing).

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

    Например, чтобы назначить лицензии Microsoft 365 корпоративный E1 и Аудиоконференции, используйте следующий синтаксис в скрипте:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Чтобы назначить телефон Teams с лицензией плана звонков, используйте следующий синтаксис в сценарии:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOTEAMS_ESSENTIALS" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Имена продуктов и идентификаторы номеров SKU для лицензирования

Ниже приведен неполный список названий продуктов и их соответствующих имен частей SKU, на которые можно ссылаться при использовании PowerShell для управления лицензиями в Teams.

Дополнительные сведения см. в разделе "Просмотр лицензий и служб с помощью [PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)", " [Названия](/azure/active-directory/users-groups-roles/licensing-service-plan-reference) продуктов и идентификаторы планов обслуживания для лицензирования" и "Справочник по [SKU для образования"](../sku-reference-edu.md).

| Наименование товара| Наименование товарной единицы |
|--------------|---------------|
| Microsoft Enterprise E5 (с телефонной системой) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (без аудиоконференций) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (с аудиоконференций) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 бизнес базовый | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 бизнес стандарт | O365_BUSINESS_PREMIUM|
| Microsoft 365 бизнес | SPB|
| Аудиоконференция | MCOMEETADV |
| Оплата аудиоконференций за минуту (оплата по мере использования) требует настройки и включения кредитов на связь.* | MCOMEETACPEA |
| Телефонная система стандартная Teams | MCOEV |
| Телефонная система Teams с тарифным планом | MCOTEAMS_ESSENTIALS |
| План международных звонков | MCOPSTN2 |
| План внутренних звонков (3000 минут на пользователя в месяц для США, PR/ЦС, 1200 минут на пользователя в месяц для стран ЕС) | MCOPSTN1 |
| План внутренних звонков (120 минут на пользователя в месяц для каждой страны) </br>*Этот план недоступен в США.* | MCOPSTN5 |
| План внутренних звонков (240 минут на пользователя в месяц для каждой страны) </br>*Этот план недоступен в США.* | MCOPSTN6 |
| Кредиты на связь | MCOPSTNPP |
| Тарифные планы с оплатой по мере использования (страны зоны 1) | MCOPSTN_PAYG_1 |
| Тарифные планы с оплатой по мере использования (страны зоны 2) | MCOPSTN_PAYG_2 |

## <a name="related-content"></a>Связанное содержимое

- [Лицензирование надстроек Teams](./microsoft-teams-add-on-licensing.md)
- [Управление доступом пользователей к Teams](../user-access.md)
- [Просмотр лицензий и служб с помощью PowerShell](/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Названия продуктов и идентификаторы планов служб для лицензирования](/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Справочник по SKU для образовательных учреждений](../sku-reference-edu.md)
