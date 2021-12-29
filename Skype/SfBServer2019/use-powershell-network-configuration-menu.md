---
title: Использование PowerShell для задач в меню конфигурации сети
ms.reviewer: ''
ms.author: ankum
author: ankum
manager: ravrao
ms.date: 11/03/2021
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: ''
description: Сводка. Skype для бизнеса Server панели управления к сопоставлению cmdlet для меню конфигурации сети.
ms.openlocfilehash: aa42ac465ffd72a4aff9c03293124c857e5b712c
ms.sourcegitcommit: 3b5ae6ebf4384166c628f66a4f17e6fe4455b708
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/29/2021
ms.locfileid: "61626521"
---
# <a name="network-configuration"></a>Конфигурация сети

В этой статье описывается, как аналогичные результаты элемента меню **конфигурации** сети в устаревшей панели управления могут быть достигнуты с помощью cmdlets.

В этой статье описаны следующие подмены:

- [Конфигурация сети](#network-configuration)
  - [Политика расположения](#location-policy)
  - [Политика пропускной способности](#bandwidth-policy)
  - [Region](#region)
  - [Site](#site)
  - [Subnet](#subnet)
  - [Регион Ссылка](#region-link)
  - [Маршрут региона](#region-route)

## <a name="location-policy"></a>Политика определения местонахождения

Меню **LOCATION POLICY** используется для применения параметров, которые относятся к функциям E9-1-1. Политика расположения определяет, может ли пользователь использовать службу E9-1-1, а также задает поведение экстренного вызова.

Рассмотрим различные задачи, которые пользователь может выполнять в политике **LOCATION,** а также Skype для бизнеса эти задачи.

---

> **Сценарий 1.** Список всех политик расположения

   ![Политика расположения списка](./media/location-policy-1.png)

***Командлет***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***Пример***

```powershell
 Get-CsLocationPolicy
```

---

> **Сценарий 2.** Создание новой политики расположения

   ![Создание политики расположения](./media/location-policy-2.png)

***Командлет***

[New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy)  

***Пример***

```powershell
 New-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

> **Сценарий 3.** Сведения о выбранной политике расположения

   ![Получить политику расположения](./media/location-policy-3.png)

***Командлет***

[Get-CsLocationPolicy](/powershell/module/skype/get-cslocationpolicy)

***Пример***

```powershell
 Get-CsLocationPolicy -Identity Reno
```

---

> **Сценарий 4.** Удаление выбранных политик расположения

   ![Удаление политики расположения](./media/location-policy-4.png)

***Командлет***

[Remove-CsLocationPolicy](/powershell/module/skype/remove-cslocationpolicy)

***Пример***

```powershell
 Remove-CsLocationPolicy -Identity Reno
```

---

> **Сценарий 5.** Обновление политики расположения

   ![Политика обновления расположения](./media/location-policy-5.png)

***Командлет***

[Set-CsLocationPolicy](/powershell/module/skype/set-cslocationpolicy)

***Пример***

```powershell
 Set-CsLocationPolicy -Identity site:Redmond -EnhancedEmergencyServicesEnabled $True
```

---

## <a name="bandwidth-policy"></a>Политика пропускной способности

В рамках контроля допуска звонков политика пропускной способности используется, чтобы определять ограничения пропускной способности для конкретных модальностей. (В Skype для бизнеса Server могут быть назначены ограничения пропускной способности только аудио и видео.) Этот комлет создает профиль контейнера для этих политик. Вы определяете отдельные политики в этом контейнере, указывая ограничения для звука и видео при вызове этого командлета.

Рассмотрим различные задачи, которые пользователь может выполнять в политике пропускной способности, и Skype для бизнеса этих задач.

---
> **Сценарий 1.** Список всех политик пропускной способности

   ![Политика пропускной способности списка](./media/bandwidth-policy-1.png)

***Командлет***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***Пример***

```powershell
 Get-CsNetworkBandwidthPolicyProfile
```

---

> **Сценарий 2.** Создание новой политики пропускной способности

   ![Новая политика пропускной способности](./media/bandwidth-policy-2.png)

***Командлет***

[New-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile)  

***Пример***

```powershell
 New-CsNetworkBandwidthPolicyProfile -Identity LowBWLimits -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400 -VideoBWSessionLimit 500
```

---

> **Сценарий 3.** Сведения о выбранной политике пропускной способности

   ![Получить политику пропускной способности](./media/bandwidth-policy-3.png)

***Командлет***

[Get-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile)

***Пример***

```powershell
 Get-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **Сценарий 4.** Удаление выбранных политик пропускной способности

   ![Удаление политики пропускной способности](./media/bandwidth-policy-4.png)

***Командлет***

[Remove-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile)

***Пример***

```powershell
 Remove-CsNetworkBandwidthPolicyProfile -Identity LowBWProfile
```

---

> **Сценарий 5.** Обновление политики пропускной способности

   ![Политика обновления пропускной способности](./media/bandwidth-policy-5.png)

***Командлет***

[Set-CsNetworkBandwidthPolicyProfile](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile)

***Пример***

```powershell
 Set-CsNetworkBandwidthPolicyProfile -Identity LowBWLimit -VideoBWLimit 2500 -VideoBWSessionLimit 300
```

---

## <a name="region"></a>Регион

Область сети связывает части сети, расположенные в различных географических районах. Каждый регион сети должен быть связан с центральным сайтом. Администраторы могут использовать меню **REGION** для управления сведениями об одном или нескольких сетевых регионах, включая связанный центральный сайт и параметры, которые определяют, разрешены ли альтернативные пути для аудио- и видеосвязи, а сайты в регионе связываются с конфигурацией обхода мультимедиа.

---

> **Сценарий 1.** Список всех регионов

   ![Область списков](./media/network-region-1.png)

***Командлет***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***Пример***

```powershell
 Get-CsNetworkRegion
```

---

> **Сценарий 2.** Создание нового региона

   ![Создание региона](./media/network-region-2.png)

***Командлет***

[New-CsNetworkRegion](/powershell/module/skype/new-csnetworkregion)  

***Пример***

```powershell
 New-CsNetworkRegion -Identity NorthAmerica -Description "All North American Locations" -CentralSite Redmond-NA-MLS
```

---

> **Сценарий 3.** Сведения об выбранном регионе

   ![Get Region](./media/network-region-3.png)

***Командлет***

[Get-CsNetworkRegion](/powershell/module/skype/get-csnetworkregion)

***Пример***

```powershell
 Get-CsNetworkRegion -Identity NorthAmerica
```

---

> **Сценарий 4.** Удаление выбранных регионов

   ![Удаление области](./media/network-region-4.png)

***Командлет***

[Remove-CsNetworkRegion](/powershell/module/skype/remove-csnetworkregion)

***Пример***

```powershell
 Remove-CsNetworkRegion -Identity NorthAmerica
```

---

> **Сценарий 5.** Обновление региона

   ![Область обновления](./media/network-region-5.png)

- **Аннотация 1 — результат**

    Эта аннотация на изображении указывает результат, то есть полученные и отображаемые данные.

    ***Командлет***

    [Get-CsNetworkSite из региона](/powershell/module/skype/get-csnetworksite)

    ***Пример***

    ```powershell
     Get-CsNetworkSite | Where-Object {$_.NetworkRegionID -eq "AKR"}
    ```

- **Аннотация 2 — параметр (для пользователя)**

    Эта аннотация на изображении указывает на возможность для пользователя реализовать, то есть сохранить сетевой регион.

    [Set-CsNetworkRegion](/powershell/module/skype/set-csnetworkregion)

   ***Пример***

   ```powershell
   Set-CsNetworkRegion -Identity NorthAmerica -Description "North American Region"
   ```

---

## <a name="site"></a>Site

Сетевые сайты — это офисы или местоположения, заданные внутри каждого региона развертывания CAC или E9-1-1. **Подмена** SITE помогает администраторам добавлять, удалять или управлять их настройками.

Рассмотрим различные задачи, которые пользователь может выполнять на **САЙТе,** и Skype для бизнеса эти задачи на карте.

---

> **Сценарий 1.** Список всех сайтов

   ![Список сайта](./media/network-site-1.png)

***Командлет***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***Пример***

```powershell
 Get-CsNetworkSite
```

---

> **Сценарий 2.** Создание нового сайта

   ![Создание сайта](./media/network-site-2.png)

***Командлет***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksite)  

***Пример***

```powershell
 New-CsNetworkSite -Identity Vancouver -NetworkRegionID NorthAmerica
```

---

> **Сценарий 3.** Сведения об выбранном сайте

   ![Получить сайт](./media/network-site-3.png)

***Командлет***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksite)

***Пример***

```powershell
 Get-CsNetworkSite -Identity Redmond
```

---

> **Сценарий 4.** Удаление выбранных сайтов

   ![Удаление сайта](./media/network-site-4.png)

***Командлет***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksite)

***Пример***

```powershell
 Remove-CsNetworkSite -Identity Vancouver
```

---

> **Сценарий 5.** Обновление сайта

   ![Обновление сайта](./media/network-site-5.png)

- **Аннотация 1 — результат**

    Эта аннотация на изображении указывает результат, то есть полученные и отображаемые данные.

    ***Командлет***

    [Get-CsNetworkSubnet с сайта](/powershell/module/skype/get-csnetworksubnet)

    ***Пример***

    ```powershell
     Get-CsNetworkSubnet | Where-Object {$_.NetworkSiteID -eq "Vancouver"}
    ```

- **Аннотация 2 — параметр (для пользователя)**

    Эта аннотация на изображении указывает на возможность для пользователя реализовать, то есть сохранить сетевой сайт.

   ***Командлет***

   [Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksite)

   ***Пример***

   ```powershell
    Set-CsNetworkSite -Identity Vancouver - BWPolicyProfileID LowBWLimits
   ```

---

## <a name="subnet"></a>Подсеть

Администраторы могут использовать **sub-menu SUBNET** для создания, обновления и управления сетевыми подсетями.

Рассмотрим различные задачи, которые пользователь может выполнять в **SUBNET,** и Skype для бизнеса эти задачи будут на карте.

---

> **Сценарий 1.** Список всех подсетей

   ![Подсеть списка](./media/network-subnet-1.png)

***Командлет***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***Пример***

```powershell
 Get-CsNetworkSubnet
```

---

> **Сценарий 2.** Создание новой подсети

   ![Создание подсети](./media/network-subnet-2.png)

***Командлет***

[New-CsNetworkSubnet](/powershell/module/skype/new-csnetworksubnet)  

***Пример***

```powershell
 New-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 24 -NetworkSiteID Vancouver
```

---

> **Сценарий 3.** Сведения об выбранной подсети

   ![Get Subnet](./media/network-subnet-3.png)

***Командлет***

[Get-CsNetworkSubnet](/powershell/module/skype/get-csnetworksubnet)

***Пример***

```powershell
 Get-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **Сценарий 4.** Удаление выбранных подсетей

   ![Удаление подсети](./media/network-subnet-4.png)

***Командлет***

[Remove-CsNetworkSubnet](/powershell/module/skype/remove-csnetworksubnet)

***Пример***

```powershell
 Remove-CsNetworkSubnet -Identity 172.11.15.0
```

---

> **Сценарий 5.** Обновление подсети

   ![Обновление подсети](./media/network-subnet-5.png)

***Командлет***

[Set-CsNetworkSubnet](/powershell/module/skype/set-csnetworksubnet)

***Пример***

```powershell
 Set-CsNetworkSubnet -Identity 172.11.15.0 -MaskBits 25 -NetworkSiteID Chicago
```

---

## <a name="region-link"></a>Регион Ссылка

Регионы в сети связаны физическим подключением WAN. Администраторы могут использовать **подмену REGION LINK** для создания, обновления и управления сетевыми подсетями.

Рассмотрим различные задачи, которые пользователь может выполнять в **РЕГИОНЕ LINK,** и Skype для бизнеса эти задачи на карте.

---

> **Сценарий 1.** Список всех ссылок региона

   ![Ссылка на область списка](./media/network-regionlink-1.png)

***Командлет***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***Пример***

```powershell
 Get-CsNetworkRegionLink
```

---

> **Сценарий 2.** Создание новой ссылки региона

   ![Создание ссылки регион](./media/network-regionlink-2.png)

***Командлет***

[New-CsNetworkRegionLink](/powershell/module/skype/new-csnetworkregionLink)  

***Пример***

```powershell
 New-CsNetworkRegionLink -Identity NA_EMEA -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID LowBWLimits
```

---

> **Сценарий 3.** Сведения об выбранной ссылке по региону

   ![Get Region Link](./media/network-regionlink-3.png)

***Командлет***

[Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

***Пример***

```powershell
 Get-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **Сценарий 4.** Удаление ссылок выбранного региона

   ![Удаление ссылки Регион](./media/network-regionlink-4.png)

***Командлет***

[Remove-CsNetworkRegionLink](/powershell/module/skype/remove-csnetworkregionLink)

***Пример***

```powershell
 Remove-CsNetworkRegionLink -Identity NA_EMEA
```

---

> **Сценарий 5.** Обновление ссылки региона

   ![Обновление ссылки региона](./media/network-regionlink-5.png)

***Командлет***

[Set-CsNetworkRegionLink](/powershell/module/skype/set-csnetworkregionLink)

***Пример***

```powershell
 Set-CsNetworkRegionLink -Identity NA_EMEA -BWPolicyProfileID HighBWLimits
```

---

## <a name="region-route"></a>Маршрут региона

Каждый регион в конфигурации CAC должен быть каким-либо образом связан с каждым другим регионом. Связь между регионами устанавливает ограничения пропускной способности на соединения между регионами, а также представляет собой физические подключения, в то время как маршрут определяет, по какому пути осуществляется соединение одного региона с другим. Администраторы могут использовать **подмену REGION ROUTE** для создания, обновления и управления ими.

Рассмотрим различные задачи, которые пользователь может выполнять в **РЕГИОН** ROUTE, и Skype для бизнеса эти задачи на карте.

---

> **Сценарий 1.** Список всех маршрутов региона

   ![Маршрут области списка](./media/network-regionroute-1.png)

***Командлет***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***Пример***

```powershell
 Get-CsNetworkInterRegionRoute
```

---

> **Сценарий 2.** Создание нового маршрута региона

   ![Создание маршрута региона](./media/network-regionroute-2.png)

***Командлет***

[New-CsNetworkInterRegionRoute](/powershell/module/skype/new-csnetworkinterregionroute)  

***Пример***

```powershell
 New-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA_EMEA,EMEA_APAC"
```

---

> **Сценарий 3.** Сведения о выбранном маршруте региона

   ![Маршрут "Регион"](./media/network-regionroute-3.png)

***Командлет***

[Get-CsNetworkInterRegionRoute](/powershell/module/skype/get-csnetworkinterregionroute)

***Пример***

```powershell
 Get-CsNetworkInterRegionRoute -Filter *APAC*
```

---

> **Сценарий 4.** Удаление маршрутов выбранного региона

   ![Удаление маршрутов региона](./media/network-regionroute-4.png)

***Командлет***

[Remove-CsNetworkInterRegionRoute](/powershell/module/skype/remove-csnetworkinterregionroute)

***Пример***

```powershell
 Remove-CsNetworkInterRegionRoute -Identity NA_APAC_Route
```

---

> **Сценарий 5.** Обновление маршрута региона

   ![Обновление маршрута региона](./media/network-regionroute-5.png)

- **Аннотация 1 — параметр (для пользователя)**

    Эта аннотация на изображении указывает результат, то есть полученные и отображаемые данные.

   ***Командлет***

   [Get-CsNetworkRegionLink](/powershell/module/skype/get-csnetworkregionLink)

   ***Пример***

   ```powershell
   Get-CsNetworkRegionLink
   ```

- **Аннотация 2 — параметр (для пользователя)**

    Эта аннотация на изображении указывает пользователю возможность реализовать, то есть сохранить маршрут сетевого региона.

    ***Командлет***

   [Set-CsNetworkInterRegionRoute](/powershell/module/skype/set-csnetworkinterregionroute)

   ***Пример***

   ```powershell
   Set-CsNetworkInterRegionRoute -Identity NA_APAC_Route -NetworkRegionLinkIDs "NA_SA,SA_APAC"
   ```

---
---
