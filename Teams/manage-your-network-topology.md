---
title: Управление топологией сети для облачных функций голосовой связи в Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Сведения о том, как настроить параметры сети для функций голосовой связи в облаке в Microsoft Teams.
ms.openlocfilehash: 2f615de14cb38c24a1789b968e7c77e38698e26d
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888708"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Управление топологией сети для облачных функций голосовой связи в Microsoft Teams

Если в вашей организации используется [Прямая маршрутизация](location-based-routing-plan.md) или [динамический вызов экстренной](configure-dynamic-emergency-calling.md)помощи, необходимо настроить параметры сети для использования в этих функциях голосовой связи в Microsoft Teams. Параметры сети используются для определения местоположения клиента Teams и включения сетевых регионов, сетевых сайтов, подсетей и доверенных IP-адресов. В зависимости от того, какая функция голосовой связи облачных функций и возможностей развертывается, вы можете настроить некоторые или все эти параметры. Дополнительные сведения об этих терминах можно найти в разделе [Параметры сети для функций голосовой связи в облаке](cloud-voice-network-settings.md).

Вы настраиваете параметры сети на странице **Сетевая топология** центра администрирования Microsoft Teams или с помощью Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Настройка параметров сети в центре администрирования Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

Вы определяете сетевые регионы, сетевые сайты и подсети на вкладке " **Сетевые сайты** " на странице " **топология сети** ". Здесь вы можете создать или изменить сетевой сайт, связать сайт с сетевым регионом, связать подсеть с сайтом, включить маршрутизацию на основе местоположения и назначить узлу политики для экстренного реагирования. Вы также можете добавить сетевые регионы, которые можно использовать глобально для всех сайтов.

#### <a name="add-and-configure-a-network-site"></a>Добавление и настройка сетевого сайта

1. В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Расположение** > **топологии сети**и откройте вкладку **Сетевые сайты** .
2. Нажмите кнопку **создать**, а затем введите имя и описание сайта.

    ![Снимок экрана: страница "Добавление сетевого сайта"](media/manage-network-topology-add-site.png)

3. Чтобы связать сайт с сетевым регионом, щелкните **ссылку регион сети**, выберите существующий регион или нажмите кнопку **Добавить** , чтобы добавить регион, а затем нажмите кнопку **связать**.  
4. Чтобы включить маршрутизацию на основе местоположения для сайта, включите функцию **маршрутизации на основе**местоположения.
5. Чтобы назначить на сайт политики службы экстренной помощи, выполните одно или оба указанных ниже действия.

    - Если в вашей организации используются планы звонков или прямая маршрутизация на телефонную систему, в разделе **политика вызова экстренной политики**выберите нужную политику.
    - Если ваша организация развернута прямая маршрутизация телефонной системы, выберите нужную политику в разделе **Политика маршрутизации вызова экстренной**помощи.

6. Чтобы связать подсеть с сайтом, в разделе **подсети**нажмите кнопку **Добавить подсети**. Укажите версию IP, IP-адрес, диапазон сети, добавьте описание и нажмите кнопку **Применить**. Каждая подсеть должна быть связана с определенным сайтом.
7. Нажмите кнопку **Сохранить**.

#### <a name="modify-a-network-site"></a>Изменение сетевого сайта

1. В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Расположение** > **топологии сети**и откройте вкладку **Сетевые сайты** .
2. Выберите сайт, щелкнув слева от его имени, а затем нажмите кнопку **изменить**.
3. Внесите нужные изменения и нажмите кнопку **Сохранить.**

### <a name="manage-external-trusted-ip-addresses"></a>Управление внешними надежными IP-адресами

Вы управляете внешними доверенными IP-адресами на вкладке **Надежные** IP-адреса на странице " **топология сети** " в центре администрирования Microsoft Teams. Вы можете добавить неограниченное количество внешних доверенных IP-адресов.

#### <a name="add-a-trusted-ip-address"></a>Добавление надежного IP-адреса

1. В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Расположение** > **топологии сети**и откройте вкладку **Надежные IP** .
2. Выберите **Создать**.
3. В области **Добавить доверенный IP-адрес** укажите версию IP-адреса, IP-адрес, диапазон сети, добавьте описание и нажмите кнопку **Применить**.

    ![Снимок экрана: область "добавить доверенный IP-адрес"](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Изменить доверенный IP-адрес

1. В левой области навигации центра администрирования Microsoft Teams перейдите в раздел **Расположение** > **топологии сети**и откройте вкладку **Надежные IP** .
2. Выберите IP-адрес, щелкнув слева от него и нажмите кнопку **изменить**.
3. В области **изменить доверенный IP-адрес** внесите нужные изменения и нажмите кнопку **Применить**.

## <a name="configure-network-settings-using-powershell"></a>Настройка параметров сети с помощью PowerShell

Для выполнения действий, описанных в этом разделе, вам потребуется ознакомиться с командлетами PowerShell. Дополнительные сведения можно найти в разделе [Общие сведения о Teams PowerShell](teams-powershell-overview.md).

### <a name="define-network-regions"></a>Определение регионов сети

 Используйте командлет [New-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) , чтобы определить регионы сети. Обратите внимание, что параметр RegionID является логическим именем, которое представляет собой географию области и не имеет зависимостей или ограничений и &lt;не является&gt; обязательным параметром идентификатора сайта CentralSite.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

В этом примере мы создаем сетевой регион с именем Индии.
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

Дополнительные сведения можно найти в разделе [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion).

### <a name="define-network-sites"></a>Определение сетевых сайтов

С помощью командлета [New-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) можно определять сетевые сайты. Каждый сетевой сайт должен быть связан с сетевым регионом.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

В этом примере мы создаем в регионе Индии две новые сетевые сайты, Delhi и Hyderabad.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

В следующей таблице показаны сетевые сайты, определенные в этом примере.

||Сайт 1 |Сайт 2 |
|---------|---------|---------|
|Идентификатор сайта    |    Сайт 1 (Delhi)     |  Сайт 2 (Hyderabad)       |
|КОД региона  |     Регион 1 (Индия)    |   Регион 1 (Индия)      |

Дополнительные сведения можно найти в разделе [Set-CsTenantNetworkRegion](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite).

### <a name="define-network-subnets"></a>Определение подсетей сети

С помощью командлета [New-CsTenantNetworkSubnet](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) можно определять сетевые подсети и связывать их с сетевыми сайтами. Каждая сетевая подсеть может быть связана только с одним сайтом.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

В этом примере мы создаем связь между подсетью 192.168.0.0 и сетевым сайтом Delhi и между подсетью 2001:4898: E8:25:844E: 926f: 85ad: dd8e и на сайте Hyderabad Network.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

В приведенной ниже таблице указаны подсети, определенные в этом примере.

||Сайт 1 |Сайт 2 |
|---------|---------|---------|
|КОД подсети   |    172.16.0.0     |  2001:4898: E8:25:844E: 926f: 85ad: dd8e     |
|Маски  |     24    |   120      |
|Идентификатор сайта  | Сайт (Delhi) | Сайт 2 (Hyderabad) |

Если вы используете несколько подсетей, вы можете импортировать CSV-файл с помощью такого сценария, как описано ниже.

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.SubnetID-MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

В этом примере CSV-файл выглядит примерно так:

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```

Дополнительные сведения можно найти в разделе [Set-CsTenantNetworkSubnet](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet).

### <a name="define-external-subnets-external-trusted-ip-addresses"></a>Определение внешних подсетей (внешние доверенные IP-адреса)

С помощью командлета [New-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) можно определять внешние подсети и назначать их клиентам. Вы можете определить неограниченное количество внешних подсетей для клиента.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

Например:

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

Дополнительные сведения можно найти в разделе [Set-CsTenantTrustedIPAddress](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress).

## <a name="related-topics"></a>Статьи по теме

- [Параметры сети для функций голосовой связи в облаке в Teams](cloud-voice-network-settings.md)
