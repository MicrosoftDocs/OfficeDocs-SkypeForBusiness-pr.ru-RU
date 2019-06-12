---
title: Стандартный сценарий миграции — высокоуровневый
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Standard migration scenario - high-level
ms:assetid: e768a7ca-44e3-4969-a6d9-7ed3e7029c5c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205354(v=OCS.15)
ms:contentKeyID: 48185709
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69349b90c6845d8a3f3d5ed13544da4fe4832eb8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="standard-migration-scenario---high-level"></a>Стандартный сценарий миграции — высокоуровневый

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-01-30_

Используйте следующие элементы в качестве отправной точки при переносе Lync Server 2010, групповой чат или Office Communications Server 2007 R2 Group Chat на Lync Server 2013 и на сервер сохраняемого чата. Стандартный путь миграции Lync Server 2013 выглядит следующим образом:

  - Ваша организация ранее развернула Lync Server 2010, групповой чат или Office Communications Server 2007 R2 Group чата, и вы хотите развернуть Lync Server 2013 на сервере сохраняемого чата.

  - Разверните Lync Server 2013, а затем разверните пулы серверов сохраняемого чата.

  - Подготовьте и запланируйте миграцию сохраненных комнат чатов и определите, какое время нужно выключить систему для миграции.

  - Запустите командлеты Windows PowerShell для миграции (**Export-ксперсистентчатдата** и **Import-ксперсистентчатдата**), чтобы переместить содержимое на сохраняемый сервер чата.

  - Убедитесь, что миграция выполнена успешно.

  - Списание устаревшего развертывания.

  - Настройте сохраняемый сервер чата таким образом, чтобы устаревшие клиенты могли подключаться к Lync Server 2013, серверу сохраняемого чата. Это необходимо, так как требуется время для развертывания новых клиентов, и вы хотите разрешить существующим пользователям старых клиентов получить доступ к своим комнатам чата, как только это станет возможным.

  - Развертывайте новые клиенты, продолжая обеспечивать доступ к своим комнатам чата сотрудникам с помощью устаревшего группового чата (клиентов).

</div>

<span> </span>

</div>

</div>

</div>

