---
title: Настройка Скайп для гибридных бизнеса
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Сводка: Узнайте, как настроить взаимодействие между локальным развертыванием и Скайп для бизнеса в Интернет.'
ms.openlocfilehash: db03636d412caa72a3b7a38d0c1d691c83d96a5b
ms.sourcegitcommit: 30620021ceba916a505437ab641a23393f55827a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/15/2018
ms.locfileid: "26532779"
---
# <a name="configure-skype-for-business-hybrid"></a>Настройка Скайп для гибридных бизнеса

Чтобы настроить Скайп для гибридных бизнеса, необходимо:

- [Настройка в локальной среде в федерацию с Office 365.](#configure-your-on-premises-edge-service-to-federate-with-Office-365)
- [Настройте в локальной среде для управления безопасностью Office 365 и включение общее адресное пространство SIP с помощью Office 365.](#configure-your-on-premises-environment-to-share-your-SIP-address-space-with-Office-365)
- [Включение общее адресное пространство SIP в клиент Office 365.](#configure-server-to-server-authentication-if-required)

> [!NOTE]
> Если у вас есть локальную систему Exchange, может потребоваться настройка OAuth между локальную систему Exchange и Скайп для бизнеса в Интернет сред. Для получения дополнительных сведений см. [Управление проверки подлинности сервер сервер в Скайп для Business Server](https://docs.microsoft.com/en-us/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) и [Планирование интеграции Скайп для бизнеса и Exchange](https://docs.microsoft.com/en-us/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support). 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a>Для настройки локального пограничного сервера в федерацию с Office 365

Федерации пользователи в вашем развертывании локальных для взаимодействия с пользователями Office 365 в вашей организации. Для настройки федерации, выполните следующий командлет в Скайп для консоли Business Server:
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a>Настройка в локальной среде для включения общее адресное пространство SIP с помощью Office 365

Также необходимо настроить среду для локальной для управления безопасностью Office 365 и включение общее адресное пространство SIP с помощью Office 365. Это означает, что Office 365 могут обращаться к учетных записей пользователей для тот же набор доменов SIP, как в локальной среде и сообщения могут быть маршрутизацией между пользователями, размещенного на локальном и online.  Это делается путем настройки поставщика услуг размещения с ProxyFqdn=sipfed.online.lync.com, как описано ниже.

Во-первых проверьте, если у вас уже есть поставщика услуг размещения с ProxyFqdn=sipfed.online.lync.com. Если он существует, затем удалите его с помощью следующей команды:

```
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

Затем создайте нового поставщика услуг размещения, используйте командлет New-CsHostingProvider следующим образом: 

```
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a>Включение общее адресное пространство SIP в клиент Office 365
  
Помимо изменения, внесенные в локальном развертывании вам потребуется внести соответствующие изменения в клиент Office 365 включено общее адресное пространство SIP с помощью локального развертывания.  

Чтобы включить общее адресное пространство SIP в клиент Office 365, создания удаленного сеанса PowerShell с Скайп для бизнеса в Интернет и затем выполните следующий командлет:
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> Атрибут SharedSipAddressSpace должен иметь значение True вплоть до перемещения в сеть, а в локальной системе не должны остаться пользователи. 
  
Для создания удаленного сеанса PowerShell с группами или Скайп для бизнеса в Интернет, необходимо сначала установить Скайп для бизнеса в Интернет модуля соединитель для Windows PowerShell, который вы можете получить [здесь](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
После установки модуля можно запустить удаленный сеанс с помощью следующих командлетов:
  
```
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

Дополнительные сведения о том, как установить удаленный сеанс PowerShell с Скайп для бизнеса в Интернет и использование Скайп в модуле Business Online Connector в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  


## <a name="see-also"></a>См. также

[Новый CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

