---
title: Перемещение пользователей и конечных точек в облако
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Перемещение пользователей и конечных точек перед списанием локальной среды Skype для бизнеса.
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593912"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a>Перемещение необходимых пользователей и конечных точек перед списанием локальной среды

В этой статье описывается, как переместить необходимые пользователи и конечные точки приложений в облако Microsoft перед выводом из эксплуатации локальной среды Skype для бизнеса. Это шаг 1 из следующих действий по выводу из эксплуатации локальной среды:

- **Шаг 1. Перемещение всех необходимых пользователей и конечных точек приложения из локальной сети в интернет.** (В этой статье.)

- Шаг 2. [Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)

- Шаг 3. [Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a>Перемещение всех необходимых пользователей из локального в облако

Все пользователи, которые будут продолжать использовать после завершения миграции, сначала должны быть перемещены из локального в облако. Перемещение пользователей с помощью средств администрирования на месте. Подробные сведения см. в [материале Перемещение пользователей между локальной и облачной.](move-users-between-on-premises-and-cloud.md)

Несмотря на то, что пользователи с учетными записями Skype для бизнеса Server могут использовать Teams, эти пользователи не имеют полных функциональных возможностей Teams. Эти пользователи не могут скооперироваться или федератироваться с любым другим пользователем, все еще использующим Skype для бизнеса (будь то онлайн или локально). Эти пользователи также не могут принимать вызовы PSTN в клиенте Teams. Поэтому необходимо переместить этих пользователей в интернет. Этот шаг также обеспечивает перенос контактов или собраний, созданных в Skype для бизнеса Server, в Teams.

Чтобы проверить, есть ли в локальном развертывании оставшиеся пользователи, запустите следующий комдлет в окне Skype для бизнеса Server PowerShell.

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

Если какие-либо пользователи возвращаются, просмотрите вывод, чтобы определить, следует ли какие-либо учетные записи быть перемещены в облако, и для любых таких пользователей выполните действия [здесь](move-users-between-on-premises-and-cloud.md). Для учетных записей пользователей, которые больше не нужны, запустите следующий комдлет Skype для бизнеса Server PowerShell:

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> Запуск Disable-CsUser удаляет все атрибуты Skype для бизнеса для всех пользователей, которые соответствуют критериям фильтрации. Перед началом процедуры подтвердим, что эти учетные записи больше не нужны.

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a>Перемещение конечных точек гибридного приложения в Microsoft 365

1. Извлечение и экспорт параметров конечной точки гибридного приложения на локальном сервере путем выполнения следующей локальной команды Skype для Business Server PowerShell:

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. Создание и лицензирование новых [учетных записей](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) ресурсов в Microsoft 365 для замены существующих конечных точек гибридного приложения.

3. Связывать новые учетные записи ресурсов с существующими конечными точками гибридных приложений.

4. Удалите номера телефонов, определенные в конечных точках локального гибридного приложения, исполнив следующую команду Skype для бизнеса Server PowerShell:

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. Так как возможно, что номера телефонов для этих учетных записей управлялись в Microsoft 365 вместо локального, запустите следующую команду в Skype для бизнеса Online PowerShell:

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. Назначение номеров телефонов новым учетным записям ресурсов, созданным в шаге 2. Дополнительные сведения о назначении номера телефона учетной записи ресурса см. в следующей статье: [Назначение номера службы.](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)

7. Удалите конечные точки локального сервера, исполнив следующую команду Skype для бизнеса Server PowerShell:

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
Теперь вы готовы отключить [гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)

## <a name="see-also"></a>См. также

- [Вывод из эксплуатации локальной среды Skype для бизнеса](decommission-on-prem-overview.md)

- [Отключение гибридной конфигурации](cloud-consolidation-disabling-hybrid.md)

- [Удаление локального развертывания Skype для бизнеса](decommission-remove-on-prem.md)




