---
title: Перемещение конечных точек гибридного приложения в облако
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
description: Перед выводом из эксплуатации локальной среды Skype для бизнеса переместите конечную точку приложения.
ms.openlocfilehash: af8b521eaaf4a1e86027936f3d4d3600ab4bfa7b
ms.sourcegitcommit: 71d90f0a0056f7604109f64e9722c80cf0eda47d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/09/2021
ms.locfileid: "51656887"
---
# <a name="move-hyrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>Перемещение конечных точек приложения перед выводом из эксплуатации локальной среды

В этой статье описывается, как переместить необходимые конечные точки гибридного приложения в облако Microsoft перед выводом из эксплуатации локальной среды Skype для бизнеса. Это шаг 3 из следующих действий по выводу из эксплуатации локальной среды:

- Этап 1. [Перемещение всех необходимых пользователей из локальной сети в интернет](decommission-move-on-prem-users.md)

- Шаг 2. [Отключите гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)

- **Шаг 3. Перемещение конечных точек гибридного приложения из локального в online.** (В этой статье)

- Этап 4. [Удалите локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>Перемещение всех необходимых конечных точек гибридного приложения из локального в online

Прежде чем переместить эти конечные точки в интернет, необходимо убедиться, что вы обновили записи DNS, указав на Microsoft 365 для всех доменов SIP, используемых конечными точками. Невозможно создать учетные записи ресурсов в Интернете, если записи DNS указывают на локальное. Дополнительные сведения см. в [переключеть гибридную конфигурацию.](cloud-consolidation-disabling-hybrid.md)

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
Теперь вы готовы удалить локальное развертывание [Skype для бизнеса.](decommission-remove-on-prem.md)

## <a name="see-also"></a>См. также

- [Прекращение использования локальной среды Skype для бизнеса](decommission-on-prem-overview.md)

- [Перемещение всех необходимых пользователей из локальной сети в интернет](decommission-move-on-prem-users.md)

- [Отключение гибридной конфигурации](cloud-consolidation-disabling-hybrid.md)

- [Удаление локального развертывания Skype для бизнеса](decommission-remove-on-prem.md)




