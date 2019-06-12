---
title: Миграция с Lync Server 2010 на Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Migration from Lync Server 2010 to Lync Server 2013
ms:assetid: ef99d4a9-a666-4a92-9994-4d7930f70d55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205369(v=OCS.15)
ms:contentKeyID: 48185779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4be42da09e14f91d82310258c728de4ed7976be2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849006"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-lync-server-2010-to-lync-server-2013"></a>Миграция с Lync Server 2010 на Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-17_

В этом разделе приведены инструкции по переходу с Lync Server 2010 на Lync Server 2013.

<div>


> [!IMPORTANT]  
> В этом документе описаны действия, которые обычно требуются для выполнения каждого этапа миграции. Она не будет обращаться к каждой возможной топологии устаревшего развертывания или к любому из возможных сценариев миграции. Таким образом, вам может потребоваться выполнить все описанные выше действия или, возможно, потребуется выполнить дополнительные действия в зависимости от развертывания. В этом документе также приводятся примеры шагов проверки. Эти шаги проверки предназначены для того, чтобы понять, что необходимо для того, чтобы убедиться в том, что каждый этап прошел успешно по ходу миграции. Настройте эти шаги проверки в соответствии с конкретным процессом миграции.



</div>

Это руководство содержит сведения, относящиеся к обновлению существующих развертываний. В этой статье объясняется, как изменить существующую топологию. В этом руководстве не рассматриваются реализации новых функций. Подробное описание процедуры приведено в соответствующем руководстве документа или документа.

Этот документ определяет условия, указанные в приведенном ниже списке.

  - *Перемещение*  
    Перемещение рабочего развертывания из предыдущей версии Lync Server 2010 в Lync Server 2013.

<!-- end list -->

  - *Обновление*  
    Установка более новой версии программного обеспечения на сервере или клиентском компьютере.

<!-- end list -->

  - *сосуществование*  
    Временная среда, существующая во время миграции, если некоторые функциональные возможности перенесены на Lync Server 2013, а другие функции по-прежнему остаются в более ранней версии Lync Server 2010.

<!-- end list -->

  - *взаимодействия*  
    Развертывание может успешно выполняться в течение периода сосуществования.

<div>

## <a name="in-this-section"></a>Содержание

  - [Перед началом миграции](before-you-begin-the-migration.md)

  - [Этап 1: планирование перехода с Lync Server 2010](phase-1-plan-your-migration-from-lync-server-2010.md)

  - [Этап 2: подготовка к миграции](phase-2-prepare-for-migration.md)

  - [Этап 3: развертывание пула Lync Server 2013 Pilot](phase-3-deploy-lync-server-2013-pilot-pool.md)

  - [Этап 4: перемещение тестовых пользователей в пилотный пул](phase-4-move-test-users-to-the-pilot-pool.md)

  - [Этап 5: Добавление сервера Lync Server 2013 EDGE на пилотный пул](phase-5-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Этап 6: переход от пилотного развертывания к рабочей версии](phase-6-move-from-pilot-deployment-into-production.md)

  - [Этап 7: необходимые действия после миграции](phase-7-complete-post-migration-tasks.md)

  - [Этап 8: ликвидация старых пулов](phase-8-decommission-legacy-pools.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

