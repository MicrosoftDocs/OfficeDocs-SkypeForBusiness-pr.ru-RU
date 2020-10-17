---
title: Стандартный сценарий миграции — высокий уровень
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 62a557d8b5a0f2a3e1e0f248b01795e75c02b3a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529806"
---
# <a name="standard-migration-scenario---high-level"></a>Стандартный сценарий миграции — высокий уровень

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-30_

Используйте следующие элементы в качестве отправной точки при переносе Lync Server 2010, группового чата или Office Communications Server 2007 R2 на Lync Server 2013, сервер сохраняемого чата. Стандартный путь миграции Lync Server 2013 выглядит следующим образом:

  - В Организации ранее было развернуто Lync Server 2010, Group Chat или Office Communications Server 2007 R2 Group Chat, и вы хотите развернуть Lync Server 2013, сервер сохраняемого чата.

  - Разверните Lync Server 2013, а затем разверните пул серверов сохраняемого чата.

  - Подготовьте и запланируйте миграцию комнат сохраняемого чата и определите время, необходимое для завершения миграции системы.

  - Выполните командлеты Windows PowerShell для миграции (**Export-CsPersistentChatData** и **Import-CsPersistentChatData**), чтобы переместить контент на сервер сохраняемого чата.

  - Убедитесь, что перенос прошел успешно.

  - Выведите из эксплуатации устаревшее развертывание.

  - Настройте сервер сохраняемого чата, чтобы устаревшие клиенты могли подключаться к серверу сохраняемого чата в Lync Server 2013. Это необходимо, так как для развертывания новых клиентов нужно время, а вам нужно предоставить текущим пользователям с устаревшими клиентами доступ к комнатам чата как можно быстрее.

  - Развертывайте новые клиенты, не отключаясь, чтобы сотрудники со старым сеансом группы (клиенты) могли попасть в комнаты чата.

</div>

<span> </span>

</div>

</div>

</div>

