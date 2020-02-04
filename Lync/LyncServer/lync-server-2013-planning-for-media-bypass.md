---
title: 'Lync Server 2013: планирование обхода серверов-посредников'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for media bypass
ms:assetid: 8ac732b6-8538-4d7b-b1a9-2035e419dac2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398703(v=OCS.15)
ms:contentKeyID: 48184768
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97b28559ea58439d370042d54ab7ef58943bc594
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41751159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a>Планирование обхода серверов-посредников в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Обойтись обозначает удаление сервера обновлений из пути к носителю, если это возможно, для звонков, сигнализация которых проходит на сервер обновлений.

Media bypass can improve voice quality by reducing latency, needless translation, possibility of packet loss, and the number of points of potential failure. Масштабируемость может быть улучшена, так как при отключении обработки мультимедиа для обходных вызовов уменьшается нагрузка на сервер-посредник. Благодаря этому снижению нагрузки сервер может управлять несколькими шлюзами.

Если сайт филиала без сервера-посредника подключен к центральному сайту по одной или нескольким ГЛОБАЛЬным каналам связи с ограниченной пропускной способностью, пропустите требования к пропускной способности, разрешая доступ к мультимедиа от клиента на сайте филиала для передачи данных непосредственно локальному шлюзу без Сначала перейдете по каналу глобальной сети на сервер-посредник на центральном сайте и обратно.

Вырелиевинг сервер из обработки мультимедийных сообщений, вы также можете уменьшить количество серверов, которые потребуются при работе с корпоративной голосовой сетью.

На следующем рисунке показаны основные пути мультимедиа и передачи сигналов в топологиях с обходом сервера-посредника и без такого обхода.

**Пути передачи мультимедийных данных и сигналов при включенном и отключенном режиме обхода сервера-посредника**

![Голосовой контроль допуска звонков — обход мультимедиа при принудительном подключении](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Голосовой контроль допуска звонков — обход мультимедиа при принудительном подключении")

Общая рекомендация состоит в том, чтобы включать обход сервера-посредника везде, где это возможно.

<div>

## <a name="in-this-section"></a>Содержание

  - [Общие сведения об обходном пропуске мультимедиа в Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)

  - [Режимы обхода сервера-посредника в Lync Server 2013](lync-server-2013-media-bypass-modes.md)

  - [Обход сервера-посредника и контроль допуска звонков в Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Технические требования для сервера-посредника в Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>Связанные разделы

[Развертывание улучшенных функций голосовой связи в Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Глобальные параметры обхода мультимедиа в Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

