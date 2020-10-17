---
title: Рекомендации по сосуществованию
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdad93eaf8debbc616099c1454d5e39438a63474
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499676"
---
# <a name="coexistence-considerations"></a>Рекомендации по сосуществованию

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-06_

После миграции будет существовать только сервер Lync Server 2013, пул серверов сохраняемого чата, и вы можете списать устаревшее развертывание.

Перед завершением миграции и полным списанием текущего развертывания сервера группового чата вы можете использовать любое из следующих развертываний:

  - Lync Server 2013, пул серверов сохраняемого чата, который должен быть размещен в пуле Lync Server 2013.

  - Lync Server 2010, пул группового чата, который должен быть размещен в пуле Lync Server 2010.

  - Пул группового чата Office Communications Server 2007 R2, который должен быть размещен в пуле Office Communications Server 2007 R2.

Эти развертывания могут существовать параллельно, но категории, комнаты и надстройки в разных развертываниях не могут взаимодействовать между собой.

При использовании ручной настройки клиент для Office Communications Server 2007 R2, Lync Server 2010, Group Chat или Lync Server 2013 может подключаться к одному пулу за раз.

Lync 2013 (клиент) может взаимодействовать только с пулом серверов Lync Server 2013, persistent Chat, а не с устаревшими пулами серверов группового чата. Чтобы использовать сохраняемый чат в Lync 2013 (клиент), пользователь должен быть размещен в Lync 2013 и включен в соответствии с политикой.

</div>

<span> </span>

</div>

</div>

</div>

