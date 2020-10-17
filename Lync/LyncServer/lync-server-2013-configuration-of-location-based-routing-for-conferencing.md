---
title: 'Lync Server 2013: Настройка маршрутизации Location-Based для конференц-связи'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuration of Location-Based Routing for conferencing
ms:assetid: d8c708cc-a1b1-48b1-808c-a64df15f7701
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362846(v=OCS.15)
ms:contentKeyID: 56335088
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd5ada5e4af1ed4ed43434ddf4d82abc25f4cd5e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48507806"
---
# <a name="configuration-of-location-based-routing-for-conferencing-in-lync-server-2013"></a>Настройка маршрутизации Location-Based для конференц-связи в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-09-11_

Приложение для конференц-связи Location-Based маршрутизации использует конфигурацию сервера Lync Server 2013 Location-Based маршрутизации. Ниже приведены основные конфигурации.

  - Расположение участников, присоединяющихся к собранию, определяется на основе их сетевого сайта. Сетевой сайт и связанные с ним подсети должны быть определены в Lync Server для принудительного применения маршрутизации Location-Based.

  - Чтобы обеспечить Location-Based маршрутизацию собраний, участники Lync должны быть включены для маршрутизации Location-Based.

  - Для обеспечения Location-Based маршрутизации конечных точек PSTN присоединение к собраниям необходимо настроить маршрутизацию SIP, используемую для подключения конечных точек PSTN для Location-Based маршрутизации.

Для получения дополнительных сведений о развертывании и настройке службы маршрутизации Lync Server 2013 Location-Based, обратитесь к разделу Настройка [маршрутизации на основе расположения](lync-server-2013-configuring-location-based-routing.md).

<div>

## <a name="enabling-the-location-based-routing-conferencing-application"></a>Включение приложения для конференц-связи Location-Based маршрутизации

Приложение для конференц-связи по Location-Based маршрутизации отключено по умолчанию. Перед включением этого приложения необходимо определить правильный приоритет, назначаемый приложению. Чтобы определить этот приоритет, выполните следующий командлет в командной консоли Lync Server:

```powershell
Get-CsServerApplication -Identity Service:Registrar:<Pool FQDN>
```

В этом командлете \<Pool FQDN\> — это пул, в котором включается приложение для конференц-связи с Location-Based маршрутизации.

Этот командлет возвращает список приложений, размещенных в Lync Server, и значение приоритета для каждого из них. Приложению для конференц-связи Location-Based маршрутизации необходимо назначить значение приоритета, большее, чем приложение "Удкажент" и меньше, чем приложения "Дефаултраутинг", "ExumRouting" и "Аутбаундраутинг". Мы рекомендуем назначить приложению для конференц-связи по Location-Based маршрутизации значение приоритета, равное одной точке выше значения приоритета приложения "Удкажент".

Например, если для приложения "Удкажент" задано значение приоритета "2", то приложение "Дефаултраутинг" имеет значение Priority "8", а приложение "ExumRouting" имеет значение приоритета "9", а приложение "Аутбаундраутинг" имеет значение приоритета "10", после чего необходимо назначить приложению для конференц-связи Location-Based значение приоритета "3". При этом приоритет приложений будет помещаться в следующем порядке: другие приложения (приоритеты: от 0 до 1), "Удкажент" (приоритет: 2), Location-Based приложение для конференц-связи (приоритет: 3), другие приложения (приоритеты: от 4 до 8), "Дефаултраутинг" (приоритет: 9), "ExumRouting" (приоритет: 10) и "Аутбаундраутинг" (приоритет: 11).

Когда вы найдете правильное значение приоритета для приложения Location-Basedной конференц-связи, введите следующий командлет для каждого пула Front-End или сервера Standard Edition, для которого включены пользователи жилых подключений для Location-Based маршрутизации:

```powershell
New-CsServerApplication -Identity Service:Registrar:<Pool FQDN>/LBRouting -Priority <Application Priority> -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

Например:

```powershell
New-CsServerApplication -Identity Service:Registrar:LS2013CU2LBRPool.contoso.com/LBRouting -Priority 3 -Enabled $true -Critical $true -Uri http://www.microsoft.com/LCS/LBRouting
```

После использования этого командлета перезапустите все серверы переднего плана в пуле или серверы Standard Edition, на которых было включено приложение для конференц-связи Location-Based маршрутизации.

<div>


> [!IMPORTANT]  
> Location-Based принудительная маршрутизация для конференций или передач Консультативного не будет применяться, пока не будут перезапущены все серверы переднего плана в соответствующих пулах или серверы Standard Edition.



</div>

После успешного включения приложения для конференц-связи Location-Based и повторного запуска всех соответствующих серверов Lync все конференции, организованные пользователями Lync, включенные для маршрутизации Location-Based, будут отслеживаться, чтобы предотвратить обход бесплатных звонков по сети PSTN

</div>

</div>

<span> </span>

</div>

</div>

</div>

