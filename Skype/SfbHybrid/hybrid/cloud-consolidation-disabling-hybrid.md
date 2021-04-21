---
title: Отключение гибридной среды для завершения миграции в облако
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: В этой статье содержатся подробные действия по отключению гибрида в рамках консолидации облачных технологий для Teams и Skype для бизнеса.
ms.openlocfilehash: 08d305fa2650cffbadb0ec3122458f4a57e052a4
ms.sourcegitcommit: 8750f98d59e74e3835d762d510fb0e038c8f17eb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51899110"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-the-cloud"></a>Отключение гибридной конфигурации для завершения миграции в облако

В этой статье описывается отключение гибридной конфигурации до вывода из эксплуатации локальной среды Skype для бизнеса. Это шаг 2 из следующих действий по выводу из эксплуатации локальной среды:

- Этап 1. [Перемещение всех необходимых пользователей из локального в интернет.](decommission-move-on-prem-users.md)

- **Шаг 2. Отключите гибридную конфигурацию.** (В этой статье)

- Шаг 3. [Перемещение конечных точек гибридного приложения из локального в интернет.](decommission-move-on-prem-endpoints.md)

- Этап 4. [Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)


## <a name="overview"></a>Обзор

После обновления всех пользователей из локального Skype для бизнеса в Teams Только в Microsoft 365 можно выкипать локальное развертывание Skype для бизнеса. Прежде чем отключать локальное развертывание Skype для бизнеса и удалять любое оборудование, необходимо логически отделить локальное развертывание от Microsoft 365, отключив гибрид. Отключение гибрида состоит из следующих трех этапов:

1. Изменение DNS-записей, чтобы они указывали на Microsoft 365.

2. Отключение общего пространства адресов SIP (также известного как "раздельный домен") в организации Microsoft 365.

3. Отключить возможность локального общения с Microsoft 365.

Эти действия логически отделяют локальное развертывание Skype для бизнеса Server от Microsoft 365 и должны быть сделаны вместе как подразделение. Сведения о каждом шаге предоставляются в этой статье. По завершению развертывания Skype для бизнеса можно выписаться из эксплуатации с помощью одного из двух методов, на которые ссылается ниже.

> [!Important] 
> После завершения этого логического разделения атрибуты msRTCSIP из локального Active Directory по-прежнему будут иметь значения и будут синхронизироваться с помощью Azure AD Connect в Azure AD. Вывод локальной среды из эксплуатации зависит от того, собираетесь ли вы оставить эти атрибуты на месте или сначала очистить их от локального Active Directory. Следует помнить, что очистка атрибутов msRTCSIP на месте после миграции из локального помещения может привести к потере службы для пользователей! Подробные сведения и компромиссы двух подходов к выводу из эксплуатации описаны позже.

## <a name="detailed-steps"></a>Подробные действия

1. *Обновив DNS, указав на Microsoft 365.* Внешний DNS организации для локальной организации необходимо обновить, чтобы записи Skype для бизнеса указывают на Microsoft 365 вместо локального развертывания. Это означает следующее:

    |Тип записи|Имя|TTL|Value (Значение)|
    |---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100 1 5061 sipfed.online.lync. <span> com|
    |SRV|_sip._tls|3600|100 1 443 sipdir.online.lync. <span> com|
    |CNAME| lyncdiscover|   3600|   webdir.online.lync. <span> com|
    |CNAME| sip|    3600|   sipdir.online.lync. <span> com|

    Кроме того, записи CNAME для встречи или диалогов (если присутствуют) могут быть удалены. Наконец, все записи DNS для Skype для бизнеса во внутренней сети должны быть удалены.

    > [!Note] 
    > В редких случаях изменение DNS с локальной указать на Microsoft 365 для вашей организации может привести к остановке работы федерации с некоторыми другими организациями до тех пор, пока другая организация не обновит конфигурацию федерации:
    >
    > - Всем федератным организациям, использующим старую модель Direct Federation (также известный как Разрешенный сервер партнеров), необходимо обновить разрешенные записи домена для организации, чтобы удалить прокси-сервер FQDN. Эта устаревшая модель федерации не основана на записях SRV DNS, поэтому такая конфигурация станет устаревшей после перемещения организации в облако.
    > 
    > - Любая федераированная организация, у нее нет включенного поставщика хостинга для sipfed.online.lync. <span> com необходимо обновить конфигурацию, чтобы включить это. Такая ситуация возможна только в том случае, если федератерная организация является чисто локальной и никогда не федератовывалась с любым гибридным или сетевым клиентом. В этом случае федерация с этими организациями не будет работать до тех пор, пока они не увявят поставщика хостинга.
    >
    > Если вы подозреваете, что любой из ваших федеративных партнеров может использовать Direct Federation или не был федеративен в какой-либо сетевой или гибридной организации, мы рекомендуем отправить им сообщение об этом при подготовке к завершению миграции в облако.


2.  *Отключение общего пространства адресов SIP в организации Microsoft 365.* Команда, приведенная ниже, должна быть сделана из окна Skype для бизнеса Online PowerShell.

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  *Отключить возможность локального общения с Microsoft 365.* Команда, приведенная ниже, должна быть сделана из локального окна PowerShell:

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a>Управление атрибутами после перемещения пользователей из локального в облако

По умолчанию все пользователи, которые ранее были включены для Skype для бизнес-сервера и впоследствии перемещены в облако, по-прежнему имеют атрибуты msRTCSIP, настроенные в локальном Active Directory. Эти атрибуты, в частности SIP-адрес (msRTCSIP-PrimaryUserAddress) и потенциально номер телефона (msRTCSIP-Line), продолжают синхронизироваться с Azure AD. Если требуется изменить любой из атрибутов msRTCSIP, эти изменения необходимо внести в локальном Active Directory, а затем синхронизировать его с Azure AD. Однако после удаления развертывания Skype для бизнес-сервера средства Skype для бизнеса Server будут недоступны для управления этими атрибутами.

Существует два варианта обработки этой ситуации:

1. Оставьте пользователей, включенных для учетных записей серверов Skype для бизнеса, и управляйте атрибутами msRTCSIP с помощью средств Active Directory. Это обеспечивает отсутствие потери службы для перенесенных пользователей и позволяет легко удалить развертывание Skype для бизнес-сервера, устранив (например, удаление) серверов без полного вывода из эксплуатации. Однако новые лицензированные пользователи не будут иметь эти атрибуты, заполняемые в локальном каталоге Active Directory, и им необходимо управлять в Интернете.

2.  Очистить все атрибуты msRTCSIP от перенесенных пользователей в локальном Каталоге Active Directory и управлять этими атрибутами с помощью сетевых средств. Этот метод позволяет использовать последовательный подход к управлению для существующих и новых пользователей, однако он потенциально может привести к временной потере службы во время локального процесса вывода из эксплуатации.


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Метод 1 . Управление SIP-адресами и номерами телефонов для пользователей Active Directory

Администраторы могут управлять пользователями, которые ранее были перемещены из локального Skype для бизнес-сервера в облако даже после вывода из эксплуатации локального развертывания. Если вы хотите внести изменения в SIP-адрес пользователя или номер телефона пользователя (а sip-адрес или номер телефона уже имеет значение в локальном Active Directory), необходимо сделать это в локальном Active Directory и позволить значению (s) перетекать в Azure AD. Для этого не требуется локальное skype для бизнеса Server. Скорее, эти атрибуты можно изменить непосредственно в локальном Active Directory, используя либо оснастку MMC пользователей Active Directory и компьютеров (как показано ниже), либо с помощью PowerShell. Если вы используете оснастку MMC, откройте страницу свойств пользователя, нажмите кнопку Редактор атрибута и найдите соответствующие атрибуты для изменения:

- Чтобы изменить SIP-адрес пользователя, измените `msRTCSIP-PrimaryUserAddress` .

    > [!NOTE]
    > Если атрибут `ProxyAddresses` содержит SIP-адрес, также обнови это значение в качестве наилучшей практики. Несмотря на то, что адрес SIP в случае заполнения игнорируется O365, он может использоваться другими компонентами `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` локального использования.

- Чтобы изменить телефонный номер пользователя, `msRTCSIP-Line` *измените, если он уже имеет значение*.

  ![Средство для пользователей и компьютеров Active Directory](../media/disable-hybrid-1.png)
  
-  Если у пользователя изначально не было значения для локального перед перемещением, можно изменить номер телефона с помощью параметра `msRTCSIP-Line` в командлете `onpremLineUri` [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) в модуле Skype для бизнеса Online PowerShell.

Эти действия не являются необходимыми для новых пользователей, созданных после отключения гибрида, и управлять этими пользователями можно непосредственно в облаке. Если вам удобно использовать сочетание этих методов, а также оставить атрибуты msRTCSIP на месте в локальном Active Directory, вы можете просто повторно образ локального Skype для бизнеса серверов. Однако, если вы предпочитаете очистить все атрибуты msRTCSIP и сделать традиционный удалить Skype для бизнеса Server, используйте метод 2.


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Метод 2 . Очистить атрибуты Skype для бизнеса для всех пользователей в Active Directory

Этот параметр требует дополнительных усилий и надлежащего планирования, так как пользователи, которые ранее были перемещены из локального Skype для бизнеса Server в облако, должны быть повторно продвинуты. Эти пользователи могут быть классифицированы на две разные категории: пользователи без телефонной системы и пользователи с телефонной системой. Пользователи с телефонной системой будут испытывать временную потерю телефонной службы в рамках перехода номера телефона из управления в локальном Active Directory в облако. **Перед началом массовых операций рекомендуется выполнить пилотную работу с небольшим числом пользователей с телефонной системой.** Для больших развертывания пользователи могут обрабатываться в небольших группах в разных окнах времени. 

> [!NOTE] 
> Этот процесс прост для пользователей, у которых есть совпадающий sip-адрес и UserPrincipalName. Для организаций, у пользователей с не совпадающих значений между этими двумя атрибутами, необходимо принять дополнительные меры, как отмечено ниже, для плавного перехода.

> [!NOTE]
> Если вы настроили конечные точки гибридного приложения для автоспутников или очередей вызовов, не забудьте переместить эти конечные точки в Microsoft 365 перед списанием Skype для бизнеса Server.


1. Подтверждение следующего локального cmdlet Skype для бизнеса PowerShell возвращает пустой результат. Пустой результат означает, что пользователи не находятся в локальном помещении и либо были перемещены в Microsoft 365, либо отключены:

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Запись текущего номера телефонов пользователей (LineUri), UserPrincipalName и связанных с ними данных, выполнив для экспорта пользовательских данных следующие пользовательские данные на локальном сервере Skype для бизнеса Server PowerShell:

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Перед открытием SfbUserSettings.csv файл и подтверждение успешного экспорта всех пользовательских данных. Рекомендуется хранить копию этого файла.  Не используйте этот файл в следующих действиях для обработки пользователей. 

3. Создайте файл с группой пользователей, который будет использоваться в следующих действиях. После успешного завершения работы первой группы пользователей приступим к следующей группе пользователей. В приведенном ниже примере группы пользователей выбираются в алфавитном порядке, но можно фильтровать пользователей на основе критериев, которые соответствуют тому, как вы хотите обрабатывать пользователей.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Перед открытием SfbUsers.csv файл и подтверждение успешного экспорта пользовательских данных. На более позднем этапе вам потребуется LineUri (номер телефона), UserPrincipalName, SamAccountName и SipAddress из этого файла.

4. Удалите сведения о атрибутах, связанных со Skype для бизнеса Server, из active Directory для набора пользователей, которые вы готовы обновить.  Существует 2 шага к этому процессу, как показано ниже.

   > [!Important] 
   > После следующего цикла синхронизации AAD после запуска этого шага пользователи с телефонной системой, которые ранее были перемещены из локального Skype для бизнеса Server в облако, потеряют возможность выполнять и принимать вызовы до тех пор, пока этап 8 не будет успешно завершен и подтвержден на шаге 9. Кроме того, убедитесь, что на шаге 2 сохранены номера телефонов и связанные сведения пользователя, так как эта информация необходима для этого шага.

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   Далее, для того же набора пользователей, очистить значение msRTCSIP-DeploymentLocator с помощью локального Active Directory PowerShell:

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. Запустите следующий локальном модуле Active Directory для командлета Windows PowerShell, чтобы добавить значение sip-адреса обратно в локальное прокси-серверы Active Directory. Это позволит предотвратить проблемы с интероперабельностью, которые зависят от этого атрибута. 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. Выполнить синхронизацию Azure AD

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. Подождите, пока подготовка пользователей завершится. Вы можете отслеживать ход подготовка пользователей, запуская следующую команду Skype для бизнеса Online PowerShell. Следующая команда Skype для бизнеса Online PowerShell возвращает пустой результат по мере завершения процесса.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. Выполните следующую команду Skype для бизнеса Online PowerShell, чтобы назначить номера телефонов и включить пользователей для телефонной системы:
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  Если у вас по-прежнему есть конечные точки Skype для бизнеса (клиенты Skype или телефоны 3-й стороны), вам также необходимо установить -HostedVoiceMail для $true. Если ваша организация использует только конечные точки Teams для пользователей с включенной голосовой поддержкой, этот параметр не применим к пользователям. 

9. Подтвердит правильность работы пользователей с функциями телефонной системы. Следующая команда Skype для бизнеса Online PowerShell возвращает пустой результат по мере завершения процесса.

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. Повторите действия от 3 до 9 до тех пор, пока все пользователи не будут обработаны.

11. Подтверди, что все пользователи успешно обработаны, запуская следующие две команды PowerShell.

    Локальное командное приложение Skype для бизнес-сервера PowerShell:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    Команда Skype для бизнеса Online PowerShell:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. После завершения всех действий в методе 2 см. в рубке Перемещение конечных точек гибридного приложения из локального в интернет и удаление локального [skype для](decommission-remove-on-prem.md) бизнеса Server для дополнительных действий по удалению локального развертывания Skype для бизнес-сервера. [](decommission-move-on-prem-endpoints.md)


## <a name="see-also"></a>См. также

- [Консолидация облаков для команд и Skype для бизнеса](cloud-consolidation.md)

- [Прекращение использования локальной среды Skype для бизнеса](decommission-on-prem-overview.md)

