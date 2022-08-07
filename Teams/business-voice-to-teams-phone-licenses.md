---
title: Переход с корпоративной голосовой связи на лицензии Teams Phone
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.localizationpriority: medium
search.appverid: MET150
description: Узнайте, как изменить лицензии корпоративной голосовой связи на лицензии Teams Phone.
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 6e7622e4b78e57f45209b90a525eb5fefbe8cd66
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271234"
---
# <a name="move-from-business-voice-to-teams-phone-licenses"></a>Переход с корпоративной голосовой связи на лицензии Teams Phone

К концу июня 2022 г. поддержка Корпоративной голосовой связи будет прекращена, поэтому мы рекомендуем компаниям переключиться на Телефонная система Microsoft Teams с тарифным планом [пакетов](https://techcommunity.microsoft.com/t5/small-and-medium-business-blog/teams-phone-with-calling-plan-available-in-33-markets-on-january/ba-p/2967643).

Business Voice объединяет следующие три лицензии на надстройки Teams:

- **Телефонная система Microsoft Teams** для облачной телефонной системы в Microsoft Teams.
- **Аудиоконференции** для конференц-связи с телефонным подключением и телефонным подключением для собраний.
- **Планы звонков Майкрософт** для внутренних вызовов к общедоступной телефонной сети (ТСОП).

Существующие клиенты Корпоративной голосовой связи не будут автоматически переключяться на новую модель лицензирования.

Эта статья предназначена для ИТ-администраторов, которым необходимо изменить лицензии business Voice на лицензии Телефонная система Microsoft Teams и аудиоконференций с сохранением тех же возможностей.

> [!WARNING]
> Внимательно следуйте инструкциям, приведенным в этой статье. Если в инструкциях показано, что не нажата кнопка **"Сохранить** ", не нажата **кнопка "** Сохранить".
>
> Преждевременная сохранение может привести к потере назначений номеров телефонов, абонентской группы, автосекретарей и очередей звонков.

## <a name="acquire-new-licenses"></a>Получение новых лицензий

Прежде чем заменять лицензии На голосовую связь для бизнеса, сначала необходимо приобрести лицензии на замену для пользователей.

Вам потребуются лицензии для предоставления следующих функций:

- Аудиоконференции
- Облачная телефонная система
- Связь с ТСОП

Используйте следующую таблицу, чтобы определить, какие лицензии следует приобрести в зависимости от ваших потребностей.

| Старый план лицензирования | Рекомендуемый план лицензирования | Описание |
| ---------------- | ------------------------ | ----------- |
| Business Voice с тарифным планом | Телефон Teams с планом звонков и Аудиоконференции Microsoft Teams с телефонным США/CAN | Предоставляет облачные возможности телефонной системы, план внутренних звонков с майкрософт в качестве поставщика ТСОП, а также возможности для телефонного подключения и телефонного подключения для участников собрания, упорядоченного лицензированным пользователем. |
| Бизнес-голосовая связь без плана звонков | Телефонная система стандартная Teams и Аудиоконференции Microsoft Teams с помощью подключения к США/CAN | Предоставляет облачные возможности телефонной системы, которые можно сочетать со сторонним планом звонков с поставщиком [ТСОП с помощью Operator Connect](pstn-connectivity.md) или прямой маршрутизации, а также функций телефонного подключения и телефонного подключения для участников собрания, упорядоченных лицензированным пользователем. |

## <a name="how-to-update-licenses"></a>Обновление лицензий

У вас есть четыре способа обновления лицензий:

- Обновление лицензии одного пользователя через Центр администрирования Microsoft 365
- Массовое обновление лицензии пользователя с помощью Центр администрирования Microsoft 365
- Массовое обновление лицензии пользователя с помощью скрипта PowerShell
- Массовое обновление лицензий пользователей с помощью группового лицензирования Azure

# <a name="option-1-single-user-in-admin-center"></a>[Вариант 1. Один пользователь в Центре администрирования](#tab/single-user)

### <a name="option-1-single-user-license-update-via-microsoft-365-admin-center"></a>Вариант 1. Обновление лицензии одного пользователя через Центр администрирования Microsoft 365

Чтобы обновить одного пользователя, можно использовать Центр администрирования Microsoft 365.

1. Перейдите [admin.microsoft.com](https://admin.microsoft.com/) и войдите с учетными данными администратора клиента.
1. Перейдите **к разделу "** > **Активные пользователи** " и выберите нужного пользователя.
1. Выберите **"Управление лицензиями на продукты** " на панели инструментов списка.
1. На экране **"Лицензии и приложения** " снимите флажок "Голосовая связь для бизнеса".
    > [!IMPORTANT]
    > Пока не сохраняйте изменения. Если сохранить изменения без добавления новых лицензий, учетная запись пользователя будет отозвана и номер телефона не назначен.
1. После отмены выбора корпоративной голосовой связи проверьте новые лицензии на телефон и аудиоконференции Teams.
1. Теперь вы можете безопасно сохранить изменения, выбрав команду **"Сохранить изменение"**.

Лицензии пользователя будут обновлены и не должны влиять на доступность службы.

# <a name="option-2-bulk-users-in-admin-center"></a>[Вариант 2. Массовое использование пользователей в Центре администрирования](#tab/bulk-users-admin-center)

### <a name="option-2-bulk-user-license-update-via-microsoft-365-admin-center"></a>Вариант 2. Массовое обновление лицензии пользователя с помощью Центр администрирования Microsoft 365

Для массового обновления лицензий нескольких пользователей можно использовать Центр администрирования Microsoft 365. Выбранные пользователи будут иметь то же назначение плана лицензирования.

1. Перейдите [admin.microsoft.com](https://admin.microsoft.com/) и войдите с учетными данными администратора клиента.
1. Перейдите **к разделу "** > **Активные пользователи** " и выберите всех нужных пользователей.  
1. Выберите **"Управление лицензиями на продукты** " на панели инструментов списка.
1. В **командной** строке "Что вы хотите сделать с лицензиями для этих пользователей?" выберите команду "Заменить: отменить назначение существующих лицензий" и назначить **новые** .
    > [!IMPORTANT]
    > При **выборе параметра** "Заменить" будут удалены все существующие лицензии для выбранных пользователей.  В результате необходимо выбрать требуемое состояние лицензирования для пользователей, включая любые другие лицензии, например Microsoft 365 бизнес премиум.
    >
    > Кроме того, если у выбранных пользователей разные базовые конфигурации лицензий, они будут перезаписаны выбранными лицензиями, что может повлиять на другие области Microsoft 365.
    >
    > Для клиентов со смешанной настройкой лицензии рекомендуется использовать параметр [массового обновления со скриптом PowerShell](#option-3-bulk-user-license-update-using-a-powershell-script).
1. На экране **"Лицензии и приложения** " снимите флажок "Голосовая связь для бизнеса".
    > [!IMPORTANT]
    > Пока не сохраняйте изменения. Если сохранить изменения без добавления новых лицензий, учетные записи выбранных пользователей будут отозваны и номер телефона не назначен.
1. После отмены выбора корпоративной голосовой связи проверьте новые лицензии на телефон и аудиоконференции Teams.
1. Теперь вы можете безопасно сохранить изменения, выбрав команду **"Сохранить изменение"**.
  Лицензии пользователей будут обновлены и не должны влиять на доступность служб.

# <a name="option-3-bulk-users-via-powershell"></a>[Вариант 3. Массовое использование пользователей с помощью PowerShell](#tab/powershell)

### <a name="option-3-bulk-user-license-update-using-a-powershell-script"></a>Вариант 3. Массовое обновление лицензии пользователя с помощью скрипта PowerShell

Замена плана лицензирования Корпоративной голосовой связи с помощью сценария PowerShell является эффективным решением для большинства сценариев.  

Чтобы использовать этот метод, выполните следующие общие действия:

1. Получите идентификаторы плана лицензирования для конкретного клиента текущих лицензий Корпоративной голосовой связи.
1. Получите идентификаторы клиентов для новых планов лицензирования телефонов и аудиоконференций Teams.
1. Проверьте, имеют ли новые планы лицензирования те же планы обслуживания, что и текущая лицензия "Голосовая связь для бизнеса".
1. Найдите пользователей клиента, у которых есть лицензия на Business Voice (или измените сценарий, чтобы включить фильтр для выбора подмножества пользователей при необходимости).
1. Обновите конфигурацию лицензий пользователей с помощью планов телефонной и аудиоконференции Teams.

> [!IMPORTANT]
> Предоставленный скрипт является примером кода. Скрипт не должен копироваться как есть и выполняться в рабочем клиенте без тестирования, проверки и настройки для конкретной среды.

### <a name="how-to-bulk-update-licenses-using-powershell"></a>Массовое обновление лицензий с помощью PowerShell

1. Установите и импортируйте модуль AzureAD PowerShell.

    ```powershell
    Install-Module AzureAD
    Import-Module AzureAD
    ```

1. Подключитесь к клиенту Microsoft 365 и укажите учетные данные администратора клиента.

    ```powershell
    Connect-AzureAD
    ```

1. Используйте следующий командлет, чтобы получить список всех пакетов лицензий в клиенте.

    ```powershell
    Get-AzureADSubscribedSku
    ```

1. Используйте следующую таблицу, чтобы определить план лицензирования надстройки Business Voice, который будет заменен.

    | Код SKU | Тип лицензии |
    | -------- | ------------ |
    | BUSINESS_VOICE_MED | Бизнес-голосовая связь с тарифным планом — Канада |
    | BUSINESS_VOICE | Business Voice с тарифным планом — Соединенное Королевство |
    | BUSINESS_VOICE_MED2_TELCO | Бизнес-голосовая связь с тарифным планом — США |
    | BUSINESS_VOICE_DIRECTROUTING | Бизнес-голосовая связь без плана звонков |
    | BUSINESS_VOICE_DIRECTROUTING_MED | Business Voice без тарифного плана — США |

    > [!NOTE]
    > Сценарий, приведенный в этом документе, предполагает, что в клиенте есть один номер SKU Code for Business Voice.  
    >
    > Если у вас несколько номеров SKU "Голосовая связь для бизнеса", вам потребуется настроить скрипт или выполнить его несколько раз, по одному разу для каждого кода SKU.

1. Создайте переменную PowerShell с именем `$skuSourceBV`.
    1. Обязательно замените метку `SkuPartNumber` кодом номера SKU корпоративной голосовой связи клиента.
    1. В этом примере мы используем код `BUSINESS_VOICE_MED2_TELCO` SKU.

    ```powershell
    $skuSourceBV = Get-AzureADSubscribedSku  | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
    ```

1. Используйте следующую таблицу, чтобы определить новые коды номеров SKU телефонов и аудиоконференций Teams.

    | Код SKU | Тип лицензии |
    | -------- | ------------ |
    | MCOTEAMS_ESSENTIALS | Телефонная система Teams с тарифным планом |
    | MCOEV | Телефонная система стандартная Teams (без плана звонков) |
    | MCOMEETADV | Аудиоконференция |
    | Microsoft_Teams_Audio_Conferencing_select_dial_out | Аудиоконференции Microsoft Teams dial-out |

1. Создайте переменные PowerShell для хранения уникальных кодов номеров SKU телефонов и аудиоконференций Teams.
    1. Обязательно замените метку `SkuPartNumber` кодами SKU, доступными в клиенте.
    1. В этом примере мы используем коды `MCOTEAM_ESSENTIALS` SKU `MCOMEETADV` и SKU.

        ```powershell
        $skuTargetTPCP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
        $skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"} 
        ```

1. Выполните этот сценарий, чтобы собрать необходимые данные плана обслуживания из исходного номера SKU в уникальные объекты.

     ```powershell
     $servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
    $servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
    $servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}
    ```

1. Прежде чем перейти к следующему, проверьте, включены ли в исходный номер SKU (Business Voice) и целевые номера SKU (телефонная и аудиоконференции Teams) одинаковые планы обслуживания.
    1. Несоответствие может привести к изменению лицензии, которое может нарушить работу служб голосовой связи и аудиоконференций пользователей.
    2. Создайте переменные, чтобы проверить, будут ли все планы обслуживания в исходном номере SKU заменены на один и тот же целевой план обслуживания.

        ```powershell
        $validated_TP = $false
        $validated_AC = $false
        $validated_CP = $false
        ```

    3. Если исходная лицензия business Voice не содержит тарифный план, не проверяйте ее.

        ```powershell
        if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }
        ```

    4. Убедитесь, что все планы обслуживания в исходном номере SKU имеют соответствующий план обслуживания в целевом номере SKU.

        ```powershell
        For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) {
        if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
        if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
        if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
        }
        ```

    5. Если в целевом номере SKU отсутствует план обслуживания, вы можете нарушить доступность служб для пользователей, и скрипт должен остановить обработку.

        ```powershell
        if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit }
        if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit }
        if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit }
        ```

1. Если все выглядит хорошо, подготовьте объекты PowerShell для выполнения операций обновления объектов пользователей. Используйте для `AssignedLicenses` этого объект.

    ```powershell
    $LicenseAddTPCP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddTPCP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTPCP.SkuPartNumber -EQ).SkuID
    $LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
    $LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
    
    $LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
    $LicensesToUpdate.AddLicenses += ($LicenseAddTPCP)
    $LicensesToUpdate.AddLicenses += ($LicenseAddAC)
    $LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID
    ```

1. Затем получите список пользователей, которым назначены лицензии Business Voice, и сохраните их в списке с именем `$usersLicensedOldSKU`.

    ```powershell
    $usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
    
    Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }
    ```

1. Теперь, используя новый список пользователей, выполните действие обновления, чтобы удалить лицензии "Голосовая связь для бизнеса" и добавить лицензии teams Phone и Audio Conferencing, ``$LicensesToUpdate`` используя созданный ранее объект.

    ```powershell
    $usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
    ```

> [!NOTE]
> Если у вас недостаточно доступных лицензий на Телефон Teams и (или) аудиоконференции для замены Business Voice, вы получите сообщение об ошибке "Подписка с **идентификатором guid SKU** " не имеет доступной лицензии во время назначения пользователя, как только пул лицензий будет исчерпан.

### <a name="full-script"></a>Полный скрипт

```powershell
#Install the AzureAD module when required
Install-Module AzureAD
#Import the AzureAD module so you can use the commandlets
Import-Module AzureAD

#Connect to your tenant
Connect-AzureAD

#When necessary, uncomment and use this commandlet to list all the licenses in the tenant and identify which license packages are required
#Get-AzureADSubscribedSku

##Replace the SKU codes below to match your desired scenario
$skuSourceBV = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "BUSINESS_VOICE_MED2_TELCO"}
$skuTargetTP = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOTEAMS_ESSENTIALS"}
$skuTargetAC = Get-AzureADSubscribedSku | where {$_.SkuPartNumber -eq "MCOMEETADV"}

##Replace the SKU codes below to match your desired scenario
$servicePlan_Phone = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*EV*"}
$servicePlan_AC = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*MEET*"}
$servicePlan_CP = $skuSourceBV.ServicePlans | where {$_.ServicePlanName.ToString() -like "*PSTN*"}

##Create variables to validate if all Service Plans in the source SKU will be replaced with the same target service plan
$validated_TP = $false
$validated_AC = $false
$validated_CP = $false

##If source Business Voice has no Calling Plan included, do not check
if($skuSourceBV.ServicePlans.Count -eq 2) { $validated_CP = $true }

##Verify if all service plans in source SKU have a matching service plan in target SKU
For ($i=0; $i -le $skuSourceBV.ServicePlans.Count ; $i++) { 
    if($validated_TP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_Phone)) { $validated_TP = $true } }
    if($validated_AC -eq $false) { if($skuTargetAC.ServicePlans.Contains($servicePlan_AC)) { $validated_AC = $true } }
    if($validated_CP -eq $false) { if($skuTargetTP.ServicePlans.Contains($servicePlan_CP)) { $validated_CP = $true } }
}

##If there's a missing service plan in the target sku, we might impact service availability for a user and therefore stop processing
if($validated_TP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Teams Phone." ; exit } 
if($validated_AC -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Audio Conferencing." ; exit } 
if($validated_CP -eq $false ) { Write-Host "Stop updating users because target SKU does not have the same Service Plan for Calling Plan." ; exit } 


##Prepare variables and update
$LicenseAddTP = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddTP.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetTP.SkuPartNumber -EQ).SkuID
$LicenseAddAC = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$LicenseAddAC.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuTargetAC.SkuPartNumber -EQ).SkuID
$LicensesToUpdate = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToUpdate.AddLicenses += ($LicenseAddTP)
$LicensesToUpdate.AddLicenses += ($LicenseAddAC)
$LicensesToUpdate.RemoveLicenses = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value $skuSourceBV.SkuPartNumber -EQ).SkuID

$usersLicensedOldSKU = New-Object System.Collections.Generic.List[Microsoft.Open.AzureAD.Model.User]
Get-AzureAdUser | ForEach { $BVlicensed=$False ; For ($i=0; $i -le ($_.AssignedLicenses | Measure).Count ; $i++) { If($_.AssignedLicenses[$i].SkuId -eq $skuSourceBV.SkuId) { $BVlicensed=$true } } ; If( $BVlicensed -eq $true) { $usersLicensedOldSKU.Add($_)} }

$usersLicensedOldSKU | ForEach { Set-AzureADUserLicense -ObjectId $_.ObjectId -AssignedLicenses $LicensesToUpdate; Write-Host "Completed Update of user " $_.UserPrincipalName;  }
```

# <a name="option-4-bulk-users-with-azure-group-based-licensing"></a>[Вариант 4. Массовое использование пользователей с помощью группового лицензирования Azure](#tab/azure-licensing)

### <a name="option-4-bulk-user-license-update-using-azure-group-based-licensing"></a>Вариант 4. Массовое обновление лицензий пользователей с помощью группового лицензирования Azure

Управление лицензиями на основе групп Azure позволяет назначать подписки и планы обслуживания группе.

Этот метод гарантирует следующее:

- Лицензии назначаются всем участникам группы.
- Всем новым участникам, присоединившимся к группе, назначаются соответствующие лицензии.
- При удалении участников из группы эти лицензии также удаляются.

Вам потребуется проверить требования к [лицензии для группового лицензирования](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).

> [!NOTE]
> Для этого метода обновления лицензии должны обрабатываться за один шаг.
>
> Рекомендуется скомпилировать список существующих групп с назначенными лицензиями "Голосовая связь для бизнеса", сначала выбрать небольшую тестовую группу пользователей и заменить назначение плана лицензирования на предпочтительные новые планы лицензирования.

### <a name="how-to-bulk-update-licenses-using-group-based-licensing"></a>Массовое обновление лицензий с помощью группового лицензирования

1. Перейдите [portal.azure.com](https://portal.azure.com) и войдите с помощью учетных данных администратора.
1. Перейдите **в Azure Active Directory** и в меню слева выберите **"Лицензии"**.
1. Чтобы проверить, какие группы имеют назначенные лицензии на голосовую связь для бизнеса, выберите "Все **продукты** " и выберите план "Голосовая связь для бизнеса".
1. Выберите **лицензированные группы или** **лицензированных пользователей**. Список лицензированных групп можно найти в области справа.
1. Выберите имя группы, чтобы открыть сведения о назначении группы.
1. Выберите **"Назначения** ", чтобы изменить лицензии, назначенные этой группе.
1. Установите флажки перед планами лицензирования, полученными для замены корпоративной голосовой связи.
1. Снимите флажок перед планом Голосовая связь Microsoft 365 бизнес лицензии.
1. Нажмите **Сохранить**.
1. Вернитесь в группу, выбрав имя группы. Вы увидите баннер с сообщением об **ожидающих изменениях лицензии**.
1. Выберите **"Повторная обработка** ", чтобы принудительно обновить назначение лицензии.

---

## <a name="validate-user-license-updates"></a>Проверка обновлений лицензий пользователей

После завершения выбранного метода проверьте, правильно ли обновлены пользовательские лицензии.

1. Перейдите [к Центр администрирования Microsoft 365](https://admin.microsoft.com) и войдите с помощью учетных данных администратора.
1. Перейдите **к разделу "** > **Активные пользователи** " и выберите тестового пользователя.
1. Выберите **"Управление лицензиями на продукты** " на панели инструментов.
1. На экране **"Лицензии и приложения** " проверьте, какие лицензии им назначены.

Если всем целевым пользователям назначены правильные лицензии, вы завершили обновление лицензий на голосовую связь для бизнеса до лицензий На телефонные и аудиоконференции Teams.
