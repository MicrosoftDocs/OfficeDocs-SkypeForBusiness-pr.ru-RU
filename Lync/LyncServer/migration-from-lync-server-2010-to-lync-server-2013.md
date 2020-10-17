---
title: Миграция с Lync Server 2010 на Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89bc70635ac941398a71515e77dd1a792973fc35
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527306"
---
# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>Миграция с Lync Server 2010 на Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-17_

В подразделах этого раздела описывается процесс перехода с Lync Server 2010 на Lync Server 2013.

<div>


> [!IMPORTANT]  
> В данном документе приведены действия, которые в общем случае требуется выполнить для завершения каждого из этапов миграции, и не рассматриваются все возможные топологии устаревших развертываний или сценарии миграции. Таким образом, возможно, что в зависимости от развертывания вам не потребуется выполнять все перечисленные действия или потребуется выполнить дополнительные действия. В этом документе также содержатся примеры действий по проверке, которые помогут вам понять, на что нужно обратить внимание для успешного выполнения каждого из этапов миграции. Приведите эти действия по проверки в соответствие со своим процессом миграции.



</div>

В данном руководстве приведена информация об обновлении вашего существующего развертывания. В нем не поясняется, как изменить существующую топологию или внедрить новые возможности. При наличии описания подробной процедуры в данном руководстве указывается ссылка на соответствующий документ или его раздел.

В этом документе используются термины, указанные в следующем списке.

  - *следующего*  
    Перемещение рабочего развертывания из предыдущей версии Lync Server 2010 на Lync Server 2013.

<!-- end list -->

  - *Обновление*  
    Установка более новой версии программного обеспечения на сервере или клиентском компьютере.

<!-- end list -->

  - *сосуществования*  
    Временная среда, существующая во время миграции, когда некоторые функции были перенесены в Lync Server 2013, и другие функции по-прежнему остаются в предыдущей версии Lync Server 2010.

<!-- end list -->

  - *взаимодействие*  
    Способность вашего развертывания успешно работать во время периода сосуществования.

<div>

## <a name="in-this-section"></a>Содержание

  - [Перед началом миграции](before-you-begin-the-migration.md)

  - [Этап 1: Планирование миграции с Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [Этап 2: подготовка к миграции](phase-2-prepare-for-migration.md)

  - [Этап 3: Развертывание пилотного пула Lync Server 2013](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Этап 4: перемещение тестовых пользователей в пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md)

  - [Этап 5: Добавление пограничного сервера Lync Server 2013 в пилотный пул](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Этап 6: переход от пилотного развертывания к рабочей версии](phase-6-move-from-pilot-deployment-into-production.md)

  - [Этап 7: необходимые действия после миграции](phase-7-complete-post-migration-tasks.md)

  - [Этап 8: ликвидация старых пулов](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

