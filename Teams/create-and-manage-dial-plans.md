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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- seo-marvel-apr2020
description: Узнайте, как использовать центр администрирования Microsoft Teams или Windows PowerShell для создания групп набора номера и управления ими (группы звонков по ЗВОНКОВ по НН).
ms.openlocfilehash: 44ecabfb04d8919ac289067818e736e170e6d181
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58728708"
---
# <a name="create-and-manage-dial-plans"></a>Создание и использование абонентских групп

После того как вы спланируйте наборные планы для своей организации и разберемся со всеми правилами нормализации, которые необходимо создать для голосовой маршрутизации, вы можете создать их. Если у учетной записи администратора есть действительная Teams, вы можете использовать центр администрирования Microsoft Teams или Windows PowerShell для создания телефонных планов и управления ими.  

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

### <a name="create-a-dial-plan"></a>Создание набора номера

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в **группу**  >  **голосового набора** номера .
2. Нажмите **кнопку** Добавить и введите имя и описание для набора номера.
    ![Снимок экрана: страница "Добавление" для создания набора номера.](media/create-dial-plan.png)
3. В **области Сведения о телефонной** линии укажите внешний префикс набора, если пользователям нужно набрать одну или несколько цифр (например, 9), чтобы получить внешнюю линию. Для этого выполните следующие действия:
    1. В поле **Внешний префикс набора** номера введите внешний префикс набора номера. Префикс может быть не более четырех символов (#,*и 0-9).
    2. Включите **оптимизированные наборы устройств**. Если вы указали внешний префикс набора номера, необходимо также включить этот параметр, чтобы применить префикс, чтобы звонки можно было делать за пределами организации.
4. В **области Правила нормализации** настройте и соберите одно или несколько правил нормализации [для](what-are-dial-plans.md#normalization-rules) плана набора номера. С каждой телефонной планом должно быть связано хотя бы одно правило нормализации.  Для этого сделайте следующее:
    - Чтобы создать новое правило нормализации и связать его с планом набора номера, нажмите кнопку Добавить **и** определите правило.
    - Чтобы изменить правило нормализации, уже связанное с планом набора номера, выберите его, щелкнув слева от имени правила и выбрав изменить **.** Внести нужные изменения и нажмите кнопку **Сохранить**.
    - Чтобы удалить правило нормализации из набора номера, выберите его, щелкнув слева от имени правила и выбрав **удалить**.
5. Расположить правила нормализации в нужном порядке. Нажмите **кнопку Вверх** **или** Вниз, чтобы изменить положение правил в списке.

    > [!NOTE]
    > Teams список правил нормализации сверху вниз и использует первое правило, которое соответствует набратому номеру. Если вы настроили план набора таким образом, чтобы набраный номер соответствует более чем одному правилу нормализации, убедитесь, что более строгие правила отсортировали над менее строгими. Если вы настроите телефонную шкалу, которая нормализует набраный номер без "+", служба звонков попытается снова нормализовать этот номер, используя правила клиентской и региональной телефонной карты. Чтобы избежать двойной нормализации, рекомендуется, чтобы все правила нормализации вылились в числа, начинались с "+". Клиенты прямой маршрутки могут использовать [правила](direct-routing-translate-numbers.md) перевода линии связи, чтобы при необходимости удалить "+". 

6. Нажмите кнопку **Сохранить**.
7. Если вы хотите проверить набор номеров, **введите** номер телефона в области Проверка телефонной программы, а затем нажмите кнопку **Проверить**.

### <a name="edit-a-dial-plan"></a>Изменение набора номера

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в **группу**  >  **голосового набора** номера .
2. Выберите план набора номера, щелкнув слева от ее имени и выбрав изменить **.**
3. Внести нужные изменения и нажмите кнопку **Сохранить.**

### <a name="assign-a-dial-plan-to-users"></a>Назначение набора номера пользователям

Вы назначаете план набора номера так же, как назначаете политики. [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a>С помощью PowerShell
  
### <a name="start-powershell"></a>Запуск PowerShell
- Откройте Windows PowerShell командную команду и запустите следующие команды:

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a>Создание телефонных планов и управление ими

Создание абонентских групп клиентов и управление ими можно осуществлять с помощью одиночного командлета или сценария PowerShell.
  
#### <a name="using-single-cmdlets"></a>С помощью одиночного командлета

- Чтобы создать новую телефонную план, запустите:
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Другие примеры и параметры см. в разделе [New-CsTenantDialPlan](/powershell/module/skype/new-cstenantdialplan).
    
- Чтобы изменить параметры существующей телефонной программы, запустите:
    
  ```PowerShell
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Другие примеры и параметры см. в разделе [Set-CsTenantDialPlan](/powershell/module/skype/set-cstenantdialplan).
    
- Чтобы добавить пользователей в абонентскую группу, запустите следующую команду:
    
  ```PowerShell
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Другие примеры и параметры см. в разделе [Grant-CsTenantDialPlan](/powershell/module/skype/grant-cstenantdialplan).
    
- Чтобы просмотреть параметры абонентской группы, запустите следующую команду:
    
  ```PowerShell
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Другие примеры и параметры см. в разделе [Get-CsTenantDialPlan](/powershell/module/skype/get-cstenantdialplan?view=skype-ps).
    
- Чтобы удалить абонентскую группу, запустите следующую команду:
    
  ```PowerShell
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Другие примеры и параметры см. в разделе [Remove-CsTenantDialPlan](/powershell/module/skype/remove-cstenantdialplan?view=skype-ps).
    
- Чтобы просмотреть параметры действующей абонентской группы, запустите следующую команду:
    
  ```PowerShell
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Другие примеры и параметры см. в разделе [Get-CsEffectiveTenantDialPlan](/powershell/module/skype/get-cseffectivetenantdialplan).
    
- Для проверки действующих параметров абонентской группы запустите следующую команду:
    
  ```PowerShell
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255550199 -Identity amos.marble@contoso.com
  ```

    Другие примеры и параметры см. в разделе [Test-CsEffectiveTenantDialPlan](/powershell/module/skype/test-cseffectivetenantdialplan?view=skype-ps).
    
#### <a name="using-a-powershell-script"></a>С помощью скрипта PowerShell

Чтобы удалить правило нормализации, связанное с клиентской телефонной планом, не нужно сначала удалять ее:
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

Запустите это, чтобы удалить все назначенное tenantDialPlan всех пользователей, у которых есть hostingProvider sipfed.online.lync.com.
```PowerShell
Get-CsOnlineUser -Filter {HostingProvider -eq "sipfed.online.lync.com"} | Grant-CsTenantDialPlan -policyname $null
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
- [Общие вопросы по передаче номеров телефонов](./phone-number-calling-plans/port-order-overview.md)
- [Типы номеров телефонов, используемые в планах звонков](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Управление номерами телефонов организации](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Условия и положения, распространяющиеся на экстренные вызовы](emergency-calling-terms-and-conditions.md)
- [Заявление об отказе от ответственности экстренных вызовов](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)
