---
title: Развертывание обхода мультимедиа в cloud Connector Edition
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 11/15/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: Ознакомьтесь с этой темой, чтобы узнать о шагах по развертыванию обхода мультимедиа в версии 2.0 и более поздней версии Cloud Connector Edition.
ms.openlocfilehash: edc00467d878f0f2ae137c86f179f864bb2ca53f
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/26/2021
ms.locfileid: "58613779"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Развертывание обхода мультимедиа в cloud Connector Edition
 
> [!Important]
> Cloud Connector Edition завершится 31 июля 2021 г. вместе с Skype для бизнеса Online. После обновления организации Teams, узнайте, как подключить локальной телефонной сети к Teams с помощью прямой [маршрутизации](/MicrosoftTeams/direct-routing-landing-page).

Ознакомьтесь с этой темой, чтобы узнать о шагах по развертыванию обхода мультимедиа в версии 2.0 и более поздней версии Cloud Connector Edition. 
  
Обход мультимедиа позволяет клиенту отправлять средства массовой информации непосредственно в общественную телефонную сеть (PSTN) в следующем переходе — шлюзе или пограничном контроллере сеанса (SBC) и исключить компонент Cloud Connector Edition из пути мультимедиа. См. также [План обхода мультимедиа в Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md).
  
## <a name="enable-media-bypass"></a>Разрешить обход мультимедиа

Чтобы включить обход мультимедиа, необходимо настроить имя DNS веб-службы обхода мультимедиа и включить обход мультимедиа в конфигурации клиента. Веб-служба обхода мультимедиа автоматически развертывается на каждом сервере-посреднике. Администратор клиента должен выбрать имя гибридной голосовой службы (сайта), и это имя должно быть из домена SIP, зарегистрированного для гибридного голоса. Имя службы должно быть одинаковым для всех устройств Cloud Connector и всех сайтов PSTN независимо от расположения клиента. Веб-служба должна быть доступна только внутри сети.
  
Администратор клиента должен настроить запись DNS A во внутреннем производстве Active Directory. Если у вас сложная многосайтовая среда, см. пример в примере: записи DNS-записей веб-сайта обхода мультимедиа в сложных [многосайтных средах.](deploy-media-bypass-in-cloud-connector.md#Example) Запись DNS должна разрешаться только для внутренних сетевых клиентов; она не должна разрешаться для внешних сетевых клиентов.
  
После настройки DNS подключите Skype для бизнеса Online с помощью удаленной powerShell с Skype для бизнеса администратора. Дополнительные сведения см. [в дополнительных сведениях о настройках](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) компьютера для Windows PowerShell.
  
В сеансе PowerShell введите следующие команды, чтобы включить обход мультимедиа:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Включение обхода мультимедиа — это двухшаговая процедура. В New-CsNetworkMedia не сразу сохраняется новая конфигурация; он создает только параметры в памяти. Объект, созданный этим комлетом, должен быть сохранен в переменной, а затем назначен свойству MediaBypassSettings конфигурации сети. Дополнительные сведения см. в примере: записи DNS-записей об обходе веб-сайта в сложных [многосайтных средах.](deploy-media-bypass-in-cloud-connector.md#Example)
  
Репликация между локальной и сетевой компонентами может занять до 24 часов, поэтому Корпорация Майкрософт рекомендует выполнить необходимые команды перед включением пользователей.
  
## <a name="confirm-media-bypass-settings"></a>Подтверждение параметров обхода мультимедиа

Параметры обхода мультимедиа можно проверить следующим образом. 
  
Чтобы проверить репликацию в интернете в пуле клиентов, запустите следующую команду в удаленной PowerShell:
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Чтобы проверить репликацию локального устройства, подключись к серверам-посредникам облачных соединителок, запустите следующую команду в PowerShell и убедитесь, что Enabled=True и AlwaysBypass=True
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Чтобы проверить параметры клиента, выпишитесь из Skype для бизнеса, впишитесь и убедитесь, что клиент получил URL-адрес службы следующим образом:
  
1. Откройте %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Поиск гибридного веб-адреса hybridconfigserviceinternalurl и подтверждение того URL-адреса, который вы определили.
    
## <a name="change-media-bypass-parameters"></a>Изменение параметров обхода мультимедиа

Администраторы клиентов могут изменить имя DNS веб-службы, заняв следующие cmdlet:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Клиенты должны зарегистрироваться и войти, чтобы получить новое имя службы и распознать изменение. 
  
## <a name="temporarily-disable-media-bypass"></a>Временное отключение обхода мультимедиа

Этот сценарий может быть полезен для устранения неполадок или обслуживания. Чтобы отключить службу, запустите следующие cmdlets:
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

После внесения изменений может занять некоторое время для репликации изменений во все соединители облака. Чтобы проверить состояние репликации, запустите следующий cmdlet в PowerShell на серверах-посредниках облачного соединителя: 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

После репликации изменений веб-служба на сервере-посреднике начнет отклонить клиентские запросы на службу обхода мультимедиа.
  
## <a name="disable-media-bypass-permanently"></a>Отключение обхода мультимедиа на постоянной основе

Чтобы окончательно отключить обход мультимедиа, администратору клиента необходимо выполнить следующие команды: 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Администратору также потребуется удалить веб-адреса для обхода мультимедиа с внутренних DNS-серверов. После внесения изменений может занять некоторое время для репликации всех устройств Cloud Connector. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Пример: записи DNS веб-сайта обхода мультимедиа в сложных многосайтных средах
<a name="Example"> </a>

Клиенты получат веб-адрес веб-службы обхода мультимедиа с внутреннего DNS-сервера. Имя веб-службы будет одинаковым во всех устройствах cloud Connector и сайтах PSTN облачного соединитетеля. В сложной среде с несколькими сайтами рекомендуется использовать политику DNS 2016 Windows 2016 для управления трафиком на основе Geo-Location, чтобы клиенты могли быть перенаправлены на локализованную для их сети веб-службу. 
  
Дополнительные сведения о политике DNS 2016 Windows 2016 г. см. в Geo-Location DNS Policy for Geo-Location управления трафиком [с первичными серверами.](/windows-server/networking/dns/deploy/primary-geo-location)
  
Ниже приводится пример конфигурации для компании с несколькими сайтами с Windows политики DNS 2016 Geo-Location управления трафиком.
  
Имя службы обхода — "hybridvoice.adatum.biz".
  
На сайте в Амстердаме развернуты четыре устройства cloud Connector со следующими IP-адресами сервера-посредника:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
На сайте в Сиэтле развернуты три устройства cloud Connector со следующими IP-адресами сервера-посредника:
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
С Geo-Location управления трафиком DNS-серверы будут настроены следующим образом:
  
1. Создание клиентских подсетей DNS для подсетей Амстердама и Сиэтла.
    
2. Создание областей зоны DNS для adatum.biz для Амстердама и Сиэтла.
    
3. Создание записей DNS в каждой области зоны DNS.
    
    Амстердам
    
   - Тип A;
    
   - Имя: hybridvoice в adatum.biz DNS
    
   - Целевой показатель: 192.168.1.45
    
     Создание дополнительных записей для дополнительных серверов-посредников
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Сиэтл
    
   - Тип A
    
   - Имя: hybridvoice в adatum.biz DNS-зоне
    
   - Целевой показатель: 10.10.1.8
    
     Создание дополнительных записей для дополнительных серверов-посредников
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Создайте политику DNS, которая соединяет клиентские подсети с соответствующими зонами, чтобы обеспечить нужное разрешение DNS.
    
На данный момент клиенты, делая запросы DNS из подсети Амстердама для hybridvoice.adatum.biz, возвращают 192.168.1.45, 192.168.1.46, 192.168.1.47 и 192.168.1.48 адреса, в то время как клиенты, делая ту же форму запроса, будут возвращать 10.10.1.8, 10.10.1.9 и 10.10.1.10.

> [!NOTE]
> Если устройство CCE не получает обновленные параметры, проверьте, может ли устройство связаться с клиентом с помощью удаленной powerShell. С помощью remote PowerShell можно проверить состояние устройства с помощью Get-CsHybridPSTNAppliance или использовать PowerShell на хосте CCE для проверки состояния с помощью Get-CcApplianceStatus.

  
## <a name="see-also"></a>См. также
<a name="Example"> </a>

[Планирование обхода сервера-посредника в Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)