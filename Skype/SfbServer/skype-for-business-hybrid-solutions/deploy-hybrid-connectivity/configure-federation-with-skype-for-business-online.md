---
title: Настройка федерации в Skype для бизнеса Online
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/12/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: a10bd1d5-c003-46db-9f57-7d55d3fa08da
description: 'Сводка: Узнайте, как настроить взаимодействие между локальным развертыванием и Скайп для бизнеса в Интернет.'
ms.openlocfilehash: 403cabdd808cd197ece2289564b14fea62a5c72a
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="configure-federation-with-skype-for-business-online"></a>Настройка федерации в Skype для бизнеса Online
 
**Сводка:** Узнайте, как настроить взаимодействие между локальным развертыванием и Скайп для бизнеса в Интернет.
  
Следуйте инструкциям в данном разделе по настройке взаимодействия между локальным развертыванием и Скайп для бизнеса в Интернет.
  
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
  
Для создания удаленного сеанса PowerShell с Скайп для бизнеса в Интернет, необходимо сначала установить Скайп для бизнеса в Интернет модуля соединитель для Windows PowerShell, который вы можете получить здесь: [https://go.microsoft.com/fwlink/p/?LinkId=391911](https://go.microsoft.com/fwlink/p/?LinkId=391911).
  
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

Дополнительные сведения о том, как установить удаленный сеанс PowerShell с Скайп для бизнеса в Интернет можно [подключение к Lync Online с помощью Windows PowerShell](http://technet.microsoft.com/library/6167dad9-9628-4fdb-bed1-bdb3f7108e64.aspx).
  
Дополнительные сведения об использовании Скайп для бизнеса в Интернет модуль PowerShell соединитель можно [С помощью Windows PowerShell для управления Lync Online](http://technet.microsoft.com/library/9ef2d853-10fb-4e02-a552-dcf6818d7153.aspx).
  
## <a name="see-also"></a>См. также

#### 

[Новый CsHostingProvider](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

