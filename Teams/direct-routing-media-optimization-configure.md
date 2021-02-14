---
title: Direct Routing Local Media Optimization
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Настройка оптимизации локальных мультимедиа для прямой маршрутизации
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576991"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>Настройка оптимизации локальных мультимедиа для прямой маршрутизации

Конфигурация для оптимизации локальных мультимедиа основана на параметрах сети, общих с другими облачными функциями голосовой связи, такими как маршрутизация Location-Based динамические экстренные вызовы. Дополнительные информацию о сетевых регионах, сетевых сайтах, подсетях и доверенных IP-адресах см. в параметрах сети для [функций облачной голосовой связи.](cloud-voice-network-settings.md)

Перед настройкой оптимизации локальных мультимедиа см. local [media Optimization для Direct Routing.](direct-routing-media-optimization.md)  

Чтобы настроить оптимизацию локальных мультимедиа, необходимо сделать следующее: Вы можете использовать Центр администрирования Teams или PowerShell. Подробные сведения см. [в топологии "Управление сетью".](manage-your-network-topology.md)

1. Настройте пользователя и сайты SBC (как описано в этой статье).
2. Настройте SBCs для оптимизации локальных мультимедиа (в зависимости от спецификации поставщика SBC).

На следующей схеме показана конфигурация сети, используемая в примерах этой статьи.

![Схема, на которой показаны примеры настройки сети](media/direct-routing-media-op-9.png "Примеры настройки сети")


## <a name="configure-the-user-and-the-sbc-sites"></a>Настройка пользователя и сайтов SBC

Чтобы настроить пользователя и сайты SBC, необходимо:

1. [Управление внешними надежными IP-адресами.](#manage-external-trusted-ip-addresses)  

2. [Определите топологию сети,](#define-the-network-topology) настроив сетевые регионы, сетевые сайты и подсети.

3. [Определите топологию](#define-the-virtual-network-topology) виртуальной сети, назначив SBC-серверы сайтам с соответствующими режимами и значениями SBC прокси-сервера.


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>Настройка SBC для локальной оптимизации мультимедиа в соответствии со спецификацией поставщика SBC

В этой статье описана конфигурация компонентов Майкрософт. Сведения о настройке SBC см. в документации к поставщику SBC.

Оптимизацию локальных мультимедиа поддерживают следующие поставщики SBC:

| Поставщик | ПРОИЗВЕД |    Версия программного обеспечения |
|:------------|:-------|:-------|
| [Audiocodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7.20A.256 | 
|            |  Mediant 800 SBC |   7.20A.256 | 
|            |  Mediant 2600 SBC |  7.20A.256 | 
|            |  Mediant 4000 SBC |  7.20A.256 | 
|            |  Mediant 1000B SBC | 7.20A.256 | 
|            |  Mediant 9000 SBC |  7.20A.256 | 
|            |  Mediant Virtual Edition SBC |   7.20A.256 | 
|            |  Mediant Cloud Edition SBC | 7.20A.256 |
| [Основные функции SBC на ленте](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [Лента SBC Edge](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 |
|               | SBC 1000 | 8.1.5  |
|               | SBC 2000 | 8.1.5  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1 и более |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |


## <a name="manage-external-trusted-ip-addresses"></a>Управление внешними надежными IP-адресами

Внешние доверенные IP являются внешними IP-пользователями корпоративной сети. Это IP-адреса, используемые клиентами Microsoft Teams при подключении к Microsoft 365. Эти внешние IPS необходимо добавить для каждого сайта, на котором есть пользователи с локальной оптимизацией мультимедиа.

Чтобы добавить общедоступные IP-адреса для каждого сайта, используйте New-CsTenantTrustedIPAddress управления. Для клиента можно определить неограниченное количество доверенных IP-адресов. Если внешними IP-адресами, которые видны Microsoft 365, являются IPv4- и IPv6-адреса, необходимо добавить оба типа IP-адресов. Для IPv4 используйте маску 32. Для IPv6 используйте маску 128. Вы можете добавить как отдельные внешние IP-адреса, так и внешние IP-подсети, указав в этом окне различные маскикбиты.

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


Пример добавления доверенных IP-адресов.

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a>Определение топологии сети

В этом разделе описано, как определить сетевые регионы, сетевые сайты и подсети для топологии сети.

Все параметры должны чувствительны к делу, поэтому необходимо убедиться, что используется тот же случай, который использовался при настройке.  (Например, значения GatewaySiteID "Вьетнам" и "Вьетнам" будут рассматриваться как разные сайты.)

### <a name="define-network-regions"></a>Определение сетевых регионов

Чтобы определить сетевые регионы, используйте New-CsTenantNetworkRegion. Параметр RegionID — это логическое имя, которое представляет географическое положение региона и не имеет зависимостей и ограничений. Параметр CentralSite <site ID> необязателен.

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

В следующем примере создается сетевой регион с названием APAC:

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>Определение сетевых сайтов

Чтобы определить сетевые сайты, используйте New-CsTenantNetworkSite управления. Каждый сетевой сайт должен быть связан с сетевым регионом.

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

В следующем примере создаются три новых сетевых сайта: Вьетнам, Индонезия и Сингапур в регионе APAC:

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>Определение сетевых подсетей

Чтобы определить сетевые подсети и связать их с сетевыми сайтами, воспользуйтесь New-CsTenantNetworkSubnet-данными. Каждую сетевую подсеть можно связывать только с одним сайтом. 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

В следующем примере определяются три подсети сети и они связывается с тремя сетевыми сайтами: Вьетнам, Индонезия и Сингапур:

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>Определение топологии виртуальной сети 

Во-первых, администратор клиента создает новую конфигурацию SBC для каждого соответствующего SBC с помощью New-CsOnlinePSTNGateway управления.
Администратор клиента определяет топологию виртуальной сети, определяя сетевые сайты для объектов шлюза STN с помощью Set-CsOnlinePSTNGateway управления:

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

Обратите внимание на следующее: 
   - Если у клиента один SBC, параметр -ProxySBC должен быть обязательным $null или FQDN SBC (Центральный SBC с сценариями централизованной связи).
   - Параметр -MediaBypass должен иметь $true для поддержки локальной оптимизации мультимедиа.
   - Если у SBC нет параметра -BypassMode, то X-MS-загона не будут отправлены. 
   - Все параметры должны чувствительны к делу, поэтому необходимо убедиться, что используется тот же случай, который использовался при настройке.  (Например, значения GatewaySiteID "Вьетнам" и "Вьетнам" будут рассматриваться как разные сайты.)

В следующем примере к сетевым сайтам Вьетнама, Индонезии и Сингапура в регионе APAC добавляются три SBCs в режиме "Всегда обходить":

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

Примечание. Чтобы обеспечить непрерывные операции при одновременной настройке локальной оптимизации мультимедиа и маршрутизации Location-Based (LBR), для LBR необходимо включить пустую систему SBCs для LBR, задав параметр GatewaySiteLbrEnabled для $true для каждого нитерного SBC. (Этот параметр не является обязательным для прокси-сервера SBC.)

На основе вышеприведенной информации direct Routing включает три фирменных заглавных для SIP приглашения и повторного приглашения, как показано в таблице ниже.

X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:

| Header name | Значения | Комментарии | 
|:------------|:-------|:-------|
| X-MS-UserLocation | внутреннее/внешнее | Указывает, внутренний или внешний пользователь |
| SIP-URI ПРИГЛАШЕНИЯ: +84439263000@VNsbc.contoso.com SIP /2.0 | SBC FQDN | FQDN, целевое для звонка, даже если SBC не подключен напрямую к Direct Routing |
| X-MS-MediaPath | Пример: proxysbc.contoso.com, VNsbc.contoso.com | Порядок SBCs, которые должны использоваться для пути мультимедиа между пользователем и целевой SBC. Окончательный SBC всегда последний |
| X-MS-UserSite | usersiteID | Строка, определяемая администратором клиента |

## <a name="call-flows"></a>Потоки вызовов 

Ниже показаны потоки вызовов для двух режимов:

- [Всегда обходить](#always-bypass-mode)
- [Только для локальных пользователей](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>Режим "Всегда обходить"

Режим "Всегда обходить" проще всего настроить. Администратор клиента может настроить один сайт для всех пользователей и веб-сайтов, если с любого сайта можно получить доступ к всем SBCs.

В примерах приводится обойдение режима "Всегда" в следующих сценариях:

- [Исходящие звонки, и пользователь находится в том же расположении, что и SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Входящие звонки и пользователь находится в том же расположении, что и SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Исходящие звонки, и пользователь является внешним](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [Входящие звонки, и пользователь является внешним](#inbound-calls-and-the-user-is-external-with-always-bypass)

В следующей таблице показаны FQDN и IP-адреса, используемые в примерах:

| Полное доменное имя | Внешний IP-адрес SBC | Внутренний IP-адрес SBC | Внутренняя подсеть | Местоположение | Внешний NAT (доверенный IP-адрес) |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | Нет | 192.168.1.5 | 192.168.1.0/24 | Вьетнам | 172.16.240.110 |
| IDsbc.contoso.com | Нет | 192.168.2.5 | 192.168.2.0/24 | Индонезия | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | Сингапур | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Исходящие звонки и пользователь находится в том же расположении, что и SBC с помощью always Bypass

| Режим |    Пользователь |  Местоположение |  Направление звонка |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    Internal |  Тот же сайт, что и SBC |  Исходящее |

В следующей таблице показаны конфигурация и действие для конечных пользователей.

| Физическое местонахождение пользователя| Пользователь звонит на номер или принимает его | Номер телефона пользователя  | Политика маршрутинга голосовой почты в Интернете | Режим, настроенный для SBC |
|:------------|:-------|:-------|:-------|:-------|
| Вьетнам | +84 4 3926 3000 | +84 4 5555 5555   | Приоритет 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Приоритет 2: .* — proxysbc.contoso.com   | VNsbc.contoso.com – всегда обходить <br> proxysbc.contoso.com – всегда обходить


На следующей схеме показана схема SIP для исходяшего звонка в режиме обхода Always и пользователя в том же расположении, что и SBC.

![Схема исходящие вызовы](media/direct-routing-media-op-10.png "Исходящие звонки")

В следующей таблице показаны X-MS-загона, отправленные direct Routing:

| Параметр | Пояснение |
|:------------|:-------|
| Пригласить +8443926300@VNsbc.contoso.com | Целевое FQDN SBC, определяемое в политике маршрутинга голосовой почты Online, отправляется в URI запроса. | 
| X-MS-UserLocation: внутреннее | Поле показывает, что пользователь находится в корпоративной сети. |
| X-MS-MediaPath: VNsbc.contoso.com |   Указывает, какой SBC должен проходить через клиент до целевого SBC. В этом случае у нас есть Always Bypass, а клиент является внутренним именем целевого клиента, от которого отправляется только имя в заглавном имени. | 
|X-MS-UserSite: Вьетнам |   Поле, показанное на сайте, где находится пользователь. |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Входящие звонки и пользователь находится в том же расположении, что и SBC с помощью always Bypass

| Режим |    Пользователь |  Местоположение |  Направление звонка |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    Internal | Тот же сайт, что и SBC | Входящий |


При входящий звонок местонахождение пользователя неизвестно, и SBC должен угадать его местонахождение. Если он неправил, потребуется повторно пригласить его. В этом случае предполагается, что пользователь является внутренним, мультимедиа могут перетекать напрямую и не требуются дальнейшие действия (повторное приглашение).
SBC, подключенный к службе direct Routing, сообщает о расположении SBC, Record-Route контактов. На основе этих полей путь к мультимедиа вычисляется путем Direct Routing.

Примечание. Учитывая, что у пользователя может быть несколько конечных точек, поддержка 183 не поддерживается. В этом случае при прямой маршрутике всегда используется 180 звонка. 

На следующей схеме показана схема SIP для входящие зовов с режимом AlwaysBypass, и пользователь находится в том же расположении, что и SBC.

![Схема, показывающая SIP-диаграмму](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>Исходящие звонки и внешний пользователь с помощью always Bypass

| Режим |    Пользователь |  Сайт |  Направление звонка
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Внешняя |  Н/Д | Исходящее |


На следующей схеме показана схема SIP для исходящие вызовы в режиме AlwaysBypass, а пользователь является внешним:

![Схема, показывающая SIP-диаграмму](media/direct-routing-media-op-12.png)

В следующей таблице показаны X-MS-загона, отправленные службой Direct Routing:

| Параметр |   Пояснение |
|:------------|:-------|
|Пригласить +8443926300@VNsbc.contoso.com | Целевое FQDN SBC, определяемое в политике маршрутинга голосовой почты Online, отправляется в URI запроса.|
| X-MS-UserLocation: внешняя | В поле указано, что пользователь находится за пределами корпоративной сети. |
| X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com    | Указывает, какой SBC должен проходить через клиент до целевого SBC. В этом случае мы всегда обходить, и клиент является внешним. |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>Входящие звонки и внешний пользователь с помощью always Bypass

| Режим | Пользователь | Сайт |  Направление звонка |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Внешняя |  Н/Д |   Входящий |

Для входящий звонок SBC, подключенный к прямой маршрутике, должен отправить повторное приглашение (по умолчанию локальные соискатель всегда предлагаются), если расположение пользователя является внешним.  X-MediaPath вычисляется на основе Record-Route и указанного пользователя SBC.

На следующей схеме показана схема SIP для входящий вызовов в режиме AlwaysBypass, и пользователь является внешним.

![Схема, показывающая SIP-диаграмму](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>Только для локальных пользователей

Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC. Во всех остальных случаях мультимедиа проходят через внутренний или внешний IP-адрес прокси-сервера SBC.

Описаны следующие сценарии:

- [Исходящие звонки, и пользователь находится в том же расположении, что и SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Входящие звонки и пользователь находится в том же расположении, что и SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Пользователь находится не в том же расположении, что и SBC, но находится в корпоративной сети](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [Входящие звонки и пользователь является внутренним, но находится в разных местах, что и SBC](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

В следующей таблице показаны конфигурация и действие для конечных пользователей.

| Физическое местонахождение пользователя |  Пользователь звонит на номер или принимает его |  Номер телефона пользователя | Политика маршрутинга голосовой почты в Интернете |   Режим, настроенный для SBC |
|:------------|:-------|:-------|:-------|:-------|
| Вьетнам | +84 4 3926 3000 |  +84 4 5555 5555 | Приоритет 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Приоритет 2: .* — proxysbc.contoso.com | VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Исходящие звонки, а пользователь находится в том же расположении, что и SBC, только для локальных пользователей

| Режим | Пользователь | Сайт | Направление звонка |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Internal |То же, что и SBC   | Исходящее |

На следующей схеме показан исходящие вызовы в режиме OnlyForLocalUsers, и пользователь находится в том же расположении, что и SBC. Такой же поток отображается при исходящие звонки, когда пользователь находится в том же расположении, что [и SBC.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)

![Схема, показывающая SIP-диаграмму](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Входящие звонки, и пользователь находится в том же расположении, что и SBC, и только для локальных пользователей

| Режим | Пользователь | Сайт | Направление звонка |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Internal | То же, что и SBC | Входящий |

На следующей схеме показан входящий звонок в режиме OnlyForLocalUsers, и пользователь находится в том же расположении, что и SBC. Этот поток такой же, как и при входящие звонки, если пользователь находится в том же расположении, что [и SBC.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)

![Схема, показывающая SIP-диаграмму](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>Пользователь находится не в том же расположении, что и SBC, но находится в корпоративной сети только для локальных пользователей

| Режим | Пользователь | Сайт |Направление звонка |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | Internal |   Отличается от SBC | Исходящее |

Прямая маршрутия вычисляет X-MediaPath на основе данных о расположении пользователя и режиме, настроенных на SBC.


На следующей схеме показан исходящие вызовы в режиме OnlyForLocalUsers и внутренний пользователь, который находится не в том же расположении, что и SBC.

![Схема, показывающая SIP-диаграмму](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>Входящий звонок и пользователь является внутренним, но находится в разных местах с SBC только для локальных пользователей

| Режим |    Пользователь |  Сайт |  Направление звонка |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | Internal |    Отличается от SBC |    Входящий |

На следующей схеме показан входящий звонок с режимом OnlyForLocalUsers и внутренним пользователем, который находится не в том же расположении, что и SBC.

![Схема, показывающая SIP-диаграмму](media/direct-routing-media-op-17.png)









