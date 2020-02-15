---
title: 'Lync Server 2013: Настройка поддержки автообнаружения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring support for Autodiscover
ms:assetid: 3a266456-69a0-4539-ba99-d388b83799a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945622(v=OCS.15)
ms:contentKeyID: 51541463
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79511202ddc9e413e313d12f881e7079f088c473
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046072"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>Настройка поддержки автообнаружения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-21_

**Служба автообнаружения** веб-служб Lync Server впервые появилась в накопительном обновлении lync Server 2010: Ноябрь 2011. Это обновление сопровождается первоначальным выпуском мобильных клиентов Lync. Служба автообнаружения предоставляла службы Mobility Services, называемые службой MCX.

Служба автообнаружения выступает в качестве единого расположения для всех клиентов, которые запрашивают сведения о доступных службах и функциях, а также о том, как связаться с севицес — либо с полным доменным именем, либо с помощью URL-адреса URL-адреса. Служба автообнаружения предоставляет ряд функций, и каждый клиент делает запросы на основе компонентов, которые может использовать клиент. Например, клиент Lync 2013 для настольных компьютеров будет использовать аутодисквоер для определения внешних веб-служб, но не будет использовать службы Mobility (MCX). Чтобы правильно определить и разрешить клиентам использовать доступные вам функции, необходимо определить сценарии, позволяющие клиенту эффективно находить и использовать записи автообнаружения. Чтобы использовать аутодосковер, в развертывании требуется, чтобы обратный прокси опубликовал веб-службы Lync Server, что записи DNS настроены для разрешения DNS-запросов для службы автообнаружения Lync Server и веб-служб Lync Server, а также для этих служб сертификатов. правильно настроены для конкретного сценария.

<div>


> [!TIP]  
> Технические сведения о том, что делают элементы в запросе и ответе службы автообнаружения, можно узнать <A href="lync-server-2013-understanding-autodiscover.md">в статье Общие сведения о службе автообнаружения в Lync Server 2013</A>.



</div>

Приведенные ниже сведения и таблицы определяют, какие конфигурации (при необходимости) необходимо реализовать для предоставления полного и эффективного использования службы автообнаружения. Сведения, приведенные в следующих разделах, относятся к Microsoft Lync Server 2013. Если вы ищете руководство по планированию мобильных устройств для Lync Server 2010, ознакомьтесь [http://go.microsoft.com/fwlink/?LinkId=275113](http://go.microsoft.com/fwlink/?linkid=275113)со статьей. Чтобы развернуть Mobility for Lync Server 2010, ознакомьтесь со статьей[http://go.microsoft.com/fwlink/?LinkId=275114](http://go.microsoft.com/fwlink/?linkid=275114)

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка DNS для автообнаружения в Lync Server 2013](lync-server-2013-configuring-dns-for-autodiscover.md)

  - [Настройка сертификатов для автообнаружения в Lync Server 2013](lync-server-2013-configuring-certificates-for-autodiscover.md)

  - [Настройка обратного прокси-сервера для автообнаружения в Lync Server 2013](lync-server-2013-configuring-a-reverse-proxy-for-autodiscover.md)

  - [Настройка службы автообнаружения в Lync Server 2013 для гибридных развертываний](lync-server-2013-configuring-autodiscover-for-hybrid-deployments.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

