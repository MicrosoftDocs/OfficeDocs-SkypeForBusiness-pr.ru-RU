---
title: Настройка оптимизации локальных мультимедиа для прямой маршрутизации в Teams
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
description: Настройка локальной оптимизации мультимедиа для прямой маршрутизации
appliesto:
- Microsoft Teams
ms.openlocfilehash: cf370087d109ebd12da150af44d2f13b455f4f6e
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235364"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a>Настройка локальной оптимизации мультимедиа для прямой маршрутизации

Конфигурация для оптимизации локальных мультимедиа основана на параметрах сети, которые являются общими для других облачных функций голосовой связи, таких как маршрутизация Location-Based маршрутизация и динамические экстренные вызовы. Дополнительные информацию о сетевых регионах, сетевых сайтах, сетевых подсетях и доверенных IP-адресах см. в настройках сети для облачных [голосовых функций.](cloud-voice-network-settings.md)

Прежде чем настраивать оптимизацию локальных мультимедиа, см. оптимизацию локальных [мультимедиа для прямой маршрутизации.](direct-routing-media-optimization.md)  

Чтобы настроить оптимизацию локальных мультимедиа, необходимо сделать следующее: Вы можете использовать Teams или PowerShell. Подробные сведения см. в [теме Управление топологией сети.](manage-your-network-topology.md)

1. Настройте пользователя и сайты SBC (как описано в этой статье).
2. Настройте SBCs для оптимизации локальных мультимедиа (в соответствии с спецификацией поставщика SBC).

На следующей схеме показана настройка сети, используемая в примерах этой статьи.

![Диаграмма с примерами настройки сети](media/direct-routing-media-op-9.png "Примеры настройки сети")


## <a name="configure-the-user-and-the-sbc-sites"></a>Настройка пользователя и сайтов SBC

Чтобы настроить пользователя и сайты SBC, необходимо:

1. [Управление внешними надежными IP-адресами.](#manage-external-trusted-ip-addresses)  

2. [Определите топологию сети,](#define-the-network-topology) настроив сетевые регионы, сетевые сайты и подсети.

3. [Определите топологию](#define-the-virtual-network-topology) виртуальной сети, назначив SBC-серверам сайтам соответствующие режимы и значения SBC прокси-сервера.


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a>Настройка SBC для локальной оптимизации мультимедиа в соответствии с спецификацией поставщика SBC

В этой статье описана конфигурация компонентов Майкрософт. Сведения о конфигурации SBC см. в документации поставщиков SBC.

Оптимизация локальных мультимедиа поддерживается следующими поставщиками SBC:

| Поставщик | ПРОИЗВЕД |    Версия программного обеспечения |
|:------------|:-------|:-------|
| [Audiocodes](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    Mediant 500 SBC |   7.20A.256 | 
|            |  Mediant 800 SBC |   7.20A.256 | 
|            |  Mediant 2600 SBC |  7.20A.256 | 
|            |  Mediant 4000 SBC |  7.20A.256 | 
|            |  Mediant 1000B SBC | 7.20A.256 | 
|            |  Mediant 9000 SBC |  7.20A.256 | 
|            |  Mediant Virtual Edition SBC |   7.20A.256 | 
|            |  Mediant Cloud Edition SBC | 7.20A.256 |
| [Ядро SBC на ленте](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  SBC 5110         | 8.2  |
|            |  SBC 5210         | 8.2  |
|            |  SBC 5400         | 8.2  |
|            |  SBC 7000         | 8.2  |
|            |  SBC SWe          | 8.2  |
| [Edge SBC на ленте](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  SBC SWe Lite | 8.1.5 |
|               | SBC 1000 | 8.1.5  |
|               | SBC 2000 | 8.1.5  |
| [TE-SYSTEMS](https://www.anynode.de/local_media_optimization/) |  anynode          | 4.0.1+ |
| [Oracle](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | AP 1100 | 8.4.0.0.0 |
|        | AP 3900 | 8.4.0.0.0 |
|        | AP 4600 | 8.4.0.0.0 | 
|        | AP 6300 | 8.4.0.0.0 |
|        | AP 6350 | 8.4.0.0.0 | 
|        | VME     | 8.4.0.0.0 |


## <a name="manage-external-trusted-ip-addresses"></a>Управление внешними надежными IP-адресами

Внешние доверенные IP являются внешними IP-сайтами корпоративной сети. Это IP-адреса, используемые клиентами Microsoft Teams при подключении к Microsoft 365. Эти внешние IP-сообщения необходимо добавить для каждого сайта, на котором есть пользователи, использующие локализованную оптимизацию мультимедиа.

Чтобы добавить общедоступные IP-адреса для каждого сайта, используйте New-CsTenantTrustedIPAddress управления. Для клиента можно определить неограниченное количество доверенных IP-адресов. Если внешние IP-Microsoft 365 являются ip-адресами IPv4 и IPv6, необходимо добавить оба типа IP-адресов. Для IPv4 используйте маску 32. Для IPv6 используйте маску 128. Вы можете добавить как отдельные внешние IP-адреса, так и внешние подсети IP-адресов, указав разные маскибиты в этом окне.

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

Все параметры с чувствительностью к делу, поэтому необходимо убедиться, что используется тот же случай, что и при установке.  (Например, значения GatewaySiteID "Вьетнам" и "Вьетнам" будут рассматриваться как разные сайты.)

### <a name="define-network-regions"></a>Определение сетевых регионов

Чтобы определить сетевые регионы, используйте New-CsTenantNetworkRegion. Параметр RegionID — это логическое имя, которое представляет географическое положение региона и не имеет зависимостей или ограничений. Параметр CentralSite `<site ID>` необязателен.

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

В следующем примере создается сетевой регион с именем APAC:

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a>Определение сетевых сайтов

Чтобы определить сетевые сайты, используйте New-CsTenantNetworkSite сети. Каждый сетевой сайт должен быть связан с сетевым регионом.

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

В следующем примере создаются три новых сетевых сайта : Вьетнам, Индонезия и Сингапур в регионе APAC:

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a>Определение сетевых подсетей

Чтобы определить сетевые подсети и связать их с сетевыми сайтами, используйте New-CsTenantNetworkSubnet управления. Каждую сетевую подсеть можно связывать только с одним сайтом. 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

В следующем примере определяются три сетевые подсети и они связывается с тремя сетевыми сайтами: Вьетнам, Индонезия и Сингапур:

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a>Определение топологии виртуальной сети 

Во-первых, администратор клиента создает новую конфигурацию SBC для каждого соответствующего SBC с помощью New-CsOnlinePSTNGateway SBC.
Администратор клиента определяет топологию виртуальной сети, указав сетевые сайты для объектов шлюза STN с Set-CsOnlinePSTNGateway шлюза:

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

Обратите внимание на следующее: 
   - Если у клиента один SBC, параметр -ProxySBC должен быть обязательным $null или FQDN SBC (Центр SBC с централизованной связи).
   - Параметр -MediaBypass должен иметь $true для поддержки локальной оптимизации мультимедиа.
   - Если у SBC нет параметра -BypassMode, X-MS не будет отправлен. 
   - Все параметры с чувствительностью к делу, поэтому необходимо убедиться, что используется тот же случай, который использовался при установке.  (Например, значения GatewaySiteID "Вьетнам" и "Вьетнам" будут рассматриваться как разные сайты.)

В следующем примере три SBCs добавляются на сетевые сайты Вьетнам, Индонезия и Сингапур в регионе APAC в режиме Всегда обходить:

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

Примечание. Чтобы обеспечить непрерывное прерывание операций при одновременной настройке локальных операций оптимизации мультимедиа и маршрутизации Location-Based (LBR), необходимо включить SBCs downstream для LBR, задав для параметра GatewaySiteLbrEnabled $true для каждого теного SBC. (Этот параметр не является обязательным для прокси-сервера SBC.)

На основе вышеприведенной информации прямая маршрутия включает три собственных заглавных заглавных таблицы SIP для приглашений sIP и повторного приглашения, как показано в таблице ниже.

X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:

| Header name | Значения | Комментарии | 
|:------------|:-------|:-------|
| X-MS-UserLocation | внутренние и внешние | Указывает, является ли пользователь внутренним или внешним |
| Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0 | SBC FQDN | FQDN, целевое для звонка, даже если SBC не подключен напрямую к прямой маршрутике |
| X-MS-MediaPath | Пример: proxysbc.contoso.com, VNsbc.contoso.com | Порядок SBCs, которые должны использоваться для пути мультимедиа между пользователем и целевой SBC. Последний SBC всегда должен быть последним |
| X-MS-userSite | usersiteID | Строка, определяемая администратором клиента |

## <a name="call-flows"></a>Потоки вызовов 

Ниже показаны потоки зова для двух режимов.

- [Всегда обходить](#always-bypass-mode)
- [Только для локальных пользователей](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a>Всегда обходить режим

Режим всегда обходить — простейший вариант, который нужно настроить. Администратор клиента может настроить один сайт для всех пользователей и веб-сайтов, если все SBCs находятся на любом сайте.

В примерах приводится режим обхода всегда для следующих сценариев:

- [Исходящие звонки и пользователь находится в том же расположении, что и УАЗОВ](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Входящие звонки, и пользователь находится в том же расположении, что и УАЗОВ](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [Исходящие звонки и пользователь является внешним](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [Входящие звонки и пользователь является внешним](#inbound-calls-and-the-user-is-external-with-always-bypass)

В следующей таблице показаны FQDN и IP-адреса, используемые в примерах:

| Полное доменное имя | Внешний IP-адрес SBC | Внутренний IP-адрес SBC | Внутренняя подсеть | Местоположение | Внешний NAT (надежный IP-адрес) |
|:------------|:-------|:-------|:-------|:-------|:-------|
| VNsbc.contoso.com | Нет | 192.168.1.5 | 192.168.1.0/24 | Вьетнам | 172.16.240.110 |
| IDsbc.contoso.com | Нет | 192.168.2.5 | 192.168.2.0/24 | Индонезия | 172.16.240.120 |
| proxysbc.contoso.com | 172.16.240.133 | 192.168.3.5 | 192.168.3.0/24 | Сингапур | 172.16.240.130 |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Исходящие звонки и пользователь находится в том же расположении, что и SBC с помощью always Bypass

| Режим |    Пользователь |  Местоположение |  Направление звонка |
|:------------|:-------|:-------| :-------|
| AlwaysBypass |    Internal |  Тот же сайт, что и SBC |  Исходящее |

В следующей таблице показаны конфигурация и действие для конечных пользователей.

| Физическое местонахождение пользователя| Пользователь совершает или принимает звонок на/с номера | Номер телефона пользователя  | Политика маршрутинга голосовой почты в Интернете | Режим, настроенный для SBC |
|:------------|:-------|:-------|:-------|:-------|
| Вьетнам | +84 4 3926 3000 | +84 4 5555 5555   | Приоритет 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Приоритет 2: .* — proxysbc.contoso.com   | VNsbc.contoso.com — всегда обходить <br> proxysbc.contoso.com — всегда обходить


На следующей схеме показана SIP-интерфейс для исходящие вызовы в режиме обхода Всегда, а пользователь находится в том же расположении, что и SBC.

![Схема исходящие вызовы](media/direct-routing-media-op-10.png "Исходящие звонки")

В следующей таблице показаны X-MS-заглавные заглавные данные, отправленные при прямой маршрутике:

| Параметр | Пояснение |
|:------------|:-------|
| Пригласить +8443926300@VNsbc.contoso.com | Целевое FQDN SBC, задаваемое в политике маршрутинга голосовой почты Online, отправляется в URI запроса. | 
| X-MS-UserLocation: внутренние | Поле, в которое указано, что пользователь находится в корпоративной сети |
| X-MS-MediaPath: VNsbc.contoso.com |   Определяет, какой SBC должен проходить клиентом до целевого SBC. В этом случае, так как у нас есть Всегда обходить, и клиент является внутренним целевое имя, отправленное как единственное имя в header. | 
|X-MS-userSite: Вьетнам |   Поле, указанные на сайте, где находится пользователь. |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a>Входящие звонки и пользователь находится в том же расположении, что и SBC с помощью always Bypass

| Режим |    Пользователь |  Местоположение |  Направление звонка |
|:------------|:-------|:-------|:-------|:-------|
| AlwaysBypass |    Internal | Тот же сайт, что и SBC | Входящих |


При входящий звонок местонахождение пользователя неизвестно, и SBC должен угадать, где он находится. Если предположить, что он неправиа, потребуется повторно пригласить его. В этом случае предполагается, что пользователь является внутренним, мультимедиа могут перетекать напрямую и не требуются дополнительные действия (повторное приглашение).
SBC, подключенный к службе direct Routing, сообщает о расположении SBC, Record-Route поля контактов. На основе этих полей путь к мультимедиа вычисляется с помощью прямой маршрутии.

Примечание. Если у пользователя может быть несколько конечных точек, поддержка 183 не поддерживается. В этом случае при прямой маршрутике всегда будет использоваться 180 звонка. 

На следующей схеме показано, как SIP следует входить в входящие вызовы в режиме AlwaysBypass, а пользователь находится в том же расположении, что и SBC.

![Схема, показывающая SIP-запятую.](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a>Исходящие звонки и внешний пользователь с помощью always Bypass

| Режим |    Пользователь |  Сайт |  Направление звонка
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Внешняя |  Недоступно | Исходящее |


На следующей схеме показана SIP-интерфейс для исходящие вызовы в режиме AlwaysBypass, и пользователь является внешним:

![На схеме показана запятая SIP.](media/direct-routing-media-op-12.png)

В следующей таблице показаны X-MS-заглавные таблицы, отправленные службой Direct Routing.

| Параметр |   Пояснение |
|:------------|:-------|
|Пригласить +8443926300@VNsbc.contoso.com | Конечное FQDN SBC, задаваемое в политике маршрутинга голосовой почты Online, отправляется в URI запроса.|
| X-MS-UserLocation: внешний | В поле указано, что пользователь находится за пределами корпоративной сети. |
| X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com    | Определяет, какой SBC должен проходить клиентом до целевого SBC. В этом случае, так как у нас есть Всегда обходить, и клиент является внешним. |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a>Входящие звонки и пользователь является внешним с помощью always Bypass

| Режим | Пользователь | Сайт |  Направление звонка |
|:------------|:-------|:-------|:-------|
AlwaysBypass |  Внешняя |  Недоступно |   Входящих |

Для входящий звонок SBC, подключенный к прямой маршрутике, должен отправить повторное приглашение (по умолчанию местные кандидаты мультимедиа всегда предлагаются), если расположение пользователя является внешним.  X-MediaPath вычисляется на основе Record-Route и указанного пользователя SBC.

На следующей схеме показана SIP-интерфейс для входящий вызов в режиме AlwaysBypass, и пользователь является внешним.

![На схеме снова показана разнотипная схема SIP.](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a>Только для локальных пользователей

Местные медиа кандидаты на целевой SBC будут предлагаться только в том случае, если пользователь находится в том же расположении, что и SBC. Во всех остальных случаях мультимедиа проходят через внутренний или внешний IP-адрес прокси-сервера SBC.

Описаны следующие сценарии:

- [Исходящие звонки и пользователь находится в том же расположении, что и УАЗОВ](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Входящие звонки и пользователь находится в том же расположении, что и SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [Пользователь находится не там, где находится SBC, но находится в корпоративной сети](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [Входящие звонки, и пользователь является внутренним, но не находится в том же расположении, что и SBC](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

В следующей таблице показаны конфигурация и действия для конечных пользователей.

| Физическое местонахождение пользователя |  Пользователь совершает или принимает звонок на/с номера |  Номер телефона пользователя | Политика маршрутинга голосовой почты в Интернете |   Режим, настроенный для SBC |
|:------------|:-------|:-------|:-------|:-------|
| Вьетнам | +84 4 3926 3000 |  +84 4 5555 5555 | Приоритет 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com <br> Приоритет 2: .* — proxysbc.contoso.com | VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Исходящие звонки, и пользователь находится в том же расположении, что и SBC, только для локальных пользователей.

| Режим | Пользователь | Сайт | Направление звонка |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Internal |То же, что и SBC   | Исходящее |

На следующей схеме показан исходящие вызовы в режиме OnlyForLocalUsers, и пользователь находится в том же расположении, что и SBC. Такой же поток отображается в исходящие звонки, если пользователь находится в том же расположении, что [и SBC.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)

![На схеме снова показана запятая SIP.](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a>Входящие звонки, и пользователь находится в том же расположении, что и SBC, только для локальных пользователей.

| Режим | Пользователь | Сайт | Направление звонка |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers |   Internal | То же, что и SBC | Входящих |

На следующей схеме показан входящий звонок в режиме OnlyForLocalUsers, и пользователь находится в том же расположении, что и SBC. Этот поток такой же, как в Входящие звонки, если пользователь находится в том же расположении, что [и SBC.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)

![Еще одна схема, на которой показана разнотипная схема SIP.](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a>Пользователь находится не в том же расположении, что и SBC, но находится в корпоративной сети только для локальных пользователей.

| Режим | Пользователь | Сайт |Направление звонка |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers  | Internal |   Отличается от SBC | Исходящее |

Прямая маршрутия вычисляет X-MediaPath в зависимости от расположения пользователя и режима, настроенного на SBC.


На следующей схеме показан исходящие вызовы в режиме OnlyForLocalUsers и внутренним пользователем, который находится не в том же расположении, что и SBC.

![На другой схеме показана поножовка SIP.](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a>Входящий звонок, и пользователь является внутренним, но не находится в том же расположении, что и SBC только для локальных пользователей

| Режим |    Пользователь |  Сайт |  Направление звонка |
|:------------|:-------|:-------|:-------|
| OnlyForLocalUsers | Internal |    Отличается от SBC |    Входящих |

На следующей схеме показан входящий звонок с режимом OnlyForLocalUsers и внутренним пользователем, который находится не в том же расположении, что и SBC.

![Еще одна схема с демонстрацией SIP.](media/direct-routing-media-op-17.png)









