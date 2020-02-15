---
title: 'Lync Server 2013: Планирование обхода сервера мультимедиа'
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
ms.openlocfilehash: 0bb4d495637cd78e430e975e9831421906bfbf6e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050091"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-media-bypass-in-lync-server-2013"></a>Планирование обхода сервера мультимедиа в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Обход сервера-посредника — это устранение сервера-посредника из пути мультимедиа везде, где это возможно, для вызовов, передача сигналов которых проходит через сервер-посредник.

Обход сервера-посредника может улучшить качество звука, поскольку уменьшается задержка, потребность в преобразовании, вероятность потери пакетов и число точек вероятного сбоя. Может улучшиться масштабируемость, поскольку устранение обработки мультимедиа для вызовов с обходом сервера-посредника уменьшает нагрузку на сервер-посредник. Это сокращение нагрузки дополняет способность сервера-посредника управлять несколькими шлюзами.

Когда сайт филиала без сервера-посредника подключается к центральному сайту с помощью одной или нескольких каналов глобальной сети с ограниченной пропускной способностью, обход сервера-посредника пропонижает требования к пропускной способности, разрешая обмен данными с клиентом на сайте филиала непосредственно к локальному шлюзу без Сначала перетекает через канал WAN к серверу-посреднику на центральном сайте и обратно.

Освобождая сервер-посредник из обработки мультимедиа позволяет сократить количество серверов-посредников, необходимых для инфраструктуры корпоративной голосовой связи.

На следующем рисунке показаны основные пути мультимедиа и передачи сигналов в топологиях с обходом сервера-посредника и без такого обхода.

**Пути мультимедиа и передачи сигналов с обходом сервера-посредника и без обхода**

![Режим обхода подключений голосовой связи для передачи голоса](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Режим обхода подключений голосовой связи для передачи голоса")

Общая рекомендация состоит в том, чтобы включать обход сервера-посредника везде, где это возможно.

<div>

## <a name="in-this-section"></a>Содержание

  - [Обзор обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)

  - [Режимы обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-media-bypass-modes.md)

  - [Обход сервера мультимедиа и контроль допуска звонков в Lync Server 2013](lync-server-2013-media-bypass-and-call-admission-control.md)

  - [Технические требования для обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)

</div>

<div>

## <a name="related-sections"></a>Связанные разделы

[Развертывание расширенных функций корпоративной голосовой связи в Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка магистрали с обходом сервера мультимедиа в Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md)  


[Глобальные параметры обхода мультимедиа в Lync Server 2013](lync-server-2013-global-media-bypass-options.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

