---
title: Перенос конечных точек гибридных приложений в облако
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: Миграция конечных точек приложения с гидравлией до вывода из эксплуатации Skype для бизнеса локальной среды.
ms.openlocfilehash: 74e0ef935c993f6e39b08759d3beb69e0c5c7673
ms.sourcegitcommit: d8dba15c520de3894d1781e17acb2c75fb38ed49
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2022
ms.locfileid: "62921857"
---
# <a name="migrate-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a>Перенос конечных точек гибридного приложения перед выводом из эксплуатации локальной среды

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

В этой статье описывается, как переместить необходимые конечные точки гибридных приложений в облако Майкрософт до вывода из эксплуатации локальной Skype для бизнеса среды. Это шаг 3 из следующих действий по выводу из эксплуатации локальной среды:

- Этап 1. [Перемещение всех необходимых пользователей из локальной сети в интернет](decommission-move-on-prem-users.md)

- Этап 2. [Отключите гибридную конфигурацию](cloud-consolidation-disabling-hybrid.md).

- **Шаг 3. Перенос конечных точек гибридного приложения из локального в онлайн.** (В этой статье)

- Этап 4. [Удалите локальное развертывание Skype для бизнеса развертывания](decommission-remove-on-prem.md).


## <a name="migrate-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a>Перенос всех необходимых конечных точек гибридного приложения из локального в интернет

Прежде чем переместить эти конечные точки в интернет, необходимо убедиться, что вы обновили записи DNS, чтобы указать на Microsoft 365 для всех доменов SIP, используемых конечными точками. Следует помнить, что после обновления DNS для указать на Microsoft 365, существующие конечные точки гибридных приложений больше не будут обнаруживаемыми, пока вы не выполните этот шаг. Так как этот шаг (создание учетных записей ресурсов в Интернете) невозможен, если записи DNS указывают на локальность, следует запланировать оба шага 2 и 3 в одном окне обслуживания. Дополнительные сведения см. в [переключеть гибридную конфигурацию](cloud-consolidation-disabling-hybrid.md).

1. Извлечение и экспорт параметров конечной точки гибридного приложения в локальном Skype для бизнеса Server PowerShell:

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. Создание и лицензирование новых [учетных](/microsoftteams/manage-resource-accounts) записей ресурсов в Microsoft 365 для замены существующих конечных точек гибридного приложения на локальном сайте.

3. Связывать новые учетные записи ресурсов с существующими конечными точками гибридных приложений.

4. Удалите номера телефонов, определенные в конечных точках локального гибридного приложения, исполнив следующую команду Skype для бизнеса Server PowerShell:

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. Так как возможно, что номера телефонов для этих учетных записей управлялись в Microsoft 365, а не локально, запустите следующую команду в Teams PowerShell:

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

6. Назначение номеров телефонов новым учетным записям ресурсов, созданным в шаге 2. Дополнительные сведения о назначении номера телефона учетной записи ресурса см. в следующей статье: [Назначение номера службы](/microsoftteams/manage-resource-accounts).

7. Удалите конечные точки на месте, исполнив следующую команду Skype для бизнеса Server PowerShell:

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
Теперь вы готовы удалить [локальное развертывание Skype для бизнеса.](decommission-remove-on-prem.md)

## <a name="see-also"></a>См. также

- [Прекращение использования локальной среды Skype для бизнеса](decommission-on-prem-overview.md)

- [Перемещение всех необходимых пользователей из локальной сети в интернет](decommission-move-on-prem-users.md)

- [Отключение гибридной конфигурации](cloud-consolidation-disabling-hybrid.md)

- [Удаление локального развертывания Skype для бизнеса](decommission-remove-on-prem.md)

- [Создание автопутепроводника с помощью cmdlets](/microsoftteams/create-a-phone-system-auto-attendant-via-cmdlets)




