---
title: 'Lync Server 2013: планирование связывания пула переднего плана'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4daeb3ea88570afaf9fc90c0e252466be67ed192
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036779"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a>Планирование связывания пула переднего плана в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Для достижения наилучших возможностей аварийного восстановления в Lync Server 2013 разверните пары интерфейсных пулов на двух географически распределенных сайтах. Каждый из них должен содержать интерфейсный пул, сопряженный с соответствующим интерфейсным пулом в другом узле. Оба сайта активны, а служба резервного копирования Lync Server обеспечивает репликацию данных в режиме реального времени для синхронизации пулов. Служба резервного копирования — это новая функция в Lync Server 2013, предназначенная для поддержки решения по аварийному восстановлению. Она устанавливается в интерфейсном пуле при соединении его с другим интерфейсным пулом.

Если пул в одном узле становится недоступным, вы можете перевести пользователей из этого пула в другой пул в другом узле, который предоставляет услуги для всех пользователей в обоих пулах. Для планирования емкости каждый пул должен проектироваться таким образом, чтобы обрабатывать рабочие нагрузки всех пользователей в обоих пулах в случае аварии.

<div>

## <a name="in-this-section"></a>Содержание

  - [Поддерживаемые варианты связывания пулов и рекомендации для Lync Server 2013](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [Связи регистратора резервного копирования в Lync Server 2013](lync-server-2013-backup-registrar-relationships.md)

  - [Время восстановления для отработки отказа пула и восстановления размещения пула в Lync Server 2013](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [Отработка отказа центрального хранилища управления в Lync Server 2013](lync-server-2013-central-management-store-failover.md)

  - [Безопасность данных связывания пула переднего плана в Lync Server 2013](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

