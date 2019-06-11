---
title: 'Lync Server 2013: планирование сопоставления для пула переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0445a6d952ba7311b8f6b5435c16d9e91de587f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>Планирование сопоставления для пула переднего плана в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

Для обеспечения наилучшей возможной аварии в Lync Server 2013 разверните пары пулов переднего плана на двух географически распределенных сайтах. Каждый сайт содержит пул переднего плана, связанный с соответствующим пулом переднего плана на другом сайте. Оба сайта активны, и служба резервного копирования в Lync Server обеспечивает репликацию данных в режиме реального времени, чтобы синхронизировать их с пулами. Служба резервного копирования — это новая функция в Lync Server 2013, разработанная для поддержки решения аварийного восстановления. Он устанавливается на пул переднего плана при связывании пула с другим пулом переднего плана.

Если пул на одном из сайтов завершается сбоем, вы можете перенести пользователей из этого пула в пул на другом сайте, который предоставляет доступ к службам для всех пользователей в обоих пулах. Для планирования производственных мощностей каждый пул должен быть спроектирован таким образом, чтобы обрабатывались рабочие нагрузки всех пользователей в обоих пулах в случае аварии.

<div>

## <a name="in-this-section"></a>Содержание

  - [Поддерживаемые варианты связывания пулов и рекомендации для Lync Server 2013](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Связи с регистраторами резервного копирования в Lync Server 2013](lync-server-2013-backup-registrar-relationships.md)

  - [Время восстановления при отработке отказа пулом и восстановления пула после сбоя в Lync Server 2013](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Отработка отказа центральным хранилищем управления в Lync Server 2013](lync-server-2013-central-management-store-failover.md)

  - [Безопасность спаренных данных пула переднего плана в Lync Server 2013](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

