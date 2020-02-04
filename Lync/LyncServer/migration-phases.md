---
title: Этапы миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 76719513d3b9df6b3259efef57fc0bd5ae94050f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-phases"></a>Этапы миграции

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-17_

В Lync Server 2013 вы определяете сайты в сети, которые содержат компоненты Lync Server 2013. Сайт — это набор компьютеров, которые надежно соединены в высокоскоростной сети с небольшой задержкой, например в локальной сети или в двух сетях, Соединенных высокоскоростной оптоволоконной одноранговой сетью.

*Пул переднего плана* — это набор серверных интерфейсов, которые настроены одинаково и работают вместе для предоставления служб для общей группы пользователей. Пул обеспечивает возможности масштабирования и отработки отказа для пользователей. Каждый сервер в пуле должен выполнять одну и ту же роль (или роли). Сервер Standard Edition, разработанный для малых организаций, также определяет пул и выполняется на одном сервере. Это позволяет использовать функциональность Lync Server 2013 для меньшей стоимости, но не предоставляет полноценное решение для высокой доступности.

Следующие этапы описывают процесс миграции пула с Lync Server 2010 на Lync Server 2013. Для нескольких сайтов с несколькими пулами каждый из них должен следовать этому поэтапному подходу.

1.  [Этап 1: планирование перехода с Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [Этап 2: подготовка к миграции](phase-2-prepare-for-migration.md)

3.  [Этап 3: развертывание пула Lync Server 2013 Pilot](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [Этап 4: перемещение тестовых пользователей в пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [Этап 5: Добавление сервера Lync Server 2013 EDGE на пилотный пул](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [Этап 6: переход от пилотного развертывания к рабочей версии](phase-6-move-from-pilot-deployment-into-production.md)

7.  [Этап 7: необходимые действия после миграции](phase-7-complete-post-migration-tasks.md)

8.  [Этап 8: ликвидация старых пулов](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

