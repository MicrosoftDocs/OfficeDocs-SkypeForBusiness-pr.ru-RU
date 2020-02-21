---
title: 'Lync Server 2013: Настройка расширенных 9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b8e02c81b19943baaf33ba3bb401f4810d053703
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a>Настройка расширенного 9-1-1 в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-24_

Enhanced 9-1-1 (E9-1-1) — это функция уведомления об экстренных случаях, которая связывает номер телефона вызывающего абонента с городским или почтовым адресом. Используя эти сведения, PSAP (Public Safety Answering Point) может незамедлительно направить службы экстренной помощи абоненту, находящемуся в бедственном положении.

Чтобы обеспечить поддержку E9-1-1, Lync Server 2013 должен иметь возможность правильно связать расположение с клиентом и убедиться в том, что эти сведения используются для маршрутизации экстренного вызова в ближайшее PSAP.

Сведения о планировании развертывания E9-1-1 можно найти в статье [планирование экстренных служб (E9-1-1) в Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).

<div>


> [!IMPORTANT]  
> Lync Server 2013 поддерживает только E9 – 1 – 1 в США. Чтобы развернуть E9-1-1, необходимо настроить подключение SIP к квалифицированному поставщику услуг E9-1-1 или развернуть шлюз с идентификационным номером для экстренной службы (ELIN) на основе поставщика услуг E9-1-1 на основе общедоступного коммутируемого телефона (PSTN). Дополнительные сведения: <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">расширенный 9-1-1 (E9-1-1) и сервер-посредник в Lync server 2013</A>. Дополнительные сведения о настройке магистральных соединений приведены <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">в статье Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка маршрута голосовой связи E9 – 1 – 1 в Lync Server 2013](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [Создание политик расположения в Lync Server 2013](lync-server-2013-create-location-policies.md)

  - [Настройка сведений о сайте для E9-1-1 в Lync Server 2013](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [Настройка базы данных местоположений в Lync Server 2013](lync-server-2013-configure-the-location-database.md)

  - [Настройка расширенных функций E9 – 1 – 1 в Lync Server 2013](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

