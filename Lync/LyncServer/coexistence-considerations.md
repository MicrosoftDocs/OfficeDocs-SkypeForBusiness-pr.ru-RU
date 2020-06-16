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
ms.openlocfilehash: a7052042afbc3927e1047a9c2fbb30a71168f317
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>Рекомендации по сосуществованию

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

These deployments can exist side by side. However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.

При использовании ручной настройки клиент для Office Communications Server 2007 R2, Lync Server 2010, Group Chat или Lync Server 2013 может подключаться к одному пулу за раз.

Lync 2013 (клиент) может взаимодействовать только с пулом серверов Lync Server 2013, persistent Chat, а не с устаревшими пулами серверов группового чата. Чтобы использовать сохраняемый чат в Lync 2013 (клиент), пользователь должен быть размещен в Lync 2013 и включен в соответствии с политикой.

</div>

<span> </span>

</div>

</div>

</div>

