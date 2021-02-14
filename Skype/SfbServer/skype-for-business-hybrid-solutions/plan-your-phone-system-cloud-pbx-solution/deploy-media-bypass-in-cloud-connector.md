---
title: Развертывание обхода мультимедиа в Cloud Connector Edition
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
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 0ebba3a4-6124-434c-84aa-32b1cc3345bc
description: В этом разделе вы узнаете о действиях по развертыванию обхода мультимедиа в Cloud Connector Edition версии 2.0 и более поздних версий.
ms.openlocfilehash: eeb566e2a1a16e235813c077d4e4bf6903a467d7
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47359315"
---
# <a name="deploy-media-bypass-in-cloud-connector-edition"></a>Развертывание обхода мультимедиа в Cloud Connector Edition
 
> [!Important]
> Выпуск Cloud Connector Edition завершится 31 июля 2021 г. вместе со Skype для бизнеса Online. После обновления вашей организации до Teams узнайте, как подключить свою локальной телефонной сети к Teams с помощью [прямой маршрутизации.](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page)

В этом разделе вы узнаете о действиях по развертыванию обхода мультимедиа в Cloud Connector Edition версии 2.0 и более поздних версий. 
  
Обход мультимедиа позволяет клиенту отправлять мультимедиа напрямую на следующий прыжок PSTN (шлюз или пограничный контроллер сеансов) и исключить компонент Cloud Connector Edition из пути мультимедиа. См. также [планирование обхода мультимедиа в Cloud Connector Edition.](plan-for-media-bypass-in-cloud-connector-edition.md)
  
## <a name="enable-media-bypass"></a>Разрешить обход мультимедиа

Чтобы включить обход мультимедиа, необходимо настроить DNS-имя веб-службы обхода мультимедиа и включить обход мультимедиа в конфигурации клиента. Веб-служба обхода сервера-посредника автоматически развертывается на каждом сервере-посреднике. Администратор клиента должен выбрать имя для службы гибридной голосовой связи (сайта), и это имя должно быть из домена SIP, зарегистрированного для гибридной голосовой связи. Имя службы должно быть одинаковым для всех устройств Cloud Connector и всех сайтов STN независимо от расположения клиента. Веб-служба должна быть доступна только внутри сети.
  
Администратор клиента должен настроить запись A DNS во внутренней производственной службе Active Directory. Если у вас сложная многосайтовая среда, см. пример в примере: записи DNS для обхода веб-сайта-посредника [в сложных](deploy-media-bypass-in-cloud-connector.md#Example)многосайтовые среды. Запись DNS должна разрешаться только для внутренних сетевых клиентов; Она не должна разрешаться для внешних сетевых клиентов.
  
После настройки DNS подключите Skype для бизнеса Online с помощью удаленной powerShell с учетными данными администратора Skype для бизнеса. Дополнительные сведения [см.](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md) в этой Windows PowerShell.
  
В сеансе PowerShell введите следующие команды, чтобы включить обход мультимедиа:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
$mediabypass = New-CsNetworkMediaBypassConfiguration -AlwaysBypass $true -Enabled $true
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

Включение обхода мультимедиа — это двухшаговая процедура. Этот New-CsNetworkMedia не сразу сохраняет новую конфигурацию; Он создает только параметры в памяти. Объект, созданный этим cmdlet, должен быть сохранен в переменную, а затем назначен свойству MediaBypassSettings конфигурации сети. Дополнительные сведения см. в примере: записи DNS веб-сайта обхода мультимедиа [в сложных многосайтовые среды.](deploy-media-bypass-in-cloud-connector.md#Example)
  
Репликация между локальной и сетевой компонентами может занять до 24 часов, поэтому корпорация Майкрософт рекомендует выполнить необходимые команды перед включением пользователей.
  
## <a name="confirm-media-bypass-settings"></a>Подтверждение параметров обхода мультимедиа

Параметры обхода мультимедиа можно проверить следующим образом. 
  
Чтобы проверить репликацию через Интернет в пуле клиентов, в удаленной powerShell запустите следующую команду:
  
```powershell
Get-CsTenantHybridConfiguration -LocalStore
Get-CsNetworkConfiguration -LocalStore
```

Для проверки локальной репликации подключите серверы-посредники Cloud Connector, запустите следующую команду в PowerShell и убедитесь, что enabled=True и AlwaysBypass=True
  
```powershell
Get-CsNetworkConfiguration -LocalStore
```

Чтобы проверить параметры клиента, вы можете выйти из клиента Skype для бизнеса, войти обратно и подтвердить, что клиент получил URL-адрес службы следующим образом:
  
1. Откройте %appdatalocal%\Microsoft\Office\16.0\Lync\Tracing\Lync-UccApi-0.UccApilog. 
    
2. Найди hybridconfigserviceinternalurl и подтвердив, что URL-адрес совпадает с заданным вами.
    
## <a name="change-media-bypass-parameters"></a>Изменение параметров обхода мультимедиа

Администраторы клиента могут изменить DNS-имя веб-службы, выдав следующий cmdlet:
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl http://newname.domain/hybridconfig/hybridconfigservice.svc
```

> [!IMPORTANT]
> Клиенты должны выйти и войти, чтобы получить новое имя службы и распознать изменение. 
  
## <a name="temporarily-disable-media-bypass"></a>Временное отключение обхода мультимедиа

Этот сценарий может быть полезен для устранения неполадок или обслуживания. Чтобы отключить службу, запустите следующие cmdlets:
  
```powershell
$mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass
```

После внесения изменений может занять некоторое время, чтобы изменения реплицироваться на все cloud Connectors. Чтобы проверить состояние репликации, запустите следующий cmdlet в PowerShell на серверах-посредниках Cloud Connector: 
  
```powershell
Get- CsNetworkConfiguration -LocalStore
```

После репликации изменений веб-служба на сервере-посреднике начнет отклонить запросы клиентов для службы обхода сервера-посредника.
  
## <a name="disable-media-bypass-permanently"></a>Окончательное отключение обхода мультимедиа

Чтобы окончательно отключить обход мультимедиа, администратор клиента должен выполнить следующие команды: 
  
```powershell
Set-CsTenantHybridConfiguration -HybridConfigServiceInternalUrl  $null
    $mediabypass = New-CsNetworkMediaBypassConfiguration  -Enabled $false 
Set-CsNetworkConfiguration -MediaBypassSettings $mediabypass 
```

Администратору также потребуется удалить веб-адреса для обхода сервера-посредника с внутренних DNS-серверов. После внесения изменений может занять некоторое время, чтобы изменения реплицироваться на все устройства Cloud Connector. 
  
## <a name="example-media-bypass-web-site-dns-records-in-complex-multi-site-environments"></a>Пример: записи DNS для обхода веб-сайта-посредника в сложных многосайтовые среды
<a name="Example"> </a>

Клиенты получат веб-адрес веб-службы обхода сервера-посредника от внутреннего DNS-сервера. Имя веб-службы будет одинаковым на всех устройствах Cloud Connector и сайтах STN Cloud Connector. В сложной многосайтовой среде рекомендуется использовать политику DNS Windows 2016 для управления трафиком Geo-Location, чтобы клиенты могли перенаправляться на веб-службу, которая является локальной для их сети. 
  
Дополнительные сведения о политиках DNS Для Windows 2016 см. в Geo-Location управления трафиком на основе Geo-Location с [основными серверами.](https://docs.microsoft.com/windows-server/networking/dns/deploy/primary-geo-location)
  
Ниже приводится пример конфигурации для компании с несколькими сайтами, использующими политику DNS Windows 2016 для Geo-Location трафика.
  
Имя службы обхода — hybridvoice.adatum.biz.
  
На сайте в Амстердаме развернуты четыре устройства Cloud Connector со следующими IP-адресами сервера-посредника:
  
- 192.168.1.45
    
- 192.168.1.46
    
- 192.168.1.47
    
- 192.168.1.48
    
На сайте в Сиэтле развернуты три устройства Cloud Connector со следующими IP-адресами сервера-посредника:
  
- 10.10.1.8
    
- 10.10.1.9
    
- 10.10.1.10
    
Используя Geo-Location трафика, DNS-серверы будут настроены следующим образом:
  
1. Создайте клиентские подсети DNS для подсетей в Амстердаме и Сиэтле.
    
2. Создайте области зон DNS для adatum.biz в Амстердаме и Сиэтле.
    
3. Создайте записи DNS в каждой области зоны DNS.
    
    Амстердам
    
   - Введите A;
    
   - Name : hybridvoice in the adatum.biz DNS zone
    
   - Целевой объект: 192.168.1.45
    
     Создание дополнительных записей для дополнительных серверов-посредников
    
   - 192.168.1.46
    
   - 192.168.1.47
    
   - 192.168.1.48
    
     Сиэтл
    
   - Тип A
    
   - Name : hybridvoice in adatum.biz DNS zone
    
   - Целевой объект: 10.10.1.8
    
     Создание дополнительных записей для дополнительных серверов-посредников
    
   - 10.10.1.9
    
   - 10.10.1.10
    
4. Создайте политику DNS, которая подключает клиентские подсети к соответствующим зонам, чтобы обеспечить необходимое разрешение DNS.
    
На этом этапе клиенты, делая запросы DNS из подсети Амстердама для hybridvoice.adatum.biz, возвращают 192.168.1.45, Адреса 192.168.1.46, 192.168.1.47 и 192.168.1.48, а клиенты, делая ту же форму запроса Seattle, возвращают 10.10.1.8, 10.10.1.9 и 10.10.1.10.

> [!NOTE]
> Если устройство CCE не получает обновленные параметры, проверьте, может ли устройство связаться с клиентом с помощью удаленной powerShell. С помощью удаленной powerShell можно проверить состояние устройства с помощью Get-CsHybridPSTNAppliance или с помощью PowerShell на хост-сайте CCE проверить состояние с помощью Get-CcApplianceStatus.

  
## <a name="see-also"></a>См. также
<a name="Example"> </a>

[Планирование обхода сервера-посредника в Cloud Connector Edition](plan-for-media-bypass-in-cloud-connector-edition.md)
