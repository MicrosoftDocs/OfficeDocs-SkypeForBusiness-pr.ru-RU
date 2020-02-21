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
ms.openlocfilehash: 9ed975a35c49bc5379a5cc2daf22bda729cbceee
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42190032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-multiple-sites-and-pools"></a>Перенос нескольких сайтов и пулов

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-08-26_

Lync Server 2013 поддерживает развертывание с несколькими сайтами и несколькими пулами. Процесс переноса нескольких пулов из Office Communications Server 2007 R2 на Lync Server 2013 требует следующих факторов:

1.  После развертывания пилотного пула Lync Server 2013 необходимо определить подмножество пилотных пользователей, которые будут перемещены в пул Lync Server 2013, и методологию для проверки функциональных возможностей пользователей.

2.  После развертывания пограничного сервера в пилотном пуле необходимо убедиться, что внешние пользователи могут связываться с пулом Lync Server 2013.

3.  После переноса федеративных маршрутов с пограничных серверов Office Communications Server 2007 R2 на пилотный проект Lync Server 2013 пограничные серверы необходимо убедиться, что Федеративные пользователи могут связываться с пулом Lync Server 2013.

4.  После перемещения всех пользователей и объектов контактов, не являющихся пользователями, необходимо убедиться в том, что пул Office Communications Server 2007 R2 пуст.

5.  После проверки того, что пул Office Communications Server 2007 R2 пуст, вы можете отключить пул.
    
    Дополнительные сведения об отключении устаревшего пула и серверов Office Communications Server 2007 R2 приведены в статье [этап 10: списание устаревшего сайта](phase-10-decommission-legacy-site.md).

</div>

<span> </span>

</div>

</div>

</div>

