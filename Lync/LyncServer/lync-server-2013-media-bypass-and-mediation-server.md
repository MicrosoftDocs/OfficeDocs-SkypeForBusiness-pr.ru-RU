---
title: 'Lync Server 2013: сервер обхода сервера-посредника и сервер-посредник'
description: 'Lync Server 2013: сервер обхода сервера-посредника и сервер-посредник.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and Mediation Server
ms:assetid: 8ed35f95-05cd-4b5d-8470-442d2323df71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398719(v=OCS.15)
ms:contentKeyID: 48184774
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebb005d3d52fa9e5a38fdf56a65dfcbd73616d87
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556435"
---
# <a name="media-bypass-and-mediation-server-in-lync-server-2013"></a>Обход сервера-посредника и сервер-посредник в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Обход сервера-посредника — это возможность Lync Server, которая позволяет администратору настроить маршрутизацию вызовов для направления непосредственно между конечной точкой пользователя и шлюзом PSTN без обхода сервера-посредника. Обход сервера мультимедиа улучшает качество связи за счет сокращения задержки, ненужных преобразований, вероятности потери пакетов и количества потенциальных точек сбоя. Если удаленный сайт без сервера-посредника подключен к центральному сайту с помощью одной или нескольких каналов глобальной сети с ограниченной пропускной способностью, обход сервера-посредника понижает требования к пропускной способности, позволяя компьютеру из клиента на удаленном сайте напрямую переключаться к его локальному шлюзу без необходимости перетекать через канал WAN к серверу-посреднику на центральном сайте и обратно. Это сокращение обработки мультимедиа также дополняет возможность сервера-посредника управлять несколькими шлюзами.

Обход сервера-посредника и контроль допуска звонков являются взаимоисключающими функциями. Если для вызова применяется обход сервера-посредника, то для него не применяется контроль допуска звонков. Предполагается, что нет никакой связи с ограниченной пропускной способностью сторон, участвующих в вызове.

<div>

## <a name="see-also"></a>См. также


[Контроль допуска звонков и сервер-посредник в Lync Server 2013](lync-server-2013-call-admission-control-and-mediation-server.md)  


[Планирование обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

