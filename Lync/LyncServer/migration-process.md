---
title: Процесс миграции
description: Процесс миграции.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: 13d71f4b-9d5e-4ea3-9e93-29fdad7ac68f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204696(v=OCS.15)
ms:contentKeyID: 48183474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f363bd79a3d3be709d731d2ca4bffb4f83fe89ea
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569565"
---
# <a name="migration-process"></a>Процесс миграции

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-17_

Рекомендуемая и поддерживаемая процедура миграции для Lync Server 2013 — параллельная миграция. В этом разделе описывается, почему следует использовать параллельную миграцию, а также сведения о тестировании сосуществования.

<div>

## <a name="side-by-side-migration"></a>Параллельная миграция

Почти во всех случаях следует использовать параллельную миграцию. При параллельной миграции вы развертываете новый сервер с Lync Server 2013 наряду с соответствующим сервером, на котором работает Lync Server 2010, а затем перенесите операции на новый сервер. Если потребуется выполнить откат к Lync Server 2010, только переместит операции на исходные серверы. Имейте в виду, что в этом случае проведение новых собраний, запланированных с помощью обновленных клиентов, будет невозможно, и клиенты также потребуется откатить до предыдущей версии.

</div>

<div>

## <a name="coexistence-testing"></a>Тестирование сосуществования

После развертывания Lync Server 2013 параллельно с Lync Server 2010 развертывание представляет состояние тестирования сосуществования Lync Server 2013 и Lync Server 2010. В этом состоянии важно проверить и убедиться, что службы запущены, можно администрировать каждый сайт, а клиенты могут общаться с текущими и устаревшими пользователями. Перед миграцией всех пользователей крайне важно оценить состояние каждого развертывания и убедиться в его работоспособности. Как правило, этап тестирования сосуществования существует во время пилотного тестирования Lync Server 2013. Устаревшие пользователи перемещаются в Lync Server 2013 в течение определенного периода времени, чтобы обеспечить правильную работу совместимости и функций и функций приложений. После пилотного тестирования пользователи и приложения перемещаются в рабочую версию Lync Server 2013, а устаревшие пулы и приложения Lync Server 2010 будут отменены.

</div>

</div>

<span> </span>

</div>

</div>

</div>

