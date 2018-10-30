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
ms.openlocfilehash: df5fed224484a3c8f8957365f5304095a115b7b1
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2018
ms.locfileid: "25839151"
---
# <a name="configure-skype-for-business-hybrid"></a>Настройка Скайп для гибридных бизнеса

Чтобы настроить Скайп для гибридных бизнеса, необходимо:

- [Настройка федерации](#configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online)
- [Настройте общее адресное пространство Session Initiation Protocol (SIP)](#configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space)
- [Настройка проверки подлинности сервер сервер, если необходимо](#configure-server-to-server-authentication-if-required)
  
## <a name="configure-your-on-premises-edge-service-for-federation-with-skype-for-business-online"></a>Для настройки локального пограничного сервера для федерации с Скайп для бизнеса в Интернет

Федерации пользователи в вашем развертывании локальных для взаимодействия с пользователями Office 365 в вашей организации. Для настройки федерации, выполните следующие командлеты в Скайп для консоли Business Server:
  
```
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

```
New-CSHostingProvider -Identity SkypeforBusinessOnline -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root
```

## <a name="configure-your-skype-for-business-online-tenant-for-a-shared-sip-address-space"></a>Настройка вашей Скайп для бизнеса в Интернет для клиентов для общее адресное пространство SIP

Адрес по протоколу SIP – это уникальный идентификатор каждого пользователя в сети, подобный номеру телефона или адресу электронной почты. Прежде чем переместить пользователей из локальной Скайп для бизнеса в Интернет, вам потребуются для настройки клиента Office 365 для совместного использования общих Session Initiation Protocol (SIP) адресное пространство с локальным развертыванием. Если оно не настроено, может отображаться следующее сообщение об ошибке.
  
Move-CsUser: Сбой регистр: Error=(510), описания = (клиент этого пользователя не включен для общего адресного пространства sip).
  
Чтобы настроить общее адресное пространство SIP, создания удаленного сеанса PowerShell с Скайп для бизнеса в Интернет и затем выполните следующий командлет:
  
```
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> Атрибут SharedSipAddressSpace должен иметь значение True вплоть до перемещения в сеть, а в локальной системе не должны остаться пользователи. 
  
Для создания удаленного сеанса PowerShell с Скайп для бизнеса в Интернет, необходимо сначала установить Скайп для бизнеса в Интернет модуля соединитель для Windows PowerShell, который вы можете получить [здесь](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
После установки модуля можно запустить удаленный сеанс с помощью следующих командлетов:
  
```
Import-Module SkypeOnlineConnector
```

```
$cred = Get-Credential
```

```
$CSSession = New-CsOnlineSession -Credential $cred
```

```
Import-PSSession $CSSession -AllowClobber
```

Дополнительные сведения о том, как установить удаленный сеанс PowerShell с Скайп для бизнеса в Интернет и использование Скайп в модуле Business Online Connector в разделе [Настройка компьютера для Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).
  
## <a name="configure-server-to-server-authentication-if-required"></a>Настройка проверки подлинности сервер сервер, если необходимо

В зависимости от типа гибридной среды, которые вы настраиваете может потребоваться настройка проверки подлинности сервер сервер.  Для получения дополнительных сведений см. [Проверка подлинности сервер сервер управление в Скайп для Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications).


## <a name="see-also"></a>См. также

[Новый CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

