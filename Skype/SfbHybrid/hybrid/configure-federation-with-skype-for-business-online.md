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
ms.openlocfilehash: 1b36a25674c3d6690b7490d0cd0793f05131cc12
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726789"
---
# <a name="configure-skype-for-business-hybrid"></a>Настройка гибридной среды Skype для бизнеса

Чтобы настроить гибридную среду Skype для бизнеса, необходимо выполнить следующие действия.

- [Настройте службу локальной среды для Федерации с Office 365](#configure-your-on-premises-edge-service-to-federate-with-office-365).
- [Настройте локальную среду для доверия к office 365 и включите общее адресное пространство SIP с помощью Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).
- [Включите общее адресное пространство SIP в клиенте Office 365](#enable-shared-sip-address-space-in-your-office-365-tenant).

Обратите внимание на то, что если у вас есть локальная служба Exchange, может потребоваться настроить OAuth между локальной средой Exchange и средой Skype для бизнеса Online. Дополнительные сведения можно найти [в статье Управление проверкой подлинности между серверами в Skype для бизнеса Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) и [Планирование интеграции Skype для бизнеса и Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a>Настройка локальной службы пограничной службы для Федерации с Office 365

Федерация позволяет пользователям в локальном развертывании взаимодействовать с пользователями Office 365 в вашей организации. Чтобы настроить федерацию, выполните следующий командлет в командной консоли Skype для бизнеса Server:
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

Если для параметра "-EnablePartnerDiscovery" задано значение 1, Skype для бизнеса Server будет использовать записи DNS для попытки обнаружения доменных доменов, не указанных в списке Алловеддомаинс. Если значение равно 0, Skype для бизнеса Server будет использовать только Федерацию с доменами, обнаруженными в списке Алловеддомаинс. Этот параметр необходим, если используется маршрутизация службы DNS.



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

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a>Включение общего адресного пространства SIP в клиенте Office 365
  
В дополнение к изменениям, внесенным в локальном развертывании, необходимо внести соответствующие изменения в клиенте Office 365, чтобы включить общее адресное пространство SIP с локальным развертыванием.  

Чтобы включить общее адресное пространство SIP в клиенте Office 365, установите удаленный сеанс PowerShell с помощью Skype для бизнеса Online, а затем выполните следующий командлет:
  
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

