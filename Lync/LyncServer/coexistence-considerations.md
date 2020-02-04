---
title: Замечания по сосуществованию
ms.reviewer: ''
ms.author: kenwith
author: kenwith
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
ms.openlocfilehash: e53c57b90a85024ed5375129ce23c6ff0060edc4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727988"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a>Замечания по сосуществованию

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-06_

После миграции будет существовать только сервер Lync Server 2013, пул серверов сохраняемого чата, и вы можете списать устаревшее развертывание.

Перед тем как вы завершите миграцию и до того, как вы полностью намерены списать текущее развертывание сервера группового чата, вы можете использовать любое из указанных ниже развертываний.

  - Сервер Lync Server 2013, пул серверов сохраняемого чата, который должен находиться в пуле Lync Server 2013.

  - Lync Server 2010, пул группового чата, который должен быть расположен в пуле Lync Server 2010.

  - Пул группового чата Office Communications Server 2007 R2, который должен быть расположен в пуле Office Communications Server 2007 R2.

Эти развертывания могут находиться рядом друг с другом. Однако категории, комнаты и надстройки в одном развертывании не взаимодействуют с теми, которые находятся в сопутствующем развертывании.

При использовании ручного конфигурирования для Office Communications Server 2007 R2, Lync Server 2010, группового чата или Lync Server 2013 вы можете подключаться к одному пулу за один из стандартных клиентов (клиент группового чата).

Lync 2013 (клиент) может взаимодействовать только с серверным пулом Lync Server 2013, сохраняемым чат, а не с пулами серверов группового чата. Для использования сохраняемого чата в Lync 2013 (клиент) пользователь должен быть расположен в Lync 2013 и включен в соответствии с политикой.

</div>

<span> </span>

</div>

</div>

</div>

