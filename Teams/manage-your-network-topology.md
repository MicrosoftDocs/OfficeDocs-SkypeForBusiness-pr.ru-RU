---
title: Управление топологией сети для функций облачного голосового управления в Microsoft Teams
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
- m365initiative-voice
f1.keywords:
- CSH
ms.custom: ms.teamsadmincenter.networktopology.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Узнайте, как настроить параметры сети для функций облачного голосового связи в Microsoft Teams.
ms.openlocfilehash: 2414010a6e7098a18954067dad659cb8c9912736
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031105"
---
# <a name="manage-your-network-topology-for-cloud-voice-features-in-microsoft-teams"></a>Управление топологией сети для функций облачного голосового управления в Microsoft Teams

Если ваша организация [](location-based-routing-plan.md) развертывает маршрутную маршрутику на основе местоположения для прямой маршрутизации или динамических экстренных вызовов, [](configure-dynamic-emergency-calling.md)необходимо настроить параметры сети для использования с этими облачными функциями голосовой связи в Microsoft Teams. Параметры сети используются для определения расположения клиента Teams и включают сетевые регионы, сетевые сайты, подсети и надежные IP-адреса. В зависимости от функции облачного голосового голоса и возможности развертывания вы можете настроить некоторые или все эти параметры. Подробнее об этих условиях см. в параметрах сети для [функций облачного голосового связи.](cloud-voice-network-settings.md)

Параметры сети настраиваются на **странице** топологии сети Центра администрирования Microsoft Teams или с помощью Windows PowerShell.

## <a name="configure-network-settings-in-the-microsoft-teams-admin-center"></a>Настройка параметров сети в Центре администрирования Microsoft Teams

[!INCLUDE [preview-feature](includes/preview-feature.md)]

На вкладке "Сетевые сайты" страницы топологии сети определяются сетевые регионы, сетевые сайты **и** подсети.  Здесь можно создать или изменить сетевой сайт, связать сайт с сетевым регионом, связать с ним подсеть, включить маршрутизация на основе расположения и назначить на сайт политики экстренной помощи. Вы также можете добавить сетевые регионы, которые можно использовать глобально для всех сайтов.

#### <a name="add-and-configure-a-network-site"></a>Добавление и настройка сетевого сайта

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в топологию **сетей Locations** и щелкните вкладку  >   **"Сетевые сайты".**
2. Нажмите **кнопку**"Добавить" и введите имя и описание сайта.

    ![Снимок экрана: страница добавления сайта сети](media/manage-network-topology-add-site.png)

3. Чтобы связать сайт с сетевым регионом, щелкните "Добавить  регион сети", выберите существующий регион или нажмите кнопку "Добавить", чтобы добавить регион, а затем нажмите кнопку **"Ссылка".**  
4. Чтобы включить Location-Based для сайта, включив **маршрутную маршрутку на основе расположения.**
5. Чтобы назначить на сайт политики экстренных служб, сделайте следующее:

    - Если в вашей организации используются планы звонков или развернута прямая маршрутия телефонной системы, в соответствии с политикой экстренных вызовов **выберите** политику.
    - Если в вашей организации развернута прямая маршрутия телефонной системы, выберите ее в соответствии с политикой маршрутизации экстренных вызовов.

6. Чтобы связать подсеть с сайтом, в **подсетях** нажмите кнопку **"Добавить подсети".** Укажите версию IP-адреса, IP-адрес, диапазон сети, добавьте описание и нажмите кнопку **"Применить".** Каждую подсеть необходимо связывать с определенным сайтом.
7. Щелкните **Сохранить**.

#### <a name="modify-a-network-site"></a>Изменение сайта сети

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в топологию **сетей Locations** и щелкните вкладку  >   **"Сетевые сайты".**
2. Выберите сайт, щелкнув слева от его имени и нажав кнопку **"Изменить".**
3. Внести нужные изменения и нажмите кнопку **"Сохранить".**

### <a name="manage-external-trusted-ip-addresses"></a>Управление внешними надежными IP-адресами

Управление внешними надежными IP-адресами происходит  на вкладке **"Надежные IP-адреса"** на странице топологии сети Центра администрирования Microsoft Teams. Вы можете добавить неограниченное количество внешних доверенных IP-адресов.

#### <a name="add-a-trusted-ip-address"></a>Добавление надежного IP-адреса

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в топологию **сети** locations и перейдите на вкладку  >  "Надежные **адреса IPs".**
2. Выберите **Создать**.
3. В области **"Добавление** доверенных IP-адресов" укажите версию IP-адреса, IP-адрес, диапазон сети, добавьте описание и нажмите кнопку **"Применить".**

    ![Снимок экрана: области "Добавление доверенных IP-адресов"](media/manage-network-topology-add-trusted-ip.png)

#### <a name="edit-a-trusted-ip-address"></a>Изменение надежного IP-адреса

1. В левой области навигации Центра администрирования Microsoft Teams перейдите в топологию **сети** locations и перейдите на вкладку  >  "Надежные **адреса IPs".**
2. Выберите IP-адрес, щелкнув слева от него и нажав кнопку **"Изменить".**
3. В области **"Изменить надежные IP-адреса"** внесите нужные изменения и нажмите кнопку "Применить". 

## <a name="configure-network-settings-using-powershell"></a>Настройка параметров сети с помощью PowerShell

Для выполнения действий, которые вы выполните в этом разделе, необходимо ознакомиться с cmdlets PowerShell. Дополнительные сведения см. в [обзоре Teams PowerShell.](teams-powershell-overview.md)

### <a name="define-network-regions"></a>Определение сетевых регионов

 Для определения сетевых регионов используйте командлет [New-CsTenantNetworkRegion.](https://docs.microsoft.com/powershell/module/skype/New-CsTenantNetworkRegion) Обратите внимание, что параметр RegionID — это логическое имя, которое представляет географическое положение региона и не имеет зависимостей и ограничений, а параметр "ИД центрального сайта" &lt; &gt; необязателен.

```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

В этом примере мы создадим сетевой регион "Индия".
```PowerShell
New-CsTenantNetworkRegion -NetworkRegionID "India"  
```

См. [также Set-CsTenantNetworkRegion.](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworkregion)

### <a name="define-network-sites"></a>Определение сетевых сайтов

Для определения сетевых сайтов [используйте командлет New-CsTenantNetworkSite.](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksite?view=skype-ps) Каждый сетевой сайт должен быть связан с сетевым регионом.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

В этом примере мы создадим два новых сетевых сайта— "Кузьмина" и "Кузьмина" в Индии.

```PowerShell
New-CsTenantNetworkSite -NetworkSiteID "Delhi" -NetworkRegionID "India"
New-CsTenantNetworkSite -NetworkSiteID "Hyderabad" -NetworkRegionID "India"
```

В таблице ниже показаны сетевые сайты, определенные в данном примере.

||Сайт 1 |Сайт 2 |
|---------|---------|---------|
|ИД сайта    |    Сайт 1 (Висяк)     |  Сайт 2 (Приокрет)       |
|ИД региона  |     Регион 1 (Индия)    |   Регион 1 (Индия)      |

См. [также Set-CsTenantNetworkRegion.](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite)

### <a name="define-network-subnets"></a>Определение сетевых подсетей

Используйте [командлет New-CsTenantNetworkSubnet,](https://docs.microsoft.com/powershell/module/skype/new-cstenantnetworksubnet?view=skype-ps) чтобы определить подсети сети и связать их с сетевыми сайтами. Каждую сетевую подсеть можно связывать только с одним сайтом.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

В этом примере мы создадим связь между подсетей 192.168.0.0 и сетевым сайтом "Ветвь" и между подсети 2001:4898:e8:25:844e:926f:85ad:dd8e и сайтом сети Послевузова.

```PowerShell
New-CsTenantNetworkSubnet -SubnetID "192.168.0.0" -MaskBits "24" -NetworkSiteID "Delhi"
New-CsTenantNetworkSubnet -SubnetID "2001:4898:e8:25:844e:926f:85ad:dd8e" -MaskBits "120" -NetworkSiteID "Hyderabad"
```

В следующей таблице показаны подсети, определенные в данном примере.

||Сайт 1 |Сайт 2 |
|---------|---------|---------|
|ИД подсети   |    192.168.0.0     |  2001:4898:e8:25:844e:926f:85ad:dd8e     |
|Маска  |     24    |   120      |
|ИД сайта  | Сайт (Высве)) | Сайт 2 (Приокрет) |

Для нескольких подсетей CSV-файл можно импортировать с помощью следующего сценария:

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

См. [также Set-CsTenantNetworkSubnet.](hhttps://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksubnet)

### <a name="define-external-subnets-external-trusted-ip-addresses"></a>Определение внешних подсетей (внешних доверенных IP-адресов)

Чтобы определить внешние подсети и назначить их для клиента, используйте для этого [cmdlet New-CsTenantTrustedIPAddress.](https://docs.microsoft.com/powershell/module/skype/new-cstenanttrustedipaddress?view=skype-ps) Для клиента можно определить неограниченное количество внешних подсетей.

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description> 
```

Например:

```PowerShell
New-CsTenantTrustedIPAddress -IPAddress 198.51.100.0 -MaskBits 30 -Description "Contoso address"  
```

См. [также Set-CsTenantTrustedIPAddress.](https://docs.microsoft.com/powershell/module/skype/set-cstenanttrustedipaddress)

## <a name="related-topics"></a>Статьи по теме

- [Параметры сети для функций облачного голосового связи в Teams](cloud-voice-network-settings.md)
