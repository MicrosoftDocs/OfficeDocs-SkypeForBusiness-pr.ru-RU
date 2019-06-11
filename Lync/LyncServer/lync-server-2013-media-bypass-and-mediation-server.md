---
title: 'Lync Server 2013: сервер-посредник и обход сервера посредника'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8524c0f2556eec339b6698f156966ea95538dbaa
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827524"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Сервер-посредник и обход сервера посредника в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Обтекание мультимедиа — это возможность Lync Server, которая позволяет администратору настроить маршрутизацию звонков прямо между конечной точкой пользователя и шлюзом коммутируемой телефонной сети (PSTN) без обхода сервера-посредника. Обход мультимедиа улучшает качество связи, уменьшая задержку, ненужные переводы, вероятность потери пакетов и количество возможных точек сбоя. Если удаленный сайт без сервера-посредника подключен к центральному сайту по одной или нескольким ГЛОБАЛЬным каналам связи с ограниченной пропускной способностью, пропустите требования к пропускной способности, разрешив доступ к мультимедиа с клиента на удаленном сайте для непосредственного подключения к локальному шлюзу без Сначала перейдете по каналу глобальной сети на сервер-посредник на центральном сайте и обратно. Это сокращение в обработке мультимедиа также дополняет возможности сервера-посредника для управления несколькими шлюзами.

Обход сервера-посредника и контроль допуска звонков являются взаимоисключающими функциями. Если для вызова применяется обход сервера-посредника, то для него не применяется контроль допуска звонков. Предполагается, что нет никакой связи с ограниченной пропускной способностью сторон, участвующих в вызове.

<div>

## <a name="see-also"></a>См. также


[Контроль допуска звонков и сервер-посредник в Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)  


[Планирование обхода серверов-посредников в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

