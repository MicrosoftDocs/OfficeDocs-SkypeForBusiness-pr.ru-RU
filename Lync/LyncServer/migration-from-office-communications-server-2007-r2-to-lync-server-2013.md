---
title: Миграция с Office Communications Server 2007 R2 на Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Office Communications Server 2007 R2 to Lync Server 2013
ms:assetid: f3fa4f5f-e9a2-4fb7-a12d-20f04173e697
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205375(v=OCS.15)
ms:contentKeyID: 48185802
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 39aef26271594ed57d113bed4c3bb3702df41fac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42148778"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>Миграция с Office Communications Server 2007 R2 на Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-19_

В подразделах этого раздела описывается процесс перехода с Office Communications Server 2007 R2 на Lync Server 2013

<div>


> [!IMPORTANT]  
> В данном документе приведены действия, которые в общем случае требуется выполнить для завершения каждого из этапов миграции, и не рассматриваются все возможные топологии устаревших развертываний или сценарии миграции. Таким образом, возможно, что в зависимости от развертывания вам не потребуется выполнять все перечисленные действия или потребуется выполнить дополнительные действия. В этом документе также содержатся примеры действий по проверке, которые помогут вам понять, на что нужно обратить внимание для успешного выполнения каждого из этапов миграции. Приведите эти действия по проверки в соответствие со своим процессом миграции.



</div>

В данном руководстве приведена информация об обновлении вашего существующего развертывания. В нем не поясняется, как изменить существующую топологию или внедрить новые возможности. При наличии описания подробной процедуры в данном руководстве указывается ссылка на соответствующий документ или его раздел.

В этом документе используются термины, указанные в следующем списке.

  - *следующего*  
    Перемещение рабочего развертывания из предыдущей версии Office Communications Server 2007 R2 на Lync Server 2013.

<!-- end list -->

  - *Обновление*  
    Установка более новой версии программного обеспечения на сервере или клиентском компьютере.

<!-- end list -->

  - *сосуществования*  
    Временная среда, существующая во время миграции, когда некоторые функции были перенесены в Lync Server 2013, и другие функции по-прежнему остаются в предыдущей версии Office Communications Server 2007 R2.

<!-- end list -->

  - *взаимодействие*  
    Способность вашего развертывания успешно работать во время периода сосуществования.

<div>

## <a name="in-this-section"></a>Содержание

  - [Перед началом миграции](before-you-begin-the-migration_1.md)

  - [Этапы миграции](migration-phases_1.md)

  - [Этап 1: Планирование миграции с Office Communications Server 2007 R2](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [Этап 2: подготовка к миграции](phase-2-prepare-for-migration_1.md)

  - [Этап 3: Развертывание пилотного пула Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [Этап 4: объединение топологий](phase-4-merge-topologies.md)

  - [Этап 5: Настройка пилотного пула](phase-5-configure-the-pilot-pool.md)

  - [Этап 6: перемещение пользователей в пилотный пул](phase-6-move-users-to-the-pilot-pool.md)

  - [Этап 7: Добавление пограничного сервера Lync Server 2013 в пилотный пул](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Этап 8: переход от пилотного развертывания к рабочей среде](phase-8-move-from-pilot-deployment-into-production.md)

  - [Этап 9: выполнение задач, выполняемых после миграции](phase-9-complete-post-migration-tasks.md)

  - [Этап 10: списание устаревшего сайта](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

