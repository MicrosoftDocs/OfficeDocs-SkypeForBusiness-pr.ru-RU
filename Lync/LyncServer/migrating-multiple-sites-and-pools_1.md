---
title: Перенос нескольких сайтов и пулов
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating multiple sites and pools
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49733615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 71ff9164dcd824d6b836577b04783954cb81b067
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Перенос нескольких сайтов и пулов

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-08-26_

Lync Server 2013 поддерживает развертывание с несколькими сайтами и несколькими пулами. Процесс миграции нескольких пулов из Office Communications Server 2007 R2 на Lync Server 2013 требует указанных ниже факторов.

1.  После развертывания пула Lync Server 2013 Pilot вы должны определить подмножество пользователей пилотной версии, которые будут перенесены в пул Lync Server 2013, и методологию для проверки функциональных возможностей пользователей.

2.  После развертывания пограничного сервера в пилотном пуле необходимо проверить, могут и внешние пользователи взаимодействовать с пулом Lync Server 2013.

3.  После перевода федеративных маршрутов с Office Communications Server 2007 R2 Edge Server на пробный проект Lync Server 2013 пограничные серверы, вам нужно подтвердить, что Федеративные пользователи смогут взаимодействовать с пулом Lync Server 2013.

4.  После перемещения всех пользователей и объектов контактов, не являющихся пользователями, нужно проверить, что пул Office Communications Server 2007 R2 пуст.

5.  После того как вы убедитесь в том, что пул Office Communications Server 2007 R2 пуст, вы можете деактивировать пул.
    
    Подробнее об отключении устаревшего пула и серверов Office Communications Server 2007 R2 вы можете найти в статье [этап 10: списание устаревшего сайта](phase-10-decommission-legacy-site.md).

</div>

<span> </span>

</div>

</div>

</div>

