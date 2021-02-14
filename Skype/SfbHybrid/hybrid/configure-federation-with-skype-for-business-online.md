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
ms.openlocfilehash: 0df507fcc47157a9290018a199e1362cb203048b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221453"
---
# <a name="configure-skype-for-business-hybrid"></a>Настройка гибридной среды Skype для бизнеса

Чтобы настроить гибридную среду Skype для бизнеса, необходимо выполнить следующие действия.

- Настройка локальной службы Edge для федерации с [Microsoft 365 или Office 365.](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365)
- [Настройка локальной среды для доверия Microsoft 365 или Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365)и включить общее адресное пространство SIP.
- [Включить общее адресное пространство SIP в организации Microsoft 365 или Office 365.](#enable-shared-sip-address-space-in-your-organization)

Обратите внимание, что если у вас есть локальное приложение Exchange, может потребоваться настроить OAuth между локальной средой Exchange и средой Skype для бизнеса Online. Дополнительные сведения см. в управлении проверкой подлинности ["сервер-сервер"](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) в Skype для бизнеса Server и планировании интеграции Skype для бизнеса [и Exchange.](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support) 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a>Настройка локальной службы edge для федерации с Microsoft 365 или Office 365

Федерация позволяет пользователям в локальном развертывании взаимодействовать с пользователями Microsoft 365 или Office 365 в организации. Чтобы настроить федерацию, запустите следующий cmdlet в оболочке управления Skype для бизнеса Server:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Если для значения "-EnablePartnerDiscovery" установлено значение $True, Skype для бизнеса Server будет использовать записи DNS для обнаружения доменов партнеров, не указанных в списке AllowedDomains. Если задается значение $False, Skype для бизнеса Server будет федерации только с домены, найденные в списке AllowedDomains. Этот параметр необходим, если используется маршрутизация службы DNS.

> [!NOTE]
> Дополнительные сведения о включите федерацию между пользователями локального развертывания Skype для бизнеса и пользователями организации Skype для бизнеса Online, см. в настройках поддержки федерации для клиента Skype для бизнеса Online в [Skype для бизнеса Server.](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support)


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a>Настройка локальной среды для обеспечения общего адресного пространства SIP в Microsoft 365 или Office 365

Кроме того, необходимо настроить в локальной среде доверие к Microsoft 365 или Office 365 и включить общее адресное пространство SIP. Это означает, что Microsoft 365 или Office 365 потенциально могут использовать учетные записи пользователей для того же набора доменов SIP, что и в локальной среде, а сообщения могут маршрутиться между пользователями, которые были установлены в локальной и сетевой среде.  Это можно сделать, настроив поставщика услуг размещения с proxyFqdn=sipfed.online.lync.com, как описано ниже.

Сначала проверьте, есть ли у вас поставщик услуг размещения с ProxyFqdn=sipfed.online.lync.com. Если он существует, удалите его с помощью следующей команды:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Затем создайте нового поставщика услуг размещения, используйте New-CsHostingProvider следующим образом: 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a>Включить общее адресное пространство SIP в организации
  
Помимо изменений, сделанных в локальном развертывании, необходимо внести соответствующие изменения в организацию Microsoft 365 или Office 365, чтобы включить общее адресное пространство SIP в локальном развертывании.  

Чтобы включить общее адресное пространство SIP в организации, создайте удаленный сеанс PowerShell со Skype для бизнеса Online и запустите следующий cmdlet:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> Атрибут SharedSipAddressSpace должен оставаться "True", пока переход на веб-сайт не будет окончательным, и никакие пользователи не останутся в локальной сети. 
  
Чтобы установить удаленный сеанс PowerShell с Teams или Skype для бизнеса Online, сначала необходимо установить модуль соединителя Skype для бизнеса Online для Windows PowerShell, который можно [получить здесь.](https://go.microsoft.com/fwlink/p/?LinkId=391911)
  
После установки модуля можно установить удаленный сеанс со следующими командлетами:
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Дополнительные сведения о создании удаленного сеанса PowerShell со Skype для бизнеса Online и использовании модуля соединителю Skype для бизнеса Online см. в [Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
  


## <a name="see-also"></a>См. также

[New-CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
