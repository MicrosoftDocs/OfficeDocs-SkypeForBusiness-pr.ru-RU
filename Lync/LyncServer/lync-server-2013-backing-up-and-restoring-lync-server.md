---
title: 'Lync Server 2013: резервное копирование и восстановление сервера Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6947035af0021090596348b1aab873c60b930e00
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532736"
---
# <a name="backing-up-and-restoring-lync-server-2013"></a>Резервное копирование и восстановление Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

В этом разделе вы найдете рекомендации по резервному копированию данных Lync Server 2013 и их восстановлению в случае сбоя. Эти рекомендации применимы к следующим ситуациям:

  - Весь пул Lync Server любого типа (сервер переднего плана, пограничный сервер, сервер-посредник, сервер сохраняемого чата или директор) или отдельный сервер в одном из этих пулов.

  - Центральный сервер управления

  - Сервер Standard Edition

  - Сервер переднего план выпуска Enterprise Edition

  - Хранилище файлов

  - База данных архивации, база данных мониторинга или база данных сохраняемого чата

В этом разделе не представлены сведения о восстановлении всего сайта или для разработки резервного сайта. Подробные сведения о разработке решения аварийного восстановления с подключенными интерфейсными пулами приведены [в статье Планирование обеспечения высокой доступности и аварийного восстановления в Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md). Это рекомендуемый способ планирования аварийного восстановления.

Если вы развернули связанные пулы переднего плана, если один из этих пулов отказывается и становится невосстанавливаемым, можно восстановить пул с новым полным доменным именем (FQDN) из соответствующего пула. Подробные сведения о действиях, выполняемых для выполнения этого восстановления, приведены в разделе Failing of The Pool of the [Lync Server 2013](lync-server-2013-failing-over-a-pool.md). Кроме того, если позднее потребуется повторно создать неисправной и невосстанавливаемый пул, который являлся частью многосерверной связи, можно выполнить действия, описанные в статье [выполнение отработки отказа для пула переднего плана ABC в Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).

В методологии, описанной в этом документе, используются особые рекомендации на этапе планирования. Сведения о [создании плана резервного копирования и восстановления для Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).

<div>

## <a name="in-this-section"></a>Содержание

  - [Подготовка к резервному копированию и восстановлению Lync Server 2013](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [Резервное копирование данных и параметров в Lync Server 2013](lync-server-2013-backing-up-data-and-settings.md)

  - [Восстановление данных и параметров в Lync Server 2013](lync-server-2013-restoring-data-and-settings.md)

  - [Таблицы резервного копирования и восстановления для Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

