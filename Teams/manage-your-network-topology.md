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
description: Узнайте, как настроить параметры сети для функций облачной голосовой связи в Microsoft Teams.
ms.openlocfilehash: bdb81fa7f8dee559f7c47e276224ecb2333c7bb5
ms.sourcegitcommit: 95a56dab4e30f7ad6615ebd4a4a0f61996fdc20f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/17/2023
ms.locfileid: "69812696"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Управление топологией сети для облачных голосовых функций в Microsoft Teams

Если ваша организация развертывает [маршрутизацию на основе местоположения для прямой маршрутизации](location-based-routing-plan.md) или [динамических экстренных вызовов](configure-dynamic-emergency-calling.md), необходимо настроить параметры сети для использования с этими облачными функциями голосовой связи в Microsoft Teams. Параметры сети используются для определения расположения клиента Teams и включают сетевые регионы, сетевые сайты, подсети и доверенные IP-адреса. В зависимости от функции облачной голосовой связи и возможностей, которые вы развертываете, вы настраиваете некоторые или все эти параметры. Дополнительные сведения об этих терминах см. в статье [Параметры сети для функций облачной голосовой связи](cloud-voice-network-settings.md).

Параметры сети можно настроить на странице **Топология сети** в Центре администрирования Microsoft Teams или с помощью Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Настройка параметров сети в Центре администрирования Microsoft Teams

Сетевые регионы, сетевые сайты и подсети определяются на вкладке **Сетевые сайты** на странице **Топология сети** . Здесь можно создать или изменить сетевой сайт, связать сайт с регионом сети, связать подсеть с сайтом, включить маршрутизацию на основе расположения и назначить ему политики для экстренного реагирования. Можно также добавить сетевые регионы, которые можно использовать глобально для всех сайтов.

#### <a name="add-and-configure-a-network-site"></a>Добавление и настройка сетевого сайта

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в **раздел Расположения** > **Топология сети** и перейдите на вкладку **Сетевые сайты** .
2. Нажмите кнопку **Добавить**, а затем введите имя и описание сайта.

    ![Снимок экрана: страница "Добавление сетевого сайта".](media/manage-network-topology-add-site.png)

3. Чтобы связать сайт с регионом сети, нажмите кнопку **Добавить регион сети**, выберите существующий регион или нажмите кнопку **Добавить** , чтобы добавить регион, а затем нажмите кнопку **Связать**.  
4. Чтобы включить Location-Based маршрутизацию для сайта, включите **маршрутизацию на основе расположения**.
5. Чтобы назначить политикам экстренных служб сайту, выполните одно или оба из следующих действий:

    - Если в вашей организации используются планы звонков, подключение к оператору или прямая маршрутизация, в разделе **Политика экстренных вызовов** выберите нужную политику.
    - Если ваша организация развернула прямую маршрутизацию, в разделе **Политика маршрутизации экстренных вызовов** выберите нужную политику.

6. Чтобы связать подсеть с сайтом, в разделе **Подсети** щелкните **Добавить подсети**. Укажите ip-версию, IP-адрес, диапазон сети, добавьте описание и нажмите кнопку **Применить**. Каждая подсеть должна быть связана с определенным сайтом.
7. Нажмите кнопку **Сохранить**.

#### <a name="modify-a-network-site"></a>Изменение сетевого сайта

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в **раздел Расположения** > **Топология сети** и перейдите на вкладку **Сетевые сайты** .
2. Выберите сайт, щелкнув слева от имени сайта, а затем нажмите кнопку **Изменить**.
3. Внесите необходимые изменения и нажмите кнопку **Сохранить.**

### <a name="manage-external-trusted-ip-addresses"></a>Управление внешними доверенными IP-адресами

Управление внешними доверенными IP-адресами выполняется на вкладке **Доверенные IP-адреса** на странице **Топология сети** в Центре администрирования Microsoft Teams. Вы можете добавить неограниченное количество внешних доверенных IP-адресов.

#### <a name="add-a-trusted-ip-address"></a>Добавление доверенного IP-адреса

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в раздел **Расположения** > **Топология сети**, а затем откройте вкладку **Доверенные IP-адреса** .
2. Выберите **Создать**.
3. В области **Добавление доверенного IP-адреса** укажите версию IP-адреса, IP-адрес, диапазон сети, добавьте описание и нажмите кнопку **Применить**.

    ![Снимок экрана: панель "Добавление доверенного IP-адреса".](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Изменение доверенного IP-адреса

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в раздел **Расположения** > **Топология сети**, а затем откройте вкладку **Доверенные IP-адреса** .
2. Выберите IP-адрес, щелкнув слева от него, а затем нажмите кнопку **Изменить**.
3. В области **Изменение доверенного IP-адреса** внесите необходимые изменения и нажмите кнопку **Применить**.

## <a name="configure-network-settings-using-powershell"></a>Настройка параметров сети с помощью PowerShell

Чтобы выполнить действия, описанные в этом разделе, вам потребуется ознакомиться с командлетами PowerShell. Дополнительные сведения см. в статье [Общие сведения о Teams PowerShell](teams-powershell-overview.md).

### <a name="define-network-regions"></a>Определение регионов сети

 Используйте командлет [New-CsTenantNetworkRegion](/powershell/module/skype/New-CsTenantNetworkRegion) для определения регионов сети. Обратите внимание, что параметр RegionID — это логическое имя, которое представляет географию региона и не имеет зависимостей или ограничений, а параметр CentralSite &lt;site ID&gt; необязателен.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

В этом примере мы создадим регион сети с именем India.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

См. также [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworkregion).

### <a name="define-network-sites"></a>Определение сетевых сайтов

Используйте командлет [New-CsTenantNetworkSite](/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) для определения сетевых сайтов. Каждый сетевой сайт должен быть связан с регионом сети.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

В этом примере мы создадим два новых сетевых сайта, Дели и Хайдарабад, в регионе Индии.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

В следующей таблице показаны сетевые сайты, определенные в этом примере.

|&nbsp;|Сайт 1 |Сайт 2 |
|---------|---------|---------|
|Идентификатор сайта    |    Сайт 1 (Дели)     |  Сайт 2 (Хайдарабад)       |
|Идентификатор региона  |     Регион 1 (Индия)    |   Регион 1 (Индия)      |

См. также [Set-CsTenantNetworkRegion](/powershell/module/skype/set-cstenantnetworksite).

### <a name="define-network-subnets"></a>Определение сетевых подсетей

Используйте командлет [New-CsTenantNetworkSubnet](/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) , чтобы определить подсети сети и связать их с сетевыми сайтами. Каждая подсеть сети может быть связана только с одним сайтом.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

В этом примере мы создадим связь между подсетью 192.168.0.0 и сетевым сайтом Дели, а также между подсетью 2001:4898:e8:25:844e:926f:85ad:dd8e и сайтом сети Hyderabad.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

В следующей таблице показаны подсети, определенные в этом примере.

|&nbsp;|Сайт 1 |Сайт 2 |
|---------|---------|---------|
|Идентификатор подсети   |    192.168.0.0     |  2001:4898:e8:25:844e:926f:85ad:dd8e     |
|Маска  |     24    |   120      |
|Идентификатор сайта  | Сайт (Дели) | Сайт 2 (Хайдарабад) |

Для нескольких подсетей можно импортировать CSV-файл с помощью следующего сценария.

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

Используйте командлет [New-CsTenantTrustedIPAddress](/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) , чтобы определить внешние подсети и назначить их клиенту. Вы можете определить неограниченное количество внешних подсетей для клиента.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

Например:

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

См. также [Set-CsTenantTrustedIPAddress](/powershell/module/skype/set-cstenanttrustedipaddress).

## <a name="enabling-network-roaming-policies"></a>Включение политик сетевого роуминга

Настроив политики сетевого роуминга, необходимо включить **поиск конфигурации сети** в каждой из политик *собраний** в Центре Администратор Teams в разделе **Собрания > политики собраний.**

Вы можете изменить глобальную политику или создать новую политику и назначить ее определенным пользователям.

## <a name="related-topics"></a>См. также

- [Параметры сети для функций облачной голосовой связи в Teams](cloud-voice-network-settings.md)
