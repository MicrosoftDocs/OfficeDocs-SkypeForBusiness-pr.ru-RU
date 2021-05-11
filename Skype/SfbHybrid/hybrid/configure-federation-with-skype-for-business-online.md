---
title: Настройка гибридной среды Skype для бизнеса
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
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
ms.custom: ''
description: Сводка. Сведения о настройке взаимодействия между локальной развертыванием и Teams.
ms.openlocfilehash: 2c6fda43b939a616071009be2b8d28e636036101
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305973"
---
# <a name="configure-skype-for-business-hybrid"></a>Настройка гибридной среды Skype для бизнеса

Чтобы настроить гибридную среду Skype для бизнеса, необходимо выполнить следующие действия.

- [Настройка локальной службы Edge для федерации с помощью Teams.](#configure-your-on-premises-edge-service-to-federate-with-teams)
- [Настройте локальное окружение,](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)чтобы доверять Teams и включить общее пространство адресов SIP.
- [Включить общее пространство адресов SIP](#enable-shared-sip-address-space-in-your-organization)в Teams организации.

Если у вас Exchange локальной среды, может потребоваться настроить OAuth между локальной Exchange и Skype для бизнеса среде Online. Дополнительные сведения см. в [веб-сведениях Управление](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) проверкой подлинности от сервера к серверу в Skype для бизнеса Server и планирование интеграции Skype для бизнеса [и Exchange.](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a>Настройка локальной службы Edge для федерации с помощью Teams

Федерация позволяет пользователям локального развертывания общаться с Teams и Skype для бизнеса пользователями в вашей организации. Чтобы настроить федерацию, запустите следующий cmdlet в Skype для бизнеса Server Management Shell:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Если значение '-EnablePartnerDiscovery' установлено $True, Skype для бизнеса Server записи DNS будут использовать для обнаружения доменов партнеров, не указанных в списке AllowedDomains. Если значение задается для $False, Skype для бизнеса Server только федерация с доменами, найденными в списке AllowedDomains. Этот параметр необходим, если используется маршрутизация службы DNS.

> [!NOTE]
> Дополнительные сведения о включании федерации между пользователями локального развертывания Skype для бизнеса и пользователями организации Microsoft 365 см. в материале [Configuring federation support for a Microsoft 365 клиента в Skype для бизнеса Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a>Настройка локальной среды, чтобы включить общее пространство адресов SIP с Teams

Кроме того, необходимо настроить локальное окружение, чтобы доверять Teams и включить общее пространство адресов SIP. Эта конфигурация Teams потенциально может принимать учетные записи пользователей для того же набора доменов SIP, что и локальной среды, а сообщения можно отправлять между пользователями, установленными в помещениях и в Интернете. Настройка поставщика хостинга с помощью ProxyFqdn=sipfed.online.lync.com, как описано ниже.

Сначала проверьте, есть ли у вас поставщик хостинга с ProxyFqdn=sipfed.online.lync.com. Если существует, удалите его с помощью следующей команды в командной Skype для бизнеса Server:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Затем создайте нового поставщика хостинга с помощью New-CsHostingProvider следующим образом: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Включить общее пространство адресов SIP в организации
  
Помимо изменений, которые были сделаны в локальном развертывании, необходимо внести соответствующие изменения в организацию Teams, чтобы включить общее адресное пространство SIP с локальной развертыванием.  

Чтобы включить общее пространство адресов SIP в организации, создайте удаленный сеанс PowerShell с Teams, а затем запустите следующий cmdlet:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> Атрибут SharedSipAddressSpace должен оставаться "True", пока переход к сети не будет окончательным, и никакие пользователи не останутся на месте. 
  
Чтобы установить удаленный сеанс PowerShell с Teams (или Skype для бизнеса Online), сначала необходимо установить модуль Teams [PowerShell.](/microsoftteams/teams-powershell-install) Модуль Teams PowerShell заменяет Skype соединитель Busines Online, который был снят.
  
После установки модуля можно установить удаленный сеанс со следующими командлетами:
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Дополнительные сведения о создании удаленного сеанса PowerShell с Teams и использовании модуля Teams PowerShell см. в этой ссылке Настройка компьютера для Windows PowerShell [.](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
  


## <a name="see-also"></a>См. также

[New-CsHostingProvider](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
