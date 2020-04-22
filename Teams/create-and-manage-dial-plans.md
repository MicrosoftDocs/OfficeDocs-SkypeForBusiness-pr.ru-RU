---
title: Создание и использование абонентских групп
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Сведения о том, как создавать абонентские группы и управлять ими (абонентские группы для звонков по коммутируемой телефонной связи) и как управлять ими.
ms.openlocfilehash: 9c72745e6dee12ffbac4d91df47df37c327aab33
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43778265"
---
# <a name="create-and-manage-dial-plans"></a>Создание и использование абонентских групп

После того как вы запланируете абонентские группы для Организации и выйдете все правила нормализации, которые необходимо создать для маршрутизации звонков, вы можете создать абонентские группы. Вы можете использовать центр администрирования Microsoft Teams или Windows PowerShell для создания абонентских групп и управления ими.  

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

### <a name="create-a-dial-plan"></a>Создание абонентской группы

1. В левой области навигации центра администрирования Microsoft Teams выберите > **абонентская** **абонентская**группа.
2. Нажмите кнопку **Добавить**, а затем введите имя и описание абонентского плана.
    ![Снимок экрана, на котором показана страница "Добавление" для создания абонентской группы](media/create-dial-plan.png)
3. В разделе **сведения о абонентской схеме**укажите внешний префикс набора номера, если пользователям необходимо набрать одну или несколько начальных цифр (например, 9), чтобы получить внешнюю строку. Для этого выполните следующие действия:
    1. В поле **Префикс внешнего набора** введите внешний префикс. Префикс может состоять не более чем из четырех знаков (#, * и 0-9).
    2. Включите **оптимизированный набор номера для устройств**. Если указан внешний префикс набора номера, необходимо также включить этот параметр, чтобы применить префикс, чтобы звонки могли выполняться за пределами Организации.
4. В разделе **правила нормализации**настройте и свяжите одно или несколько [правил нормализации](what-are-dial-plans.md#normalization-rules) для абонентской группы. Каждая абонентская группа должна иметь по крайней мере одно связанное с ним правило нормализации.  Чтобы сделать это, выполните одно или несколько из указанных ниже действий.
    - Чтобы создать новое правило нормализации и связать его с абонентской панелью, нажмите кнопку **Добавить**, а затем укажите правило.
    - Чтобы изменить правило нормализации, уже связанное с абонентской панелью, выберите правило, щелкнув слева от имени правила, а затем нажмите кнопку **изменить**. Внесите нужные изменения и нажмите кнопку **сохранить**.
    - Чтобы удалить правило нормализации абонентской группы, выберите правило, щелкнув слева от имени правила, а затем нажмите кнопку **Удалить**.
5. Расположите правила нормализации в нужном порядке. Нажмите кнопку **переместить вверх** или **Переместить вниз** , чтобы изменить расположение правил в списке.

    > [!NOTE]
    > Teams обходит список правил нормализации сверху вниз и использует первое правило, которое соответствует номеру набора. Если вы настроили абонентскую группу таким образом, чтобы номер с набором номера мог совпадать с более чем одним правилом нормализации, убедитесь в том, что более ограниченные правила сортируются над менее строгими.

6. Нажмите кнопку **Сохранить**.
7. Если вы хотите протестировать абонентскую группу, в разделе **Проверка абонентской группы**введите номер телефона и нажмите кнопку **проверить**.

### <a name="edit-a-dial-plan"></a>Изменение абонентской группы

1. В левой области навигации центра администрирования Microsoft Teams выберите > **абонентская** **абонентская**группа.
2. Выберите абонентскую группу, щелкнув слева от имени абонентской группы, а затем нажмите кнопку **изменить**.
3. Внесите нужные изменения и нажмите кнопку **сохранить**.

### <a name="add-users-to-a-dial-plan"></a>Добавление пользователей в абонентскую группу

1. В левой области навигации центра администрирования Microsoft Teams перейдите к разделу **Пользователи**.
2. Выберите пользователя, щелкнув отображаемое имя.
3. Перейдите на вкладку **политики** .
4. Нажмите кнопку **изменить** справа от назначенных политик.
5. В раскрывающемся меню **абонентская группа** выберите абонентскую группу, которую вы хотите назначить пользователю, и нажмите кнопку **Применить**.

## <a name="using-powershell"></a>Использование PowerShell
  
### <a name="verify-and-start-remote-powershell"></a>Проверка и запуск удаленной оболочки PowerShell

 **Убедитесь в том, что вы используете Windows PowerShell версии 3,0 или более поздней.**
  
1. Чтобы убедиться в том, что у вас установлена версия 3,0 или выше: **меню** > "Пуск"**Windows PowerShell**.
    
2. Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.
    
3. Если у вас нет версии 3,0 или более поздней, скачайте и установите обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4,0, ознакомьтесь с разгрузкой [платформы Windows Management Framework 4,0](https://go.microsoft.com/fwlink/?LinkId=716845) . Перезагрузите компьютер после появления соответствующего запроса.
    
4. Кроме того, вам потребуется установить модуль Windows PowerShell для Skype для бизнеса Online, который позволяет создавать удаленные сеансы Windows PowerShell, которые подключаются к Skype для бизнеса Online. Вы можете скачать этот модуль, который поддерживается только на компьютерах с 64-разрядными компьютерами и в [модуле Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). Перезагрузите компьютер, если будет предложено.
    
Дополнительные сведения можно найти в разделе [подключение ко всем службам Office 365 в одном окне Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).
  
 **Запуск сеанса Windows PowerShell**
  
1. Нажмите кнопку **запустить** > **Windows PowerShell**.
    
2. В окне **Windows PowerShell** подключитесь к службе Microsoft 365 или Office 365, выполнив следующие действия:
    
    > [!NOTE]
    > Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.
  

    ```PowerShell
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
    ```
  
### <a name="create-and-manage-your-dial-plans"></a>Создание абонентских планов и управление ими

Создание абонентских групп клиентов и управление ими можно осуществлять с помощью одиночного командлета или сценария PowerShell.
  
#### <a name="using-single-cmdlets"></a>С помощью одиночного командлета

- Чтобы создать новую абонентскую группу, выполните:
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Другие примеры и параметры см. в разделе [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).
    
- Чтобы изменить параметры существующей абонентской группы, выполните:
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Другие примеры и параметры см. в разделе [Set-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/set-cstenantdialplan).
    
- Чтобы добавить пользователей в абонентскую группу, запустите следующую команду:
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Другие примеры и параметры см. в разделе [Grant-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/grant-cstenantdialplan).
    
- Чтобы просмотреть параметры абонентской группы, запустите следующую команду:
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Другие примеры и параметры см. в разделе [Get-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cstenantdialplan?view=skype-ps).
    
- Чтобы удалить абонентскую группу, запустите следующую команду:
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Другие примеры и параметры см. в разделе [Remove-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).
    
- Чтобы просмотреть параметры действующей абонентской группы, запустите следующую команду:
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Другие примеры и параметры см. в разделе [Get-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/get-cseffectivetenantdialplan).
    
- Для проверки действующих параметров абонентской группы запустите следующую команду:
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    Другие примеры и параметры см. в разделе [Test-CsEffectiveTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).
    
#### <a name="using-a-powershell-script"></a>С помощью скрипта PowerShell

Запустите этот параметр, чтобы удалить правило нормализации, связанное с абонентской планом клиента, не требуя сначала удалить абонентскую группу.
```PowerShell
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
Запустите эту команду для добавления следующего правила нормализации к существующему клиенту абонентской группы с именем RedmondDialPlan.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
Запустите эту команду для удаления следующего правила нормализации из существующего клиента абонентской группы с именем RedmondDialPlan.
```PowerShell
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Запустите следующую команду, когда вы хотите также проверить существующие правила нормализации, определить, какое из них нужно удалить, а затем использовать его индекс для удаления. Массив правил нормализации начинается с индекса 0. Если мы хотим удалить з-х цифровое правило нормализации, индекс будет 1.
  
```PowerShell
Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules
Description         : 4-digit
Pattern             : ^(\\d{4})$
Translation         : +1426666$1
Name                : NR2
IsInternalExtension : False

Description         : 3-digit
Pattern             : ^(\\d{3})$
Translation         : +14255551$1
Name                : NR12
IsInternalExtension : False

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Запустите эту команду для поиска всех пользователей, которым была присвоена абонентская группа клиента RedmondDialPlan.
  
```PowerShell
Get-CsOnlineUser | Where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Запустите этот элемент, чтобы удалить все назначенные TenantDialPlan от всех пользователей, у которых есть HostingProvider из sipfed.online.lync.com.
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq “sipfed.online.lync.com”} | Grant-CsTenantDialPlan -policyname $null
```

Запустите эту команду для добавления существующей локальной абонентской группы с именем OPDP1 в качестве абонентской группы клиента для вашей организации. Необходимо сначала сохранить локальную абонентскую группу в XML-файл, а затем использовать ее для создания новой абонентской группы клиента.
  
Запустите эту команду для сохранения локальной абонентской группы в XML-файл.
  
```PowerShell
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Запустите эту команду для создания новой абонентской группы клиента.
  
```PowerShell
$DPFileName = "dialplan.xml"
$dp = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" + $nr.Name
 $nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation -IsInternalExtension $nr.IsInternalExtension -InMemory
 $NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
    
## <a name="related-topics"></a>Статьи по теме

- [Что такое абонентские группы?](what-are-dial-plans.md)
- [Общие вопросы по передаче номеров телефонов](transferring-phone-numbers-common-questions.md)
- [Типы номеров телефонов, используемые в планах звонков](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Управление номерами телефонов организации](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Условия и положения, распространяющиеся на экстренные вызовы](emergency-calling-terms-and-conditions.md)
- [Метка отказа в звонке в экстренном случае](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)
