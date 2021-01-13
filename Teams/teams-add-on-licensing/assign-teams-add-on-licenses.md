---
title: Назначение пользователям лицензий на надстройки Teams
author: cichur
ms.author: v-cichur
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
description: Узнайте, как назначать пользователям лицензии на надстройки Teams для таких функций, как аудиоконференция, телефонная система и планы звонков.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f19060245a54012de1dbc1f38edd43365e4aaa6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809329"
---
# <a name="assign-teams-add-on-licenses-to-users"></a>Назначение пользователям лицензий на надстройки Teams

Лицензии на надстройки — это лицензии на определенные функции Teams, такие как аудиоконференция, телефонная система и планы звонков. В этой статье описано, как массово назначить лицензии на надстройки как отдельным пользователям, так и большим наборам пользователей.

> [!NOTE]
> См. [лицензирование надстройки](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing) Teams для функций Teams, доступных с лицензиями на надстройки. Вы также увидите сведения о том, какие лицензии необходимо приобрести и как их приобрести (в зависимости от плана), чтобы пользователи могли получить доступ к таким функциям, как аудиоконференция, бесплатные номера и возможность звонить на телефонные номера за пределы организации. После того как вы решите, какие функции нужны пользователям, назначьте им лицензии.

Для назначения лицензий пользователям в организации можно использовать Центр администрирования Microsoft 365 или PowerShell. Для управления лицензиями необходимо быть глобальным администратором или администратором управления пользователями.

## <a name="what-you-need-to-know-before-you-assign-phone-system-calling-plan-and-communication-credits-licenses"></a>Что нужно знать перед назначением лицензий на телефонную систему, план звонков и кредиты на связь

Прежде чем начать, просмотрите следующие вопросы:

- Если вы используете для гибридных пользователей возможность подключения к локальной телефонной сети общего перейти на ЗВОНКОВ, необходимо только назначить лицензию на телефонную систему. Не назначать лицензию на план звонков.

- Из-за задержки между Microsoft 365 и Microsoft Teams назначение пользователю плана звонков после назначения лицензии может занять до 24 часов. Если пользователю не назначен план звонков по и после 24 часов, обратитесь в службу поддержки по продуктам для [бизнеса— справка для администраторов.](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b)

- Если приобретено неправильное количество лицензий, вы получите сообщение об ошибке. Если вам нужно приобрести дополнительные лицензии на план звонков, выберите нужный вариант.

- Даже если вашим пользователям назначены лицензии на корпоративный [](../what-are-communications-credits.md) E5, им необходимо назначить лицензии на кредиты на связь, если они захотят звонить или принимать звонки через ПС.

- После назначения пользователям лицензий на план звонков или кредиты на связь вам потребуется получить номера телефонов для организации, а затем назначить их пользователям. Пошаговые инструкции см. в статье [Настройка планов звонков](../set-up-calling-plans.md).

## <a name="using-the-microsoft-365-admin-center"></a>Использование Центра администрирования Microsoft 365

Для назначения лицензий отдельным пользователям или небольшим наборам пользователей за раз используйте Центр администрирования Microsoft 365. Лицензии можно назначать на странице **"Лицензии"** (не более 20 пользователей одновременно) или на странице **"Активные** пользователи". Выбор метода зависит от того, хотите ли вы управлять лицензиями на продукты для определенных пользователей или лицензиями пользователей для определенных продуктов.

Пошаговую инструкцию см. в инструкции по [назначению лицензий пользователям.](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)

Если необходимо назначить лицензии большому количеству пользователей, например сотням или тысячам пользователей, используйте Powershell или групповое лицензирование в [Azure Active Directory (Azure AD).](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)  

## <a name="using-powershell"></a>С помощью PowerShell

Используйте PowerShell для массового назначения лицензий пользователям.  Дополнительные данные см. в записях [PowerShell для назначения лицензий учетным записям пользователей.](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)

### <a name="example-script"></a>Пример сценария

Вот пример использования сценария для назначения лицензий пользователям.

1. Установите 64-битную версию Microsoft Online Services для [ИТ-специалистов, RTW.](https://go.microsoft.com/fwlink/p/?LinkId=286152)
2. Установите модуль Microsoft Azure Active Directory для Windows PowerShell:
    1. Откройте командную Windows PowerShell с повышенными Windows PowerShell (запустите Windows PowerShell от имени администратора).
    2. Выполните следующую команду.
        ```powershell
        Install-Module MSOnline
        ```
    3. Если вам будет предложено установить поставщика NuGet, введите **Y** и нажмите ввод.
    4. Если вам будет предложено установить модуль из PSGallery, введите **Y** и нажмите ввод.
3. В командной Windows PowerShell запустите следующий сценарий, чтобы назначить лицензии пользователям, где находится название организации и идентификатор лицензии, которую вы \<CompanyName:License> хотите назначить. Например, litwareinc:MCOMEETADV.

    Идентификатор отличается от удобного имени лицензии. Например, идентификатором для аудиоконференции будет MCOMEETADV. Подробнее см. в названиях продуктов и [идентификаторах SKU для лицензирования.](#product-names-and-sku-identifiers-for-licensing)

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

    Например, чтобы назначить лицензии на Microsoft 365 корпоративный 1 и аудиоконференцию, используйте в сценарии следующий синтаксис:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:ENTERPRISEPACK" -ErrorAction SilentlyContinue
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:MCOMEETADV" -ErrorAction SilentlyContinue
      ```

    Чтобы назначить лицензию на Microsoft Business Voice (без плана звонков), используйте в сценарии следующий синтаксис:

      ```powershell
      Set-MsolUserLicense -UserPrincipalName $user -AddLicenses "litwareinc:BUSINESS_VOICE_DIRECTROUTING" -ErrorAction SilentlyContinue
      ```

## <a name="product-names-and-sku-identifiers-for-licensing"></a>Названия продуктов и идентификаторы SKU для лицензирования

Вот неполный список названий продуктов и соответствующих названий их составных номеров SKU, которые можно использовать в качестве справки при использовании PowerShell для управления лицензиями в Teams.

Дополнительные данные см. в справке по лицензиям и службам [PowerShell,](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)именам продуктов и планам обслуживания для лицензирования [и](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)справке по SKU для [образования.](../sku-reference-edu.md)

| Наименование товара| Наименование товарной единицы |
|--------------|---------------|
| Microsoft Enterprise E5 (с телефонной системой) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E5 (без аудиоконференции) | ENTERPRISEPREMIUM_NOPSTNCONF |
| Microsoft Enterprise E5 (с аудиоконференцией) | ENTERPRISEPREMIUM |
| Microsoft Enterprise E3 | ENTERPRISEPACK |
| Microsoft Enterprise E1 | STANDARDPACK |
| Microsoft 365 бизнес базовый | O365_BUSINESS_ESSENTIALS|
| Microsoft 365 бизнес стандарт | O365_BUSINESS_PREMIUM|
| Microsoft 365 бизнес | SPB|
| Microsoft Business Voice (Канада)| BUSINESS_VOICE_MED  |
| Microsoft Business Voice (Соединенное Королевство) | BUSINESS_VOICE  |
| Microsoft Business Voice (США) | BUSINESS_VOICE_MED2  |
| Microsoft Business Voice (без плана звонков) | BUSINESS_VOICE_DIRECTROUTING  |
| Microsoft Business Voice (без плана звонков) для США| BUSINESS_VOICE_DIRECTROUTING _MED |
| Аудиоконференция | MCOMEETADV | 
| Аудиоконференция с поминутной оплатой (оплата по мере ее оплаты)</br>*Требуется настроить и включить кредиты на связь.* | MCOMEETACPEA |
| Телефонная система | MCOEV |
| План внутренних и международных звонков | MCOPSTN2 |
| План внутренних звонков (3000 минут на пользователя в месяц для США/PR/CA, 1200 минут на пользователя в месяц для стран ЕС) | MCOPSTN1 |
| План внутренних звонков (120 минут на каждого пользователя в месяц для каждой страны) </br>*Этот план не доступен в США.* | MCOPSTN5 |
| План внутренних звонков (240 минут на пользователя в месяц для каждой страны) </br>*Этот план не доступен в США.* | MCOPSTN6 |
| Кредиты на связь | MCOPSTNPP |

## <a name="related-topics"></a>Статьи по теме

- [Лицензирование надстроек Teams](https://docs.microsoft.com/microsoftteams/teams-add-on-licensing/microsoft-teams-add-on-licensing)
- [Управление доступом пользователей к Teams](../user-access.md)
- [Просмотр лицензий и служб с помощью PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/view-licenses-and-services-with-office-365-powershell)
- [Названия продуктов и идентификаторы планов служб для лицензирования](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)
- [Справка по SKU для образования](../sku-reference-edu.md)