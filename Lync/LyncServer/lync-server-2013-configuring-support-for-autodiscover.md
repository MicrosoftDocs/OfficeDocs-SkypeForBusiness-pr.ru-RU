---
title: 'Lync Server 2013: Настройка поддержки автообнаружения'
description: 'Lync Server 2013: Настройка поддержки автообнаружения.'
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
ms.openlocfilehash: 23991f2f9467035f4ba461ff1b6a84fa8ed1a11d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556915"
---
# <a name="configuring-support-for-autodiscover-in-lync-server-2013"></a>Настройка поддержки автообнаружения в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-21_

**Служба автообнаружения** веб-служб Lync Server впервые появилась в накопительном обновлении lync Server 2010: Ноябрь 2011. Это обновление сопровождается первоначальным выпуском мобильных клиентов Lync. Служба автообнаружения предоставляла службы Mobility Services, называемые службой MCX.

Служба автообнаружения выступает в качестве единого расположения для всех клиентов, которые запрашивают сведения о доступных службах и функциях, а также о том, как связаться с севицес — либо с полным доменным именем, либо с помощью URL-адреса URL-адреса. Служба автообнаружения предоставляет ряд функций, и каждый клиент делает запросы на основе компонентов, которые может использовать клиент. Например, клиент Lync 2013 для настольных компьютеров будет использовать аутодисквоер для определения внешних веб-служб, но не будет использовать службы Mobility (MCX). Чтобы правильно определить и разрешить клиентам использовать доступные вам функции, необходимо определить сценарии, позволяющие клиенту эффективно находить и использовать записи автообнаружения. Для использования аутодосковер необходимо, чтобы обратный прокси-сервер опубликовал веб-службы Lync Server, что записи DNS настроены для разрешения DNS-запросов для службы автообнаружения Lync Server и веб-служб Lync Server, а службы сертификации правильно настроены для конкретного сценария.

<div>


> [!TIP]  
> Технические сведения о том, что делают элементы в запросе и ответе службы автообнаружения, можно узнать <A href="lync-server-2013-understanding-autodiscover.md">в статье Общие сведения о службе автообнаружения в Lync Server 2013</A>.



</div>

Приведенные ниже сведения и таблицы определяют, какие конфигурации (при необходимости) необходимо реализовать для предоставления полного и эффективного использования службы автообнаружения. Сведения, приведенные в следующих разделах, относятся к Microsoft Lync Server 2013. Если вы ищете руководство по планированию мобильных устройств для Lync Server 2010, ознакомьтесь со статьей [https://go.microsoft.com/fwlink/?LinkId=275113](https://go.microsoft.com/fwlink/?linkid=275113) . Чтобы развернуть Mobility for Lync Server 2010, ознакомьтесь со статьей [https://go.microsoft.com/fwlink/?LinkId=275114](https://go.microsoft.com/fwlink/?linkid=275114)

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

