---
title: Управление топологией сети для облачных голосовых функций в Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Узнайте, как настроить параметры сети для облачных функций голосовой связи в Microsoft Teams.
ms.openlocfilehash: 701e3900980b628f66d9d62d3dade987fee821fe
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/30/2021
ms.locfileid: "58726578"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Управление топологией сети для облачных голосовых функций в Microsoft Teams

Если в вашей [](location-based-routing-plan.md) организации развертывается маршрутная маршрутия на основе местоположения для прямой маршрутизации или динамических экстренных вызовов, [](configure-dynamic-emergency-calling.md)необходимо настроить параметры сети для использования с этими облачными функциями голосовой связи в Microsoft Teams. Параметры сети используются для определения расположения клиента Teams и включают сетевые регионы, сетевые сайты, подсети и доверенные IP-адреса. В зависимости от облачной голосовой функции и возможности развертывания вы можете настроить некоторые или все эти параметры. Дополнительные информацию об этих терминах см. в настройках [сети для облачных функций голосовой связи.](cloud-voice-network-settings.md)

Параметры сети можно настроить  на странице Топология сети центра администрирования Microsoft Teams или с помощью Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Настройка параметров сети в Центре Microsoft Teams администрирования

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Сетевые регионы, сетевые сайты и подсети определяются на вкладке Сетевые **сайты** на странице **Топология** сети. Здесь можно создать или изменить сетевой сайт, связать сайт с сетевым регионом, связать с ним подсеть, включить маршрутизация на основе местоположения и назначить сайту политики экстренного размещения. Вы также можете добавить сетевые регионы, которые можно использовать глобально для всех сайтов.

#### <a name="add-and-configure-a-network-site"></a>Добавление и настройка сетевого сайта

1. В левой области навигации центра администрирования Microsoft Teams перейдите в топологию **сети** местоположений и перейдите  >  на **вкладку Сетевые сайты.**
2. Нажмите **кнопку** Добавить и введите имя и описание сайта.

    ![Снимок экрана: страница "Добавление сетевого сайта".](media/manage-network-topology-add-site.png)

3. Чтобы связать сайт с сетевым регионом, щелкните Добавить  сетевой регион **,** выберите существующий регион или нажмите кнопку Добавить, чтобы добавить регион, а затем нажмите кнопку **Ссылка**.  
4. Чтобы включить Location-Based маршрутику для сайта, включите маршрутику на основе **расположения.**
5. Чтобы назначить на сайт политики экстренных служб, сделайте следующее:

    - Если ваша организация использует планы звонков или развернута телефонная система прямой маршрутизации, в области Политика экстренных вызовов **выберите** политику.
    - Если ваша организация развернула телефонная система маршрутизации, в области Политика маршрутизации экстренных вызовов **выберите** политику.

6. Чтобы связать подсеть с сайтом, в области **Подсети** щелкните **Добавить подсети.** Укажите версию IP-адреса, IP-адрес, диапазон сети, добавьте описание и нажмите кнопку **Применить.** Каждая подсеть должна быть связана с определенным сайтом.
7. Нажмите кнопку **Сохранить**.

#### <a name="modify-a-network-site"></a>Изменение сайта сети

1. В левой области навигации центра администрирования Microsoft Teams перейдите в топологию **сети** местоположений и перейдите  >  на **вкладку Сетевые сайты.**
2. Выберите сайт, щелкнув слева от его имени и выбрав **изменить**.
3. Внести нужные изменения и нажмите кнопку **Сохранить.**

### <a name="manage-external-trusted-ip-addresses"></a>Управление внешними надежными IP-адресами

Управление внешними надежными IP-адресами можно  управлять на вкладке Надежные **IP-адреса** на странице топологии сети Microsoft Teams центре администрирования. Вы можете добавить неограниченное количество внешних доверенных IP-адресов.

#### <a name="add-a-trusted-ip-address"></a>Добавление надежного IP-адреса

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в топологию **сети** расположения и перейдите на вкладку  >   **Надежные адреса.**
2. Выберите **Создать**.
3. В области **Добавление надежного IP-адреса** укажите IP-версию, IP-адрес, диапазон сети, добавьте описание и нажмите кнопку **Применить**.

    ![Снимок экрана: области "Добавление надежного IP-адреса".](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Изменение надежного IP-адреса

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в топологию **сети** расположения и перейдите на вкладку  >   **Надежные адреса.**
2. Выберите IP-адрес, щелкнув слева от него и выбрав **изменить**.
3. В области **Изменение надежного IP-адреса** внесите нужные изменения и нажмите кнопку **Применить**.

## <a name="configure-network-settings-using-powershell"></a>Настройка параметров сети с помощью PowerShell

Для выполнения действий, которые вы выполните в этом разделе, вам потребуется ознакомиться с помощью powerShell.) Дополнительные сведения см. [в Teams PowerShell.](teams-powershell-overview.md)

### <a name="define-network-regions"></a>Определение сетевых регионов

 Для определения сетевых регионов используйте командлет [New-CsTenantNetworkRegion.](/powershell/module/skype/New-CsTenantNetworkRegion) Обратите внимание, что параметр RegionID — это логическое имя, которое представляет географическое положение региона и не имеет зависимостей или ограничений, а параметр CentralSite &lt; Site ID необязателен. &gt;

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

В этом примере мы создадим сетевой регион с именем Индия.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

См. [также Set-CsTenantNetworkRegion.](/powershell/module/skype/set-cstenantnetworkregion)

### <a name="define-network-sites"></a>Определение сетевых сайтов

Для определения сетевых сайтов используйте командлет [New-CsTenantNetworkSite.](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) Каждый сетевой сайт должен быть связан с сетевым регионом.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

В этом примере мы создадим два новых сетевых сайта — "Кузьмина" и "Кузьмина" в индийском регионе.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

В таблице ниже показаны сетевые сайты, определенные в данном примере.

||Сайт 1 |Сайт 2 |
|---------|---------|---------|
|ИД сайта    |    Сайт 1 (вЕтвях)     |  Сайт 2 (Кузьмина)       |
|ИД региона  |     Регион 1 (Индия)    |   Регион 1 (Индия)      |

См. [также Set-CsTenantNetworkRegion.](/powershell/module/skype/set-cstenantnetworksite)

### <a name="define-network-subnets"></a>Определение сетевых подсетей

С помощью [командлета New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) можно определить сетевые подсети и связать их с сетевыми сайтами. Каждую сетевую подсеть можно связывать только с одним сайтом.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

В этом примере мы создадим связь между подсетей 192.168.0.0 и сетевым сайтом "Объединение" и между подсети 2001:4898:e8:25:844e:926f:85ad:dd8e и сайтом сети Диссерии.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

В таблице ниже показаны подсети, определенные в данном примере.

||Сайт 1 |Сайт 2 |
|---------|---------|---------|
|ИД подсети   |    192.168.0.0     |  2001:4898:e8:25:844e:926f:85ad:dd8e     |
|Маска  |     24    |   120      |
|ИД сайта  | Сайт (Висяк) | Сайт 2 (Кузьмина) |

CSV-файл можно импортировать для нескольких подсетей с помощью следующего сценария:

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

В этом примере CSV-файл выглядит так:

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


См. [также Set-CsTenantNetworkSubnet.](/powershell/module/skype/set-cstenantnetworksubnet)


### <a name="define-external-subnets-external-trusted-ip-addresses"></a>Определение внешних подсетей (внешних доверенных IP-адресов)

Чтобы определить внешние подсети и назначить их клиенту, используйте для этого [cmdlet New-CsTenantTrustedIPAddress.](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) Для клиента можно определить неограниченное количество внешних подсетей.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

Например:

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

См. [также Set-CsTenantTrustedIPAddress.](/powershell/module/skype/set-cstenanttrustedipaddress)

## <a name="related-topics"></a>Статьи по теме

- [Параметры сети для облачных функций голосовой связи в Teams](cloud-voice-network-settings.md)
