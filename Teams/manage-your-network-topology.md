---
title: Управление топологией сети для облачных голосовых функций в Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
- m365initiative-voice
- highpri
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Узнайте, как настроить параметры сети для облачных голосовых функций в Microsoft Teams.
ms.openlocfilehash: a75ce05a29df84bb46cb430016e1a3453e96b64e
ms.sourcegitcommit: cbcf37f395832bed871fe709b87c6eecb1fdfd72
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2022
ms.locfileid: "68584250"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Управление топологией сети для облачных голосовых функций в Microsoft Teams

Если ваша организация развертывает маршрутизацию на основе расположения для прямой маршрутизации или динамических экстренных [](location-based-routing-plan.md) вызовов[, необходимо](configure-dynamic-emergency-calling.md) настроить параметры сети для использования с этими облачными функциями голосовой связи в Microsoft Teams. Параметры сети используются для определения расположения клиента Teams и включают сетевые регионы, сетевые сайты, подсети и доверенные IP-адреса. В зависимости от функции облачной голосовой связи и возможностей, которые вы развертываете, вы настраиваете некоторые или все эти параметры. Дополнительные сведения об этих терминах см. в разделе ["Параметры сети" для облачных голосовых функций](cloud-voice-network-settings.md).

Параметры сети настраиваются **на странице** топологии сети в Центре администрирования Microsoft Teams или с помощью Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Настройка параметров сети в Центре администрирования Microsoft Teams

Вы определяете сетевые регионы, сетевые сайты и подсети на вкладке **"** Сетевые сайты" на странице **топологии** сети. Здесь можно создать или изменить сетевой сайт, связать сайт с сетевым регионом, связать подсеть с сайтом, включить маршрутизацию на основе расположения и назначить сайту политики экстренного реагирования. Вы также можете добавить сетевые регионы, которые можно использовать глобально для всех сайтов.

#### <a name="add-and-configure-a-network-site"></a>Добавление и настройка сетевого сайта

1. В левой области навигации Центра администрирования Microsoft Teams перейдите к топологии **сети** >  расположений **и** перейдите на вкладку **"Сетевые сайты**".
2. Нажмите **кнопку** "Добавить", а затем введите имя и описание сайта.

    ![Снимок экрана: страница "Добавление сетевого сайта".](media/manage-network-topology-add-site.png)

3. Чтобы связать сайт с сетевым регионом, щелкните "Добавить сетевой регион **", выберите** существующий регион или нажмите кнопку "Добавить", чтобы добавить регион, а затем нажмите кнопку **"Ссылка"**.  
4. Чтобы включить Location-Based маршрутизации для сайта, включите маршрутизацию **на основе расположения**.
5. Чтобы назначить сайту политики экстренных служб, выполните одно или оба из следующих действий:

    - Если в вашей организации используются планы звонков, подключение оператора или прямая маршрутизация, в разделе "Политика экстренных вызовов" выберите политику.
    - Если ваша организация развернула прямую маршрутизацию, в разделе политики маршрутизации экстренных вызовов выберите политику.

6. Чтобы связать подсеть с сайтом, в разделе " **Подсети**" нажмите кнопку **"Добавить подсети"**. Укажите версию IP-адреса, IP-адрес, диапазон сети, добавьте описание и нажмите кнопку "Применить **"**. Каждая подсеть должна быть связана с определенным сайтом.
7. Нажмите кнопку **Сохранить**.

#### <a name="modify-a-network-site"></a>Изменение сетевого сайта

1. В левой области навигации Центра администрирования Microsoft Teams перейдите к топологии **сети** >  расположений **и** перейдите на вкладку **"Сетевые сайты**".
2. Выберите сайт, щелкнув слева от имени сайта, а затем нажмите кнопку "Изменить **"**.
3. Внесите необходимые изменения и нажмите кнопку " **Сохранить".**

### <a name="manage-external-trusted-ip-addresses"></a>Управление внешними доверенными IP-адресами

Вы управляете внешними доверенными IP-адресами на вкладке "Надежные **IP-адреса**" на странице топологии сети Центра администрирования Microsoft Teams. Вы можете добавить неограниченное количество внешних доверенных IP-адресов.

#### <a name="add-a-trusted-ip-address"></a>Добавление доверенного IP-адреса

1. В левой области навигации Центра администрирования Microsoft Teams перейдите к топологии **сети** >  расположений **и** перейдите на вкладку **"Надежные IP-адреса**".
2. Выберите **Создать**.
3. В области **"Добавление доверенного IP-адреса** " укажите версию IP-адреса, IP-адрес, диапазон сети, добавьте описание и нажмите кнопку " **Применить"**.

    ![Снимок экрана: панель "Добавление доверенного IP-адреса".](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Изменение доверенного IP-адреса

1. В левой области навигации Центра администрирования Microsoft Teams перейдите к топологии **сети** >  расположений **и** перейдите на вкладку **"Надежные IP-адреса**".
2. Выберите IP-адрес, щелкнув его слева, а затем нажмите кнопку "Изменить **"**.
3. В области **"Изменение доверенного IP-адреса** " внесите необходимые изменения и нажмите кнопку "Применить **"**.

## <a name="configure-network-settings-using-powershell"></a>Настройка параметров сети с помощью PowerShell

Для выполнения действий, описанных в этом разделе, необходимо ознакомиться с командлетами PowerShell. Дополнительные сведения см. в [обзоре Teams PowerShell](teams-powershell-overview.md).

### <a name="define-network-regions"></a>Определение сетевых регионов

 Используйте [командлет New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) для определения сетевых регионов. Обратите внимание, что параметр RegionID является логическим именем, представляющее географию региона и не имеет зависимостей или ограничений, а параметр идентификатора сайта CentralSite &lt;&gt; является необязательным.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

В этом примере мы создадим сетевой регион с именем India.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

См. также [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworkregion).

### <a name="define-network-sites"></a>Определение сетевых сайтов

Используйте [командлет New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) для определения сетевых сайтов. Каждый сетевой сайт должен быть связан с сетевым регионом.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

В этом примере мы создадим в индийском регионе два новых сетевых сайта — "Гофайла" и "Окремент".

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

В следующей таблице показаны сетевые сайты, определенные в этом примере.

|&nbsp;|Сайт 1 |Сайт 2 |
|---------|---------|---------|
|Идентификатор сайта    |    Сайт 1 (Индия)     |  Сайт 2 (Сша)       |
|Идентификатор региона  |     Регион 1 (Индия)    |   Регион 1 (Индия)      |

См. также [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworksite).

### <a name="define-network-subnets"></a>Определение сетевых подсетей

Используйте [командлет New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) , чтобы определить сетевые подсети и связать их с сетевыми сайтами. Каждая подсеть сети может быть связана только с одним сайтом.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

В этом примере мы создадим связь между подсетью 192.168.0.0 и сетевым сайтом "Посчитание", а также между подсетью 2001:4898:e8:25:844e:926f:85ad:dd8e и сетевым сайтом Приложения.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

В следующей таблице показаны подсети, определенные в этом примере.

|&nbsp;|Сайт 1 |Сайт 2 |
|---------|---------|---------|
|Идентификатор подсети   |    192.168.0.0     |  2001:4898:e8:25:844e:926f:85ad:dd8e     |
|Маска  |     24    |   120      |
|Идентификатор сайта  | Сайт (Сша) | Сайт 2 (Сша) |

Для нескольких подсетей CSV-файл можно импортировать с помощью следующего скрипта.

```PowerShell
Import-CSV C:\subnet.csv | foreach {New-CsTenantNetworkSubnet –SubnetID $_.Identity -MaskBits $_.Mask -NetworkSiteID $_.SiteID}  
```

В этом примере CSV-файл выглядит примерно так:

```console
Identity, Mask, SiteID
172.11.12.0, 24, Redmond
172.11.13.0, 24, Chicago
172.11.14.0, 25, Vancouver
172.11.15.0, 28, Paris
```


См. также [Set-CsTenantNetworkSubnet](/powershell/module/skype/set-cstenantnetworksubnet).


### <a name="define-external-subnets-external-trusted-ip-addresses"></a>Определение внешних подсетей (внешних доверенных IP-адресов)

Используйте [командлет New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) , чтобы определить внешние подсети и назначить их клиенту. Вы можете определить неограниченное количество внешних подсетей для клиента.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

Например:

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

См. также [Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress).

## <a name="related-topics"></a>См. также

- [Параметры сети для функций облачной голосовой связи в Teams](cloud-voice-network-settings.md)
