---
title: Этапы миграции
description: Этапы миграции.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migration phases
ms:assetid: cb7747ba-b872-42ca-ab41-76e3c4e77d06
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205336(v=OCS.15)
ms:contentKeyID: 48185642
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 72ef47cb9b6c9eba75c395eb9bd94c887ca5a433
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547055"
---
# <a name="migration-phases"></a>Этапы миграции

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-17_

В Lync Server 2013 вы определяете сайты в сети, содержащие компоненты Lync Server 2013. Сайт — это набор компьютеров, которые подключены к высокоскоростной сети с небольшой задержкой, например к одной локальной сети (LAN), или две сети, соединенные высокоскоростной оптоволоконной сетью.

*Интерфейсный пул* — это набор серверов переднего плана, настроенных одинаково и совместно работающих для предоставления служб для общей группы пользователей. Пул обеспечивает масштабируемость и возможность отработки отказа для пользователей. Каждый сервер в пуле должен содержать идентичные роли сервера. Сервер Standard Edition, предназначенный для малых организаций, также определяет пул и выполняется на отдельном сервере. Это позволяет использовать функциональность Lync Server 2013 для уменьшения затрат, но не предоставляет полноценное решение для высокой доступности.

На следующих этапах описывается процесс миграции пула с Lync Server 2010 на Lync Server 2013. Для нескольких сайтов, содержащих несколько пулов, каждый пул должен соответствовать этому поэтапному подходу.

1.  [Этап 1: Планирование миграции с Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

2.  [Этап 2: подготовка к миграции](phase-2-prepare-for-migration.md)

3.  [Этап 3: Развертывание пилотного пула Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

4.  [Этап 4: перемещение тестовых пользователей в пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md)

5.  [Этап 5: Добавление пограничного сервера Lync Server 2013 в пилотный пул](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

6.  [Этап 6: переход от пилотного развертывания к рабочей версии](phase-6-move-from-pilot-deployment-into-production.md)

7.  [Этап 7: необходимые действия после миграции](phase-7-complete-post-migration-tasks.md)

8.  [Этап 8: ликвидация старых пулов](phase-8-decommission-legacy-pools.md)

</div>

<span> </span>

</div>

</div>

</div>

