---
title: Процесс миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba15e7fc3d190970d8c7cbc5bf7f6465286d1bc5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-process"></a>Процесс миграции

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-24_

Рекомендуемая и поддерживаемая процедура миграции для Lync Server 2013 — это процедура параллельной миграции. В этой статье описаны причины, по которым следует использовать параллельную миграцию, а также сведения о сосуществовании.

<div>

## <a name="side-by-side-migration"></a>Переход с одной стороны на другую

Почти во всех случаях миграции следует использовать путь параллельной миграции. При переходе по отдельности вы можете развернуть новый сервер с помощью Lync Server 2013 и соответствующего сервера, на котором запущен Office Communications Server 2007 R2, а затем перенести операции на новый сервер. Если вы хотите вернуться к Office Communications Server 2007 R2, вам нужно будет только перевернуть их на первоначальные серверы. Имейте в виду, что в этом случае новые собрания, запланированные на обновленных клиентах, не будут работать, а клиентам также потребуется понизить уровень.

</div>

<div>

## <a name="coexistence-testing"></a>Тестирование сосуществования

После развертывания Lync Server 2013 параллельно с Office Communications Server 2007 R2 топология представляет состояние тестирования сосуществования Lync Server 2013 и Office Communications Server 2007 R2. В этом состоянии важно проверить и убедиться, что службы запущены, можно администрировать каждый сайт, а клиенты смогут общаться с текущими и устаревшими пользователями. Прежде чем переходить от всех пользователей, очень важно понять состояние каждого развертывания и убедиться, что каждое развертывание работает и работает правильно. Как правило, этап тестирования сосуществования используется во время пилотного тестирования Lync Server 2013. Пользователи прежних версий перемещаются на Lync Server 2013 в течение определенного периода времени, чтобы обеспечить правильную работу функций и функций. После пилотной проверки пользователи и приложения перемещаются в рабочую версию Lync Server 2013, а устаревшие пулы и приложения Office Communications Server 2007 R2 будут прекращены.

</div>

</div>

<span> </span>

</div>

</div>

</div>

