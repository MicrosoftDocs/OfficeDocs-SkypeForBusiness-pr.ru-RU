---
title: Перенос нескольких сайтов и пулов
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205165(v=OCS.15)
ms:contentKeyID: 48185079
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2f01303c7fe137253d8e993edb05e9562d963ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765257"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Перенос нескольких сайтов и пулов

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-17_

Lync Server 2013 поддерживает развертывание с несколькими сайтами и несколькими пулами. Процесс миграции нескольких пулов с Lync Server 2010 на Lync Server 2013 требует указанных ниже факторов.

1.  После развертывания пула Lync Server 2013 Pilot вы должны определить подмножество пользователей пилотной версии, которые будут перенесены в пул Lync Server 2013, и методологию для проверки функциональных возможностей пользователей. Например, после перемещения пользователя в пилотный пул убедитесь, что политика конференции пользователя перешла на Lync Server 2013.

2.  После развертывания пограничного сервера в пилотном пуле необходимо проверить, могут и внешние пользователи взаимодействовать с пулом Lync Server 2013.

3.  После перевода федеративных маршрутов с сервера Lync Server 2010 EDGE на пробную подложку Lync Server 2013 Edges необходимо проверить, что Федеративные пользователи смогут взаимодействовать с пулом Lync Server 2013.

4.  После перемещения всех пользователей и объектов контактных лиц, не являющихся пользователями, необходимо проверить, что пул Lync Server 2010 пуст.

5.  После того как вы убедитесь в том, что пул Lync Server 2010 пуст, вы можете деактивировать пул.
    
    Подробнее об отключении устаревшего пула и серверов Lync Server 2010 вы можете найти в разделе [Этап 8: списание стандартных пулов](phase-8-decommission-legacy-pools.md).

</div>

<span> </span>

</div>

</div>

</div>

