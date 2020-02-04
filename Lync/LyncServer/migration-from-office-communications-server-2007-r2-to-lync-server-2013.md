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
ms.openlocfilehash: e32d43e8052de454647cd9f69b4572d178a0cecb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migration-from-office-communications-server-2007-r2-to-lync-server-2013"></a>Миграция с Office Communications Server 2007 R2 на Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-19_

В этом разделе приведены инструкции по переходу с Office Communications Server 2007 R2 на Lync Server 2013

<div>


> [!IMPORTANT]  
> В этом документе описаны действия, которые обычно требуются для выполнения каждого этапа миграции. Она не будет обращаться к каждой возможной топологии устаревшего развертывания или к любому из возможных сценариев миграции. Таким образом, вам может потребоваться выполнить все описанные выше действия или, возможно, потребуется выполнить дополнительные действия в зависимости от развертывания. В этом документе также приводятся примеры шагов проверки. Эти шаги проверки предназначены для того, чтобы понять, что необходимо для того, чтобы убедиться в том, что каждый этап прошел успешно по ходу миграции. Настройте эти шаги проверки в соответствии с конкретным процессом миграции.



</div>

Это руководство содержит сведения, относящиеся к обновлению существующих развертываний. В этой статье объясняется, как изменить существующую топологию. В этом руководстве не рассматриваются реализации новых функций. Подробное описание процедуры приведено в соответствующем руководстве документа или документа.

Этот документ определяет условия, указанные в приведенном ниже списке.

  - *Перемещение*  
    Перемещение рабочего развертывания из предыдущей версии Office Communications Server 2007 R2 на Lync Server 2013.

<!-- end list -->

  - *Обновление*  
    Установка более новой версии программного обеспечения на сервере или клиентском компьютере.

<!-- end list -->

  - *сосуществование*  
    Временная среда, существующая во время миграции, если некоторые функции были перенесены на Lync Server 2013, а другие функции по-прежнему остаются на ранней версии Office Communications Server 2007 R2.

<!-- end list -->

  - *взаимодействия*  
    Развертывание может успешно выполняться в течение периода сосуществования.

<div>

## <a name="in-this-section"></a>Содержание

  - [Перед началом миграции](before-you-begin-the-migration_1.md)

  - [Этапы миграции](migration-phases_1.md)

  - [Этап 1: планирование перехода с Office Communications Server 2007 R2](phase-1-plan-your-migration-from-office-communications-server-2007-r2.md)

  - [Этап 2: подготовка к миграции](phase-2-prepare-for-migration_1.md)

  - [Этап 3: развертывание пула Lync Server 2013 Pilot](phase-3-deploy-lync-server-2013-pilot-pool_1.md)

  - [Этап 4: объединение топологий](phase-4-merge-topologies.md)

  - [Этап 5: Настройка пилотного пула](phase-5-configure-the-pilot-pool.md)

  - [Этап 6: перемещение пользователей в пилотный пул](phase-6-move-users-to-the-pilot-pool.md)

  - [Этап 7: Добавление сервера Lync Server 2013 EDGE на пилотный пул](phase-7-add-lync-server-2013-edge-server-to-pilot-pool.md)

  - [Этап 8: переход с пилотного развертывания на рабочий](phase-8-move-from-pilot-deployment-into-production.md)

  - [Этап 9: завершение задач после миграции](phase-9-complete-post-migration-tasks.md)

  - [Этап 10: списание устаревшего сайта](phase-10-decommission-legacy-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

