---
title: Перенос нескольких сайтов и пулов
description: Перенос нескольких сайтов и пулов.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7efaa6f038286ff9138e631f23da88bb445e20f1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543255"
---
# <a name="migrating-multiple-sites-and-pools"></a>Перенос нескольких сайтов и пулов

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-17_

Lync Server 2013 поддерживает развертывание с несколькими сайтами и несколькими пулами. Процесс переноса нескольких пулов с Lync Server 2010 на Lync Server 2013 требует следующих факторов:

1.  После развертывания пилотного пула Lync Server 2013 необходимо определить подмножество пилотных пользователей, которые будут перемещены в пул Lync Server 2013, и методологию для проверки функциональных возможностей пользователей. Например, после перемещения пользователя в пилотный пул убедитесь, что политика конференции пользователя перемещена в Lync Server 2013.

2.  После развертывания пограничного сервера в пилотном пуле необходимо убедиться, что внешние пользователи могут связываться с пулом Lync Server 2013.

3.  После переноса федеративных маршрутов с пограничных серверов Lync Server 2010 на пилотный проект Lync Server 2013 пограничные серверы необходимо проверить, что Федеративные пользователи могут связываться с пулом Lync Server 2013.

4.  После перемещения всех пользователей и объектов контактов, не являющихся пользователями, необходимо проверить, что пул Lync Server 2010 не заполнен.

5.  После проверки того, что пул Lync Server 2010 является пустым, вы можете отключить пул.
    
    Сведения об отключении устаревшего пула и серверов Lync Server 2010 приведены в статье [Этап 8: списание устаревших пулов](phase-8-decommission-legacy-pools.md).

</div>

<span> </span>

</div>

</div>

</div>

