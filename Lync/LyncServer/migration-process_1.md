---
title: Процесс миграции
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration process
ms:assetid: b2bd9c76-2f4b-4d14-a5c4-157bbff75de0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205181(v=OCS.15)
ms:contentKeyID: 48185157
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 752bd5dd75eeaf87e4fccd553d5d13da16855499
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515046"
---
# <a name="migration-process"></a>Процесс миграции

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-24_

Рекомендуемая и поддерживаемая процедура миграции для Lync Server 2013 — это параллельная процедура миграции. В этом разделе описываются причины для использования параллельной миграции и приводятся сведения о сосуществовании.

<div>

## <a name="side-by-side-migration"></a>Параллельная миграция

Почти во всех случаях следует использовать параллельную миграцию. При параллельной миграции вы развертываете новый сервер с Lync Server 2013 наряду с соответствующим сервером, на котором работает Office Communications Server 2007 R2, а затем переносите операции на новый сервер. Если потребуется выполнить откат к серверу Office Communications Server 2007 R2, только переместит операции обратно на исходные серверы. Имейте в виду, что в этом случае проведение новых собраний, запланированных с помощью обновленных клиентов, будет невозможно, и клиенты также потребуется откатить до предыдущей версии.

</div>

<div>

## <a name="coexistence-testing"></a>Тестирование сосуществования

После развертывания Lync Server 2013 параллельно с Office Communications Server 2007 R2 топология представляет состояние тестирования сосуществования Lync Server 2013 и Office Communications Server 2007 R2. Пока топология находится в этом состоянии, необходимо убедиться в том, что службы запускаются, все сайты доступны для администрирования и клиенты обеспечивают взаимодействие как с новыми, так и со старыми пользователями. Перед миграцией всех пользователей крайне важно оценить состояние каждого развертывания и убедиться в его работоспособности. Как правило, этап тестирования сосуществования существует во время пилотного тестирования Lync Server 2013. Устаревшие пользователи перемещаются в Lync Server 2013 в течение определенного периода времени, чтобы обеспечить правильную работу совместимости и функций и функций приложений. После пилотного тестирования пользователи и приложения переносятся в рабочую версию Lync Server 2013, а устаревшие пулы и приложения Office Communications Server 2007 R2 будут отменены.

</div>

</div>

<span> </span>

</div>

</div>

</div>

