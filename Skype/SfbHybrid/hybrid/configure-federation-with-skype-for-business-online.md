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
description: Сводка. Сведения о настройке взаимодействия между локальной развертыванием и Skype для бизнеса Online.
ms.openlocfilehash: a97072c9c4b65b4cc13d29a733b8ddc840529363
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569221"
---
# <a name="configure-skype-for-business-hybrid"></a>Настройка гибридной среды Skype для бизнеса

Чтобы настроить гибридную среду Skype для бизнеса, необходимо выполнить следующие действия.

- [Настройка локальной службы Edge для федерации с помощью Microsoft 365 или Office 365.](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)
- Настройте локальное окружение, чтобы доверять [Microsoft 365 или Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)и включить общее пространство адресов SIP.
- [Включить общее пространство адресов SIP в организации Microsoft 365 или Office 365.](#enable-shared-sip-address-space-in-your-organization)

Обратите внимание, что если у вас есть локальное приложение Exchange, вам может потребоваться настроить OAuth между локальной средой Exchange и средой Skype для бизнеса Online. Дополнительные сведения см. в рублях Управление проверкой подлинности от сервера к серверу в [Skype для бизнес-сервера](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) и планирование интеграции [Skype для бизнеса и Exchange.](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support) 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>Настройка локальной службы Edge для федерации с помощью Microsoft 365 или Office 365

Федерация позволяет пользователям локального развертывания общаться с пользователями Microsoft 365 или Office 365 в вашей организации. Чтобы настроить федерацию, запустите следующий комдлет в оболочке управления skype для бизнес-серверов:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Если значение "EnablePartnerDiscovery" установлено $True, Skype для бизнеса Server будет использовать записи DNS для обнаружения доменов партнеров, не указанных в списке AllowedDomains. Если значение задается $False, Skype для бизнеса Server будет только федератом с доменами, найденными в списке AllowedDomains. Этот параметр необходим, если используется маршрутизация службы DNS.

> [!NOTE]
> Дополнительные сведения о включании федерации между пользователями локального развертывания Skype для бизнеса и пользователями организации Skype для бизнеса в Интернете см. в материале Настройка поддержки федерации для клиента Skype для бизнеса Online в [Skype для](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)бизнеса Server .


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>Настройка локальной среды, чтобы включить общее пространство адресов SIP с Microsoft 365 или Office 365

Кроме того, необходимо настроить локальное окружение, чтобы доверять Microsoft 365 или Office 365 и включить общее пространство адресов SIP. Это означает, что Microsoft 365 или Office 365 потенциально могут принимать учетные записи пользователей для того же набора доменов SIP, что и локальной среды, и сообщения могут отправляться между пользователями, которые будут отправляться в локальной и интерактивной среде.  Это необходимо, настроив поставщика хостинга на proxyFqdn=sipfed.online.lync.com, как описано ниже.

Сначала проверьте, есть ли у вас поставщик хостинга с ProxyFqdn=sipfed.online.lync.com. Если существует, удалите его с помощью следующей команды:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Затем создайте нового поставщика хостинга, используйте New-CsHostingProvider кодлета следующим образом: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Включить общее пространство адресов SIP в организации
  
Помимо изменений, которые были сделаны в локальном развертывании, необходимо внести соответствующие изменения в организации Microsoft 365 или Office 365 для включения общего пространства адресов SIP с локальной развертыванием.  

Чтобы включить общее пространство адресов SIP в организации, создайте удаленный сеанс PowerShell в Skype для бизнеса Online и запустите следующий раздел:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> Атрибут SharedSipAddressSpace должен оставаться "True", пока переход к сети не будет окончательным, и никакие пользователи не останутся на месте. 
  
Чтобы установить удаленный сеанс PowerShell в Teams или Skype для бизнеса Online, сначала необходимо установить [модуль Teams PowerShell.](https://docs.microsoft.com/microsoftteams/teams-powershell-install)
  
После установки модуля можно установить удаленный сеанс со следующими командлетами:
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

Дополнительные сведения о создании удаленного сеанса PowerShell в Skype для бизнеса Online и использовании модуля соединитель Skype для бизнеса в Интернете см. в Windows PowerShell [.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
  


## <a name="see-also"></a>См. также

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
