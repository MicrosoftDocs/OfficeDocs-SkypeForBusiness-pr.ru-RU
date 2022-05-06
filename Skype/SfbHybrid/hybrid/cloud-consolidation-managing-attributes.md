---
title: Выберите, как управлять атрибутами после списания
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
ms.localizationpriority: medium
description: В этой статье описывается, как управлять атрибутами после списания локальной среды.
ms.openlocfilehash: b838b965430a007fa74320d7dbebdcf7ee36c3a9
ms.sourcegitcommit: 140c34f20f9cd48d7180ff03fddd60f5d1d3459f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2022
ms.locfileid: "65249021"
---
# <a name="decide-how-to-manage-attributes-after-decommissioning"></a>Выберите, как управлять атрибутами после списания

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


По умолчанию все пользователи, которые были включены для Skype для бизнеса Server а затем перемещены в облако, по-прежнему имеют атрибуты msRTCSIP, настроенные в локальная служба Active Directory. 

Эти атрибуты, в частности SIP-адрес (msRTCSIP-PrimaryUserAddress) и номер телефона (msRTCSIP-Line), продолжают синхронизироваться с Azure AD. Если требуются изменения в любом из атрибутов msRTCSIP, эти изменения необходимо внести в локальная служба Active Directory, а затем синхронизировать с Azure AD. Однако после Skype для бизнеса Server развертывания средства Skype для бизнеса Server будут недоступны для управления этими атрибутами.

Существует два варианта обработки этой ситуации:

1. Оставьте пользователей, для которых Skype для бизнеса учетных записей сервера, и управляйте атрибутами msRTCSIP с помощью средств Active Directory. Этот метод гарантирует отсутствие потери службы для перенесенных пользователей и позволяет удалить развертывание Skype для бизнеса Server путем удаления (например, очистки) серверов без полного вывода из эксплуатации. Однако новые лицензированные пользователи не будут заполнять эти атрибуты в вашем локальная служба Active Directory и должны будут управляться в Интернете.

2.  Удалите все атрибуты msRTCSIP от перенесенных пользователей в локальная служба Active Directory и управляйте этими атрибутами с помощью сетевых средств. Этот метод обеспечивает согласованный подход к управлению для существующих и новых пользователей. Однако это может привести к временной потере службы во время локального процесса вывода из эксплуатации.


## <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a>Метод 1. Управление SIP-адресами и номерами телефонов для пользователей в Active Directory

Администраторы могут управлять пользователями, которые были перемещены из локальной среды Skype для бизнеса Server в облако, даже после списания локального развертывания. 

Если вы хотите внести изменения в SIP-адрес пользователя или номер телефона пользователя (а sIP-адрес или номер телефона уже имеет значение в локальная служба Active Directory), необходимо внести изменения в локальная служба Active Directory и разрешить потоку значений до Azure AD. Этот метод не требует локального Skype для бизнеса Server. Вместо этого эти атрибуты можно изменить непосредственно в локальная служба Active Directory с помощью оснастки MMC Пользователи и компьютеры Active Directory (как показано ниже) или с помощью PowerShell. Если вы используете оснастку MMC, откройте страницу свойств пользователя, щелкните вкладку "Редактор атрибутов" и найдите соответствующие атрибуты для изменения:

- Чтобы изменить SIP-адрес пользователя, измените .`msRTCSIP-PrimaryUserAddress`

    > [!NOTE]
    > Если атрибут `ProxyAddresses` содержит SIP-адрес, также обновите это значение в качестве рекомендации. Несмотря на то, что адрес SIP-адреса `ProxyAddresses` игнорируется o365 `msRTCSIP-PrimaryUserAddress` , если он заполнен, он может использоваться другими локальными компонентами.

- Чтобы изменить номер телефона пользователя, измените его, `msRTCSIP-Line` если *он уже имеет значение*.

  ![Средство для пользователей и компьютеров Active Directory.](../media/disable-hybrid-1.png)


- `msRTCSIP-Line` Если у пользователя изначально не было значения для локальной среды до перемещения, `-PhoneNumber` можно изменить номер телефона с помощью параметра [командлета Set-CsPhoneNumberAssignment](/powershell/module/teams/set-csphonenumberassignment) в модуле Teams PowerShell.

Эти действия не являются необходимыми для новых пользователей, созданных после отключения гибридной среды, и этими пользователями можно управлять непосредственно в облаке. Если вам удобно использовать сочетание этих методов и оставить атрибуты msRTCSIP на месте в локальная служба Active Directory, можно повторно создать образ локальных Skype для бизнеса серверов. Однако если вы предпочитаете очистить все атрибуты msRTCSIP и выполнить традиционное удаление Skype для бизнеса Server, используйте метод 2.


## <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a>Метод 2. Очистка Skype для бизнеса атрибутов для всех локальных пользователей в Active Directory

Этот вариант требует больше усилий и надлежащего планирования, так как пользователи, перемещенные из локальной среды Skype для бизнеса Server в облако, должны быть повторно подготовлены. Этих пользователей можно классифицировать по двум разным категориям: пользователи без телефонная система и пользователи с телефонная система. Пользователи с телефонная система временную потерю телефонной службы при переносе номера телефона из управляемого локальная служба Active Directory в облако. **Перед началом массовых операций рекомендуется выполнить пилотный проект с небольшим числом телефонная система пользователей.** Для крупных развертываний пользователи могут обрабатываться в небольших группах в разных временных окнах. 

> [!NOTE] 
> Этот процесс проще всего для пользователей с соответствующим SIP-адресом и UserPrincipalName. Для организаций, в которых пользователи со значениями, не соответствующими этим двум атрибутам, должны быть внимательны, как указано ниже, для плавного перехода.

> [!NOTE]
> Если вы настроите конечные точки локального гибридного приложения для автосекретарей или очередей вызовов, не забудьте переместить эти конечные точки в Microsoft 365 перед выводом из эксплуатации Skype для бизнеса Server. Дополнительные сведения см. в разделе "Миграция конечных точек гибридных приложений" перед выводом [локальной среды из эксплуатации](decommission-move-on-prem-endpoints.md).  


1. Убедитесь, что следующий локальный Skype для бизнеса командлет PowerShell возвращает пустой результат. Пустой результат означает, что пользователи не размещены в локальной среде и либо были перемещены в Microsoft 365 либо отключены:

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. Запишите текущий номер телефона пользователя (LineUri), UserPrincipalName и связанные сведения, выполнив следующий локальный командлет Skype для бизнеса Server PowerShell для экспорта данных пользователя:

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > Прежде чем продолжить SfbUserSettings.csv файл и убедитесь, что все пользовательские данные успешно экспортированы. Рекомендуется сохранить копию этого файла.  Не используйте этот файл на следующих шагах для обработки пользователей. 

3. Создайте файл с группой пользователей, которая будет использоваться на следующих шагах. После успешного завершения работы первой группы пользователей перейдите к следующей группе пользователей. В приведенном ниже примере группы пользователей выбираются в алфавитном порядке. Вы можете фильтровать пользователей по критериям, которые соответствуют способу обработки пользователей.

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > Прежде чем продолжить SfbUsers.csv файл и убедиться, что данные пользователя успешно экспортированы. На следующем шаге вам потребуются LineUri (номер телефона), UserPrincipalName, SamAccountName и SipAddress из этого файла.

4. Удалите сведения об атрибутах, Skype для бизнеса Server из Active Directory для набора пользователей, которые вы готовы обновить.  Этот процесс выполняется в два этапа, как показано ниже.

   > [!Important] 
   > После следующего AAD Sync после выполнения этого шага пользователи с телефонная система, которые были перемещены из локального Skype для бизнеса Server в облако, потеряют возможность совершать и принимать звонки до тех пор, пока шаг 8 не будет успешно завершен и подтвержден на шаге 9. Кроме того, убедитесь, что на шаге 2 сохранены номера телефонов и связанные сведения пользователя, так как эти сведения необходимы для этого шага.

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   Затем для того же набора пользователей очистите значение msRTCSIP-DeploymentLocator с помощью локальная служба Active Directory PowerShell:

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. Чтобы добавить значение адреса SIP обратно в локальная служба Active Directory proxyAddresses, выполните следующий локальная служба Active Directory для Windows PowerShell командлета. Это действие предотвратит проблемы взаимодействия, которые зависят от этого атрибута. 

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

7. Дождитесь завершения подготовки пользователей. Ход подготовки пользователей можно отслеживать, выполнив следующую команду Teams PowerShell. Приведенная ниже Teams PowerShell возвращает пустой результат по завершении процесса.

   ```PowerShell
   Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | Where UserValidationErrors -ne $null | Select SipAddress,InterpretedUserType,UserValidationErrors
   ```

8. Чтобы назначить номера телефонов и разрешить пользователям телефонная система, выполните следующую Teams PowerShell:


   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
             Set-CsPhoneNumberAssignment -Identity $user.SipAddress -PhoneNumber $user.LineUri.Replace("tel:","") -PhoneNumberType DirectRouting
        }
   }
   ```

   > [!Note]
   >  Если у вас по-прежнему Skype для бизнеса конечных точек (Skype клиентов или сторонних телефонов), необходимо также задать для -HostedVoiceMail значение $true. Если ваша организация использует только Teams конечных точек для пользователей с поддержкой голосовой связи, этот параметр неприменим к пользователям. 

9. Убедитесь, что телефонная система были правильно подготовлены функциональные возможности. Приведенная ниже Teams PowerShell возвращает пустой результат по завершении процесса.

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled
                }
        }
   }
   ``` 

10. Повторите шаги 3–9, пока не будут обработаны все пользователи.

11. Убедитесь, что все пользователи успешно обработаны, выполнив следующие две команды PowerShell.

    Локальная Skype для бизнеса Server в локальной среде PowerShell:

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 

    Teams PowerShell:

    ```PowerShell
    Get-CsOnlineUser -Filter {IsSipEnabled -eq $True} | where {UserValidationErrors -ne $null} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, UserValidationErrors
    ``` 

12. После выполнения всех действий в методе 2 см. раздел [](decommission-move-on-prem-endpoints.md) "Перемещение конечных точек гибридных приложений из локальной среды в [](decommission-remove-on-prem.md) сеть" и "Удаление локального Skype для бизнеса Server дополнительных действий по удалению локального развертывания Skype для бизнеса Server приложения".


## <a name="see-also"></a>См. также

- [Консолидация облака для Teams и Skype для бизнеса](cloud-consolidation.md)

- [Прекращение использования локальной среды Skype для бизнеса](decommission-on-prem-overview.md)

