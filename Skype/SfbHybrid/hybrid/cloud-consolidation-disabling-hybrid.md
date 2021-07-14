---
title: Отключить гибрид для завершения миграции в Teams Только
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
description: В этой статье содержатся подробные действия по отключению гибрида в рамках консолидации облачных Teams и Skype для бизнеса.
ms.openlocfilehash: 97681f4e9306336874ba4d9428a273b1d31519db
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420844"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a>Отключение гибридной конфигурации для завершения миграции в Teams Only 

В этой статье описывается отключение гибридной конфигурации перед выводом из эксплуатации локальной Skype для бизнеса среды. Это шаг 2 из следующих действий по выводу из эксплуатации локальной среды:

- Этап 1. [Перемещение всех необходимых пользователей из локального в интернет.](decommission-move-on-prem-users.md)

- **Шаг 2. Отключите гибридную конфигурацию.** (В этой статье)

- Этап 3. [Перенос конечных точек](decommission-move-on-prem-endpoints.md)гибридных приложений из локального в онлайн.

- Этап 4. [Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)

> [!NOTE]
> Этапы 2 и 3 должны быть сделаны в одном окне обслуживания, так как существующие конечные точки гибридного приложения не будут обнаружены между этапами 2 и завершением шага 3.

## <a name="overview"></a>Обзор

После обновления всех пользователей из локального Skype для бизнеса до Teams только в Microsoft 365, вы можете списание локального Skype для бизнеса развертывания. Прежде чем отключать локальное развертывание Skype для бизнеса и удалять оборудование, необходимо логически отделить локальное развертывание от Microsoft 365 путем отключения гибрида. Отключение гибрида состоит из следующих четырех действий:

1. Изменение DNS-записей, чтобы они указывали на Microsoft 365.

2. Измените режим сосуществования для организации на Teams Только.

3. Отключение общего пространства адресов SIP (также известного как "раздельный домен") в Microsoft 365 организации.

4. Отключить возможность локального общения с Microsoft 365.

Эти действия логически отделяют локальное развертывание Skype для бизнеса Server от Microsoft 365 и гарантируют полную Teams только. Сведения о каждом шаге предоставляются в этой статье. По завершению развертывания можно списание локального Skype для бизнеса с помощью одного из двух методов, на которые ссылается ниже.

> [!Important] 
> После завершения этого логического разделения атрибуты msRTCSIP из локального Active Directory по-прежнему будут иметь значения и будут синхронизироваться с помощью Azure AD Подключение в Azure AD. Вывод локальной среды из эксплуатации зависит от того, собираетесь ли вы оставить эти атрибуты на месте или сначала очистить их от локального Active Directory. Следует помнить, что очистка атрибутов msRTCSIP на месте после миграции из локального помещения может привести к потере службы для пользователей! Подробные сведения и компромиссы двух подходов к выводу из эксплуатации описаны позже.

## <a name="detailed-steps"></a>Подробные действия

1. *Обновление DNS, чтобы указать на Microsoft 365.* Внешние DNS организации для локальной организации должны быть обновлены таким образом, чтобы Skype для бизнеса записи указывают на Microsoft 365 вместо локального развертывания. Это означает следующее:

    |Тип записи|Имя|TTL|Priority|Насыщенность|Порт|Value (Значение)|
    |---|---|---|---|---|---|---|
    |SRV|_sipfederationtls._tcp|3600|100|1|5061|sipfed.online.lync. <span> com|
    |SRV|_sip._tls|3600|100|1|443|sipdir.online.lync. <span> com|
    |CNAME| lyncdiscover|   3600| | | |webdir.online.lync. <span> com|
    |CNAME| sip|    3600| | | | sipdir.online.lync. <span> com|

    Кроме того, записи CNAME для встречи или диалогов (если присутствуют) могут быть удалены. Наконец, все записи DNS для Skype для бизнеса во внутренней сети должны быть удалены.

    > [!Note] 
    > В редких случаях изменение DNS с указать на Microsoft 365 для организации может привести к остановке работы федерации с некоторыми другими организациями до тех пор, пока другая организация не обновит конфигурацию федерации:
    >
    > - Всем федератным организациям, использующим старую модель Direct Federation (также известный как Разрешенный сервер партнеров), необходимо обновить разрешенные записи домена для организации, чтобы удалить прокси-сервер FQDN. Эта устаревшая модель федерации не основана на записях SRV DNS, поэтому такая конфигурация станет устаревшей после перемещения организации в облако.
    > 
    > - Любая федераированная организация, у нее нет включенного поставщика хостинга для sipfed.online.lync. <span> com необходимо обновить конфигурацию, чтобы включить это. Такая ситуация возможна только в том случае, если федератерная организация является чисто локальной и никогда не федератовывалась с любым гибридным или сетевым клиентом. В этом случае федерация с этими организациями не будет работать до тех пор, пока они не увявят поставщика хостинга.
    >
    > Если вы подозреваете, что любой из ваших федеративных партнеров может использовать Direct Federation или не был федеративен в какой-либо сетевой или гибридной организации, мы рекомендуем отправить им сообщение об этом при подготовке к завершению миграции в облако.

2.  *Измените режим сосуществования для организации на Teams Только.* Это гарантирует, что любой новый пользователь в организации всегда создается как Teams только пользователь. Кроме того, попытка изменить режим клиента на Teams только автоматически проверяет наличие каких-либо локальной DNS-записей, которые могли быть пропущены на шаге 1, и определяет эти записи в выходе.  Изменение режима клиента на Teams только не удастся до тех пор, пока не будут обновлены все записи DNS для вашего organisaiton. Чтобы изменить режим клиента на Teams выполнить только следующую команду из окна Teams PowerShell.

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
     ```
Кроме того, вы можете использовать центр администрирования Teams для изменения режима сосуществования клиента на TeamsOnly в соответствии с "Настройками на всей организации" -> "Teams обновление".    
    
3.  *Отключение общего пространства адресов sip в Microsoft 365 организации.* Команда ниже должна быть сделана из окна Teams PowerShell.

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
4.  *Отключить возможность локального общения с Microsoft 365.* Команда, приведенная ниже, должна быть сделана из локального окна PowerShell:

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a>Управление атрибутами после перемещения пользователей из локального в облако

По умолчанию все пользователи, которые ранее были включены для Skype для бизнеса Server и впоследствии перемещены в облако, по-прежнему имеют атрибуты msRTCSIP, настроенные в локальном Active Directory. Эти атрибуты, в частности SIP-адрес (msRTCSIP-PrimaryUserAddress) и потенциально номер телефона (msRTCSIP-Line), продолжают синхронизироваться с Azure AD. Если требуется изменить любой из атрибутов msRTCSIP, эти изменения необходимо внести в локальном Active Directory, а затем синхронизировать его с Azure AD. Однако после удаления Skype для бизнеса Server, Skype для бизнеса Server средства управления этими атрибутами будут недоступны.

Существует два варианта обработки этой ситуации:

1. Оставьте пользователей, включенных для Skype для бизнеса серверных учетных записей, как есть, и управляйте атрибутами msRTCSIP с помощью средств Active Directory. Это обеспечивает отсутствие потери службы для перенесенных пользователей и позволяет легко удалить развертывание Skype для бизнеса Server путем удаления (например, удаления) серверов без полного вывода из эксплуатации. Однако новые лицензированные пользователи не будут иметь эти атрибуты, заполняемые в локальном каталоге Active Directory, и им необходимо управлять в Интернете.

2.  Очистить все атрибуты msRTCSIP от перенесенных пользователей в локальном Каталоге Active Directory и управлять этими атрибутами с помощью сетевых средств. Этот метод позволяет использовать последовательный подход к управлению для существующих и новых пользователей, однако он потенциально может привести к временной потере службы во время локального процесса вывода из эксплуатации.


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Метод 1 . Управление SIP-адресами и номерами телефонов для пользователей Active Directory

Администраторы могут управлять пользователями, которые ранее были перемещены из локального Skype для бизнеса Server в облако, даже после вывода из эксплуатации локального развертывания. Если вы хотите внести изменения в SIP-адрес пользователя или номер телефона пользователя (а sip-адрес или номер телефона уже имеет значение в локальном Active Directory), необходимо сделать это в локальном Active Directory и позволить значению (s) перетекать в Azure AD. Для этого не требуется локальное Skype для бизнеса Server. Скорее, эти атрибуты можно изменить непосредственно в локальном Active Directory, используя либо оснастку MMC пользователей Active Directory и компьютеров (как показано ниже), либо с помощью PowerShell. Если вы используете оснастку MMC, откройте страницу свойств пользователя, нажмите кнопку Редактор атрибута и найдите соответствующие атрибуты для изменения:

- Чтобы изменить SIP-адрес пользователя, измените `msRTCSIP-PrimaryUserAddress` .

    > [!NOTE]
    > Если атрибут `ProxyAddresses` содержит SIP-адрес, также обнови это значение в качестве наилучшей практики. Несмотря на то, что адрес SIP в случае заполнения игнорируется O365, он может использоваться другими компонентами `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` локального использования.

- Чтобы изменить телефонный номер пользователя, `msRTCSIP-Line` *измените, если он уже имеет значение*.

  ![Средство для пользователей и компьютеров Active Directory](../media/disable-hybrid-1.png)
  
-  Если у пользователя изначально не было значения для локального перед перемещением, можно изменить номер телефона с помощью параметра `msRTCSIP-Line` в командлете `onpremLineUri` [Set-CsUser](/powershell/module/skype/set-csuser?view=skype-ps) в модуле Skype для бизнеса Online PowerShell.

Эти действия не являются необходимыми для новых пользователей, созданных после отключения гибрида, и управлять этими пользователями можно непосредственно в облаке. Если вам удобно использовать сочетание этих методов, а также оставить атрибуты msRTCSIP на месте в локальном Active Directory, вы можете просто повторно образ локального Skype для бизнеса серверов. Однако если вы предпочитаете очистить все атрибуты msRTCSIP и сделать традиционный Skype для бизнеса Server, используйте Метод 2.


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Метод 2 . Skype для бизнеса атрибуты для всех локального пользователя в Active Directory

Этот параметр требует дополнительных усилий и надлежащего планирования, так как пользователи, которые ранее были перемещены из локального Skype для бизнеса Server в облако, должны быть повторно продвинуты. Эти пользователи могут быть классифицированы на две разные категории: пользователи без телефонная система и пользователи с телефонная система. Пользователи с телефонная система будут испытывать временную потерю телефонной службы в рамках перехода номера телефона от управления в локальном Active Directory в облако. **Перед началом массовых операций рекомендуется выполнить пилотную работу с небольшим числом пользователей с телефонная система пользователями.** Для больших развертывания пользователи могут обрабатываться в небольших группах в разных окнах времени. 

> [!NOTE] 
> Этот процесс прост для пользователей, у которых есть совпадающий sip-адрес и UserPrincipalName. Для организаций, у пользователей с не совпадающих значений между этими двумя атрибутами, необходимо принять дополнительные меры, как отмечено ниже, для плавного перехода.

> [!NOTE]
> Если вы настроили конечные точки гибридного приложения для автоспутников или очередей вызовов, не забудьте переместить эти конечные точки в Microsoft 365 до вывода из эксплуатации Skype для бизнеса Server.


1. Подтверждение следующего локального Skype для бизнеса PowerShell возвращает пустой результат. Пустой результат означает, что пользователи не находятся в локальном помещении и не были перемещены в Microsoft 365 или отключены:

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Запись текущего номера телефонов пользователей (LineUri), UserPrincipalName и связанных с ними данных, путем выполнения следующего локального Skype для бизнеса Server PowerShell для экспорта пользовательских данных:

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

4. Удаление сведений о атрибутах, связанных Skype для бизнеса Server из active Directory для набора пользователей, которые вы готовы обновить.  Существует 2 шага к этому процессу, как показано ниже.

   > [!Important] 
   > После следующего цикла AAD Sync после запуска этого шага пользователи с телефонная система, которые ранее были перемещены из локального Skype для бизнеса Server в облако, потеряют возможность выполнять и принимать вызовы до тех пор, пока шаг 8 не будет успешно завершен и подтвержден на шаге 9. Кроме того, убедитесь, что на шаге 2 сохранены номера телефонов и связанные сведения пользователя, так как эта информация необходима для этого шага.

 
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

5. Запустите следующий локальном модуле Active Directory для командлета Windows PowerShell, чтобы добавить значение SIP-адреса обратно в локальное прокси-серверы Active Directory. Это позволит предотвратить проблемы с интероперабельностью, которые зависят от этого атрибута. 

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

6. Запуск Azure AD Sync

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. Подождите, пока подготовка пользователей завершится. Вы можете отслеживать ход подготовка пользователей, запуская следующую команду Skype для бизнеса PowerShell. Следующая команда Skype для бизнеса PowerShell возвращает пустой результат по мере завершения процесса.

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. Выполните следующую команду Skype для бизнеса PowerShell, чтобы назначить номера телефонов и включить пользователей для телефонная система:
     
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
   >  Если у вас Skype для бизнеса конечные точки (Skype клиенты или 3-й телефон участника), вам также необходимо установить -HostedVoiceMail для $true. Если ваша организация использует только Teams конечные точки для пользователей с включенной голосовой поддержкой, этот параметр не применим к пользователям. 

9. Подтвердит правильность телефонная система пользователей с функциональными возможностями. Следующая команда Skype для бизнеса PowerShell возвращает пустой результат по мере завершения процесса.

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

    Локальное Skype для бизнеса Server powerShell:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    Skype для бизнеса Команда Online PowerShell:

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. После завершения всех действий в методе 2 см. в рубке Перемещение [](decommission-remove-on-prem.md) конечных точек гибридного приложения из локального в интернет и удаление локального Skype для бизнеса Server дополнительных действий по удалению Skype для бизнеса Server локального развертывания. [](decommission-move-on-prem-endpoints.md)


## <a name="see-also"></a>См. также

- [Консолидация облаков для Teams и Skype для бизнеса](cloud-consolidation.md)

- [Прекращение использования локальной среды Skype для бизнеса](decommission-on-prem-overview.md)

