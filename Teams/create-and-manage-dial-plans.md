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
- seo-marvel-apr2020
description: Узнайте, как создавать и управлять группами набора Windows PowerShell с помощью Центра администрирования Microsoft Teams или службы Windows PowerShell (телефонные группы для звонков по СТАНП).
ms.openlocfilehash: 8e1d3a102d762bef29ecd3af7998646239b5f0c2
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569262"
---
# <a name="create-and-manage-dial-plans"></a>Создание и использование абонентских групп

После того как вы спланируйте наборы для своей организации и выясните все правила нормализации, которые необходимо создать для маршрутизации вызовов, вы можете при необходимости создать эти наборы. Вы можете использовать Центр администрирования Microsoft Teams или Windows PowerShell для создания телефонных групп и управления ими.  

## <a name="using-the-microsoft-teams-admin-center"></a>С помощью Центра администрирования Microsoft Teams

### <a name="create-a-dial-plan"></a>Создание набора номера

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в группу  >  **голосового набора.**
2. Нажмите **кнопку**"Добавить" и введите имя и описание для набора номера.
    ![Снимок экрана: страница добавления для создания набора номера](media/create-dial-plan.png)
3. В **области сведений о** телефонной линии укажите внешний префикс набора, если пользователям нужно набрать одну или несколько цифр (например, 9), чтобы получить внешнюю линию. Для этого выполните следующие действия:
    1. В поле **внешнего префикса набора** номера введите внешний префикс набора номера. Префикс может быть не более четырех символов (#,*и 0-9).
    2. Включите **набор номера оптимизированных устройств.** Если указать внешний префикс набора номера, необходимо также включить этот параметр, чтобы применить префикс, чтобы звонки можно было делать за пределами организации.
4. В **области "Правила нормализации"** настройте и соберите одно или несколько правил [нормализации](what-are-dial-plans.md#normalization-rules) для набора номера. С каждой телефонной планом должно быть связано хотя бы одно правило нормализации.  Для этого сделайте следующее:
    - Чтобы создать новое правило нормализации и связать его с телефонной планом, нажмите кнопку "Добавить" **и** определите правило.
    - Чтобы изменить правило нормализации, которое уже связано с ней, выберите его, щелкнув слева от его имени и нажав кнопку **"Изменить".** Внести нужные изменения и нажмите кнопку **"Сохранить".**
    - Чтобы удалить правило нормализации из набора номера, выберите его, щелкнув слева от имени правила и нажав кнопку **"Удалить".**
5. Расположить правила нормализации в нужном порядке. Нажмите **кнопку "Переместить** **вверх"** или "Вниз", чтобы изменить положение правил в списке.

    > [!NOTE]
    > Teams проходит по списку правил нормализации сверху вниз и использует первое правило, которое соответствует набратому номеру. Если настроена так, что набрано номер может соответствовать более чем одному правилу нормализации, убедитесь, что более строгие правила отсортировали над менее строгими.

6. Щелкните **Сохранить**.
7. Если вы хотите проверить набережную, введите номер телефона в области "Тестирование набора номера" и нажмите кнопку **"Проверка".** 

### <a name="edit-a-dial-plan"></a>Изменение набора номера

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в группу  >  **голосового набора.**
2. Выберите план набора, щелкнув слева от ее имени и нажав кнопку **"Изменить".**
3. Внести нужные изменения и нажмите кнопку **"Сохранить".**

### <a name="assign-a-dial-plan-to-users"></a>Назначение пользователям набора номера

Вы назначаете план набора номера таким же образом, как и политики. [!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="using-powershell"></a>С помощью PowerShell
  
### <a name="start-powershell"></a>Запуск PowerShell
- Откройте Windows PowerShell и запустите следующие команды:

```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
```
  
### <a name="create-and-manage-your-dial-plans"></a>Создание телефонных планов и управление ими

Создание абонентских групп клиентов и управление ими можно осуществлять с помощью одиночного командлета или сценария PowerShell.
  
#### <a name="using-single-cmdlets"></a>С помощью одиночного командлета

- Чтобы создать новую телефонную план, запустите ную экономию:
    
  ```PowerShell
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Другие примеры и параметры см. в разделе [New-CsTenantDialPlan](https://docs.microsoft.com/powershell/module/skype/new-cstenantdialplan).
    
- Чтобы изменить параметры существующей телефонной программы, запустите параметров:
    
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

Запустите этот запуск, чтобы удалить все назначенное tenantDialPlan для всех пользователей, у которых есть sipfed.online.lync.com.
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
- [Общие вопросы по передаче номеров телефонов](transferring-phone-numbers-common-questions.md)
- [Типы номеров телефонов, используемые в планах звонков](different-kinds-of-phone-numbers-used-for-calling-plans.md)
- [Управление номерами телефонов организации](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)
- [Условия и положения, распространяющиеся на экстренные вызовы](emergency-calling-terms-and-conditions.md)
- [Метка заявление об отказе для экстренных вызовов](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)
- [Обзор PowerShell в Teams](teams-powershell-overview.md)
