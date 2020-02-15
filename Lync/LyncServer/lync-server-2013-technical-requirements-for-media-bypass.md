---
title: 'Lync Server 2013: технические требования для обхода сервера мультимедиа'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for media bypass
ms:assetid: 6162a204-0e7c-460a-8eb2-e592c6590a8a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398435(v=OCS.15)
ms:contentKeyID: 48184321
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b962905870287ef6765ecb6e7ee9b3e321ac6a8e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028410"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-media-bypass-in-lync-server-2013"></a>Технические требования для обхода сервера мультимедиа в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Для каждого вызова PSTN сервер-посредник определяет, может ли носитель из исходной конечной точки Lync быть отправлен непосредственно на узел сервера-посредника без обхода сервера-посредника. Узлом партнера может являться шлюз ТСОП, УАТС или пограничный контроллер поставщика услуг интернет-телефонии (ITSP), связанного с магистральной линией между сервером-посредником, где маршрутизируется вызов.

Обход сервера-посредника можно использовать, если удовлетворены следующие требования:

  - Узел сервера-посредника должен поддерживать необходимые возможности для обхода сервера-посредника, наиболее важным является возможность обработки нескольких разветвленных ответов (называемых ранними диалоговыми средствами). Обратитесь к производителю шлюза или ITSP, чтобы получить значение максимального количества ранних диалогов, которые могут поддерживать шлюз, PBX или SBC

  - Узел сервера-посредника должен принимать трафик мультимедиа непосредственно из конечных точек Lync. Многие Итспс позволяют их SBC получать трафик только от сервера-посредника. Обратитесь к ITSP, чтобы определить, принимает ли его SBC трафик мультимедиа непосредственно из конечных точек Lync.

  - Клиенты Lync и одноранговые серверы-посредники должны быть хорошо подключены, то есть они размещаются в одном регионе сети или на сетевых сайтах, подключающихся к регионам по каналам глобальной сети, не имеющим ограничений пропускной способности.

<div>

## <a name="see-also"></a>См. также


[Режимы обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Обход сервера мультимедиа и контроль допуска звонков в Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

