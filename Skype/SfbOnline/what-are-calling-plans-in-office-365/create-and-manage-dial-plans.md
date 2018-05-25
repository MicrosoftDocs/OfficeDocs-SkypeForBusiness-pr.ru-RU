---
title: Создание и управление ими абонентских групп
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mikedav, roykuntz, jastark
ms.topic: article
ms.assetid: 7af17c94-5f8f-4452-ae1d-01f495b4dc94
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Calling Plans
description: 'Сведения о создании вызова абонентских групп (вызов ТСОП абонентских групп) в Office 365 и управлять ими. '
ms.openlocfilehash: 5390765db0d70acb789c6dcf4a2fd4dc488e613e
ms.sourcegitcommit: f76ac33ae47eafa2ae853cc031b6ac53c2d4fbbd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/25/2018
---
# <a name="create-and-manage-dial-plans"></a>Создание и управление ими абонентских групп

После запланированных абонентские группы для вашей организации и поняли все правила нормализации, которые необходимо создать для маршрутизации вызовов, необходимо использовать Windows PowerShell для создания абонентских групп и измените параметр.
  
> [!NOTE]
> Скайп по центру администрирования бизнес не может использоваться для создания и управления абонентских групп. 
  
## <a name="verifying-and-starting-remote-powershell"></a>Проверка и запуск удаленной оболочки PowerShell

 **Убедитесь в том, что у вас установлена оболочка Windows PowerShell 3.0 или более поздней версии**
  
1. To verify that you are running version 3.0 or higher: **Start Menu** > **Windows PowerShell**.
    
2. Проверьте версию, введя в окне _Windows PowerShell_ команду **Get-Host**.
    
3. Если у вас более ранняя версия, вам необходимо скачать и установить обновления для Windows PowerShell. Чтобы скачать и обновить Windows PowerShell до версии 4.0, перейдите на страницу [Windows Management Framework 4.0](https://go.microsoft.com/fwlink/?LinkId=716845). При появлении запроса перезагрузите компьютер.
    
4. Вам также потребуется установить модуль Windows PowerShell для Skype для бизнеса online, с помощью которого можно создать удаленный сеанс Windows PowerShell с подключением к Skype для бизнеса online. Этот модуль, который поддерживается только на 64-разрядных компьютерах, можно скачать в Центре загрузки Майкрософт на странице [Модуль Windows PowerShell для Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=294688). При появлении запроса перезагрузите компьютер.
    
Больше информации приведено в статье [Подключение ко всем службам Office 365 с помощью единого окна Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx).
  
 **Запуск сеанса Windows PowerShell**
  
1. From the **Start Menu** > **Windows PowerShell**.
    
2. В окне **Windows PowerShell** подключитесь к организации Office 365, выполнив следующую команду:
    
    > [!NOTE]
    > Команду **Import-Module** нужно запускать только при первом использовании модуля Windows PowerShell в Skype для бизнеса Online.
  
> 
  ```
    Import-Module "C:\\Program Files\\Common Files\\Skype for Business Online\\Modules\\SkypeOnlineConnector\\SkypeOnlineConnector.psd1"
    $credential = Get-Credential
    $session = New-CsOnlineSession -Credential $credential
    Import-PSSession $session
  ```

Дополнительные сведения о запуске Windows PowerShell, см [подключиться ко всем службам Office 365 в одном окне Windows PowerShell](https://technet.microsoft.com/EN-US/library/dn568015.aspx) или [подключение к Скайп для бизнеса в Интернет с помощью Windows PowerShell](https://technet.microsoft.com/en-us/library/dn362795%28v=ocs.15%29.aspx).
  
## <a name="creating-and-managing-your-dial-plans"></a>Создание и управление абонентских

Создание и управление ими абонентских групп клиентов можно использовать либо одного командлета или сценария PowerShell.
  
### <a name="using-single-cmdlets"></a>С помощью одного командлетов

- Чтобы создать новую абонентскую группу, выполните следующую команду:
    
  ```
  New-CsTenantDialPlan -Identity RedmondDialPlan -Description "Dial Plan for Redmond" -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9 -SimpleName "Dial-Plan-for-Redmond"
  ```

    Другие примеры и параметры в разделе [New-CsTenantDialPlan](https://technet.microsoft.com/library/mt775026.aspx).
    
- Внесение изменений в существующую абонентскую группу, выполните следующую команду:
    
  ```
  Set-CsTenantDialPlan -Identity RedmondDialPlan  -NormalizationRules <pslistmodifier> -ExternalAccessPrefix 9
    -SimpleName "Dial-Plan-for-Redmond"
  ```

    Другие примеры и параметры в разделе [Set-CsTenantDialPlan](https://technet.microsoft.com/library/mt775023.aspx).
    
- Чтобы добавить пользователей в абонентской группе, выполните следующую команду:
    
  ```
  Grant-CsTenantDialPlan -Identity amos.marble@contoso.com -PolicyName RedmondDialPlan
  ```

    Другие примеры и параметры в разделе [Предоставление CsTenantDialPlan](https://technet.microsoft.com/library/mt775021.aspx).
    
- Чтобы просмотреть параметры в абонентской группе, выполните следующую команду:
    
  ```
  Get-CsTenantDialPlan -Identity RedmondDialPlan
  ```

    Другие примеры и параметры в разделе [Get-CsTenantDialPlan](https://technet.microsoft.com/library/mt775024.aspx).
    
- Чтобы удалить абонентской группы, выполните следующую команду:
    
  ```
  Remove-CsTenantDialPlan -Identity RedmondDialPlan -force
  ```

    Другие примеры и параметров в разделе [Remove CsTenantDialPlan](https://technet.microsoft.com/library/mt775020.aspx).
    
- Чтобы просмотреть параметры действующих абонентскую группу, выполните следующую команду:
    
  ```
  Get-CsEffectiveTenantDialPlan -Identity amos.marble@contoso.com
  ```

    Другие примеры и параметры в разделе [Get-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775022.aspx).
    
- Для проверки действующих параметров в абонентской группе, выполните следующую команду:
    
  ```
  Test-CsEffectiveTenantDialPlan -DialedNumber 14255551234 -Identity 1849827b-a810-40a8-8f77-e94250d4680b_US_TenantDialPlanRedmond
  ```

    Другие примеры и параметры в разделе [Test-CsEffectiveTenantDialPlan](https://technet.microsoft.com/library/mt775025.aspx).
    
### <a name="using-a-powershell-script"></a>С помощью скрипта PowerShell

Выполните это для удаления правила нормализации, который связан с клиента абонентской группы без необходимости сначала удаление абонентской клиента:
```
$b1=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$b1}
(Get-CsTenantDialPlan -Identity RedmondDialPlan).NormalizationRules
$b2=New-CsVoiceNormalizationRule -Identity Global/NR4 -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$b2}
```
Запустите следующие правила нормализации Добавление существующего клиента абонентскую группу с именем RedmondDialPlan.
```
$nr1=New-CsVoiceNormalizationRule -Parent Global -Description 'Organization extension dialing' -Pattern '^(\\d{3})$' -Translation '+14255551$1' -Name NR1 -IsInternalExtension $false -InMemory
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{add=$nr1}
```
Выполните это для удаления следующее правило нормализации из существующего клиента абонентская группа с именем RedmondDialPlan.
```
$nr1=New-CsVoiceNormalizationRule -Parent Global/NR1 -InMemory
Set-CsTenantDialPlan -Identity DP1 -NormalizationRules @{remove=$nr1}
```

Когда необходимо также проверить существующие правила нормализации, определить, какой из них нужно удалить и затем использовать его индексу удаляет его, выполните следующие действия. Массив правил нормализации начинается с индексом 0. Мы предлагаем для удаления правила нормализации цифра 3, чтобы он индекса 1.
  
```
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

$nr1=(Get-CsTenantDialPlan RedmondDialPlan).NormalizationRules[Number 1]
Set-CsTenantDialPlan -Identity RedmondDialPlan -NormalizationRules @{remove=$nr1}
```

Выполните это для поиска всех пользователей, которым были присвоены RedmondDialPlan клиента абонентская группа.
  
```
Get-CsOnlineuser | where-Object {$_.TenantDialPlan -eq "RedmondDialPlan"}
```

Выполните эти для добавления существующих локальных абонентская группа с именем OPDP1 как в абонентской группе клиента для вашей организации. Необходимо сначала сохранить в локальной абонентская группа в XML-файл, а затем использовать для создания новой абонентской клиента.
  
Выполните это для сохранения локальной единой системы обмена сообщениями в XML-файл.
  
```
$DPName = "OPDP1"
$DPFileName = "dialplan.xml"
Get-CsDialplan $DPName | Export-Clixml $DPFileName
```

Выполните это для создания новой абонентской клиента.
  
```
$DPFileName = "dialplan.xml"
$DP = Import-Clixml $DPFileName
$NormRules = @()
ForEach($nr in $dp.NormalizationRules)
{
 $id1 = "Global/" +$nr.Name
$nr2 = New-CsVoiceNormalizationRule -Identity $id1 -Description $nr.Description -Pattern $nr.Pattern -Translation $nr.Translation  -IsInternalExtension $nr.IsInternalExtension -InMemory
$NormRules += $nr2
}
New-CsTenantDialPlan -Identity $dp.SimpleName -ExternalAccessPrefix $dp.ExternalAccessPrefix -Description $dp.Description -OptimizeDeviceDialing $dp.OptimizeDeviceDialing -SimpleName $dp.SimpleName -NormalizationRules $NormRules
```
## <a name="want-to-know-more-about-windows-powershell"></a>Хотите узнать больше о Windows Powershell?

- Windows PowerShell is all about managing users and what users are allowed or not allowed to do. С помощью Windows PowerShell вы можете управлять Office 365 и Skype для бизнеса online, используя единый центр администрирования, который упростит выполнение ваших повседневных задач. Чтобы начать работу с Windows PowerShell, ознакомьтесь с приведенными ниже разделами.
    
  - [Введение в Windows PowerShell и Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Шесть причин использовать Windows PowerShell для управления Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- Windows PowerShell имеет множество преимуществ в скорости, простоте и эффективности работы по сравнению с использованием только Центра администрирования Office 365, например при внесении изменений для множества пользователей одновременно. Подробнее об этих преимуществах можно узнать в следующих разделах:
    
  - [Лучшие способы управления Office 365 с помощью Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Использование Windows PowerShell для управления Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Использование возможностей Windows PowerShell для выполнения стандартных задач управления средой Skype для бизнеса Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>See also
[Общие вопросы по передаче номеров телефонов](transferring-phone-numbers-common-questions.md)

[Типы номеров телефонов, используемые в планах звонков](different-kinds-of-phone-numbers-used-for-calling-plans.md)

[Управление номерами телефонов организации](../what-are-calling-plans-in-office-365/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md)

[Условия и положения, распространяющиеся на экстренные вызовы](../legal-and-regulatory/emergency-calling-terms-and-conditions.md)

[Skype для бизнеса Online: заявление об отказе для звонков в экстренные службы](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Skype/SfbOnline/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)

  
 