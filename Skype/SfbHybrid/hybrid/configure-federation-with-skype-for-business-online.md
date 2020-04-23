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
description: Сводка. Узнайте, как настроить взаимодействие между локальным развертыванием и Skype для бизнеса Online.
ms.openlocfilehash: ccf140b62cdbad11605c99fe1cb0cc66aa1ee4dd
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780108"
---
# <a name="configure-skype-for-business-hybrid"></a>Настройка гибридной среды Skype для бизнеса

Чтобы настроить гибридную среду Skype для бизнеса, необходимо выполнить следующие действия.

- [Настройте локальную пограничной службу для Федерации с Office 365 или другой организацией](#configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization).
- [Настройте локальную среду для доверия к office 365 и включите общее адресное пространство SIP с помощью Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).
- [Включите общее адресное пространство SIP в организации Office 365](#enable-shared-sip-address-space-in-your-office-365-organization).

Обратите внимание на то, что если у вас есть локальная служба Exchange, может потребоваться настроить OAuth между локальной средой Exchange и средой Skype для бизнеса Online. Дополнительные сведения можно найти [в статье Управление проверкой подлинности между серверами в Skype для бизнеса Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) и [Планирование интеграции Skype для бизнеса и Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365-or-another-organization"></a>Настройка локальной службы пограничной службы для Федерации с Office 365 или другой организацией

Федерация позволяет пользователям в локальном развертывании общаться с Microsoft 365 или Office 365 для пользователей в вашей организации. Чтобы настроить федерацию, выполните следующий командлет в командной консоли Skype для бизнеса Server:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

Если параметру "-EnablePartnerDiscovery" присвоено значение $True, Skype для бизнеса Server будет использовать DNS-записи для попытки обнаружения доменных доменов, не указанных в списке Алловеддомаинс. Если параметру присвоено значение $False, Skype для бизнеса Server будет использовать только Федерацию с доменами, обнаруженными в списке Алловеддомаинс. Этот параметр необходим, если используется маршрутизация службы DNS.

> [!NOTE]
> Дополнительные сведения о включении Федерации между пользователями локального развертывания Skype для бизнеса и пользователей в Организации Skype для бизнеса Online приведены [в статье Настройка поддержки федерации для клиента Skype для бизнеса Online в Skype для бизнеса Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>Настройка локальной среды для включения общего адресного пространства SIP с Office 365

Вам также потребуется настроить локальную среду для доверия Office 365 и включить общее адресное пространство SIP с Office 365. Это означает, что в Office 365 потенциально могут размещаться учетные записи пользователей для того же набора доменов SIP, что и в локальной среде, а сообщения могут маршрутизироваться между пользователями, размещенными в локальной среде и в сети.  Для этого необходимо настроить поставщика услуг хостинга с ProxyFqdn = sipfed. Online. Lync. com, как описано ниже.

Сначала убедитесь, что у вас уже есть поставщик услуг хостинга с ProxyFqdn = sipfed. Online. Lync. com. Если он существует, удалите его с помощью следующей команды:

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Затем создайте нового поставщика услуг хостинга, используя командлет New – CsHostingProvider, как показано ниже. 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-organization"></a>Включение общего адресного пространства SIP в организации Office 365
  
В дополнение к изменениям, внесенным в локальном развертывании, необходимо внести соответствующие изменения в организации Office 365, чтобы она включала общее адресное пространство SIP с локальным развертыванием.  

Чтобы включить общее адресное пространство SIP в организации Office 365, установите удаленный сеанс PowerShell с помощью Skype для бизнеса Online, а затем выполните следующий командлет:
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> Атрибут SharedSipAddressSpace должен иметь значение true до тех пор, пока не будет выполнен переход в оперативный режим, и пользователи не будут сохраняться в локальной среде. 
  
Чтобы установить удаленный сеанс PowerShell с Teams или Skype для бизнеса Online, сначала необходимо установить модуль соединителя Skype для бизнеса Online для Windows PowerShell, который вы можете получить [здесь](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
После установки модуля можно установить удаленный сеанс со следующими командлетами:
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Дополнительные сведения о том, как установить удаленный сеанс PowerShell с помощью Skype для бизнеса Online, а также как использовать модуль соединителя Skype для бизнеса Online можно в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>См. также

[New — CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
