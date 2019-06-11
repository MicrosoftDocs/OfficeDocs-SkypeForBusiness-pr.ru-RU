---
title: 'Lync Server 2013: настройка службы Enhanced 9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure Enhanced 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398390(v=OCS.15)
ms:contentKeyID: 48184205
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0ef94e3de028f66684972fa6a3c95d4e63c35b5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-enhanced-9-1-1-in-lync-server-2013"></a>Настройка службы Enhanced 9-1-1 в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-24_

Enhanced 9-1-1 (E9-1-1) – это функция уведомления об экстренных случаях, которая связывает номер телефона вызывающего абонента с городским или почтовым адресом. Используя эти сведения, PSAP (Public Safety Answering Point) может незамедлительно направить службы экстренной помощи абоненту, находящемуся в бедственном положении.

Для поддержки E9-1-1 в Lync Server 2013 необходимо правильно связать расположение с клиентом и удостовериться, что эта информация используется для направления вызова экстренной помощи на ближайшее ПСАП.

Для получения подробной информации о планировании развертывания E9-1-1, ознакомьтесь со статьей [Планирование служб экстренной помощи (E9-1-1) в Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).

<div>


> [!IMPORTANT]  
> Lync Server 2013 поддерживает только E9-1-1 в США. Чтобы развернуть E9-1-1, вам нужно настроить подключение по протоколу SIP к квалифицированному поставщику услуг E9-1 или развернуть идентификационный номер места для экстренной помощи (Елин) для поставщика услуг с общедоступным коммутируемым телефонным подключением (Wi-Fi-1). Подробные сведения можно найти <A href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">в разделе улучшенный 9-1-1 (E9-1-1) и сервер-посредник в Lync server 2013</A>. Дополнительные сведения о настройке подключения к магистрали можно найти <A href="lync-server-2013-configure-a-trunk-with-media-bypass.md">в разделе Настройка магистрали с помощью мультимедийного обхода в Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка маршрута голосовой связи E9-1-1 в Lync Server 2013](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [Создание политик местоположений в Lync Server 2013](lync-server-2013-create-location-policies.md)

  - [Настройка сведений о сайте для E9-1-1 в Lync Server 2013](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [Configure the location database in Lync Server 2013](lync-server-2013-configure-the-location-database.md)

  - [Настройка расширенных возможностей E9-1-1 в Lync Server 2013](lync-server-2013-configure-advanced-e9-1-1-features.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

