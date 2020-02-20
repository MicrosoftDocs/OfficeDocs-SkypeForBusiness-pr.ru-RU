---
title: Lync Server 2013 поддерживаемые варианты связывания пула и рекомендации
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported pool pairing options and best practices
ms:assetid: 142caf34-0f20-47f3-9d32-ce25ab622fad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204697(v=OCS.15)
ms:contentKeyID: 48183478
ms.date: 03/09/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c73108f832aaa10b0539aa6fd56b4f4a7bb0cbb1
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42142385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="supported-pool-pairing-options-and-best-practices-for-lync-server-2013"></a>Поддерживаемые варианты связывания пулов и рекомендации для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2017-03-09_

Не существует ограничений на расстояние между двумя центрами обработки данных, которые включают в себя межсерверные пулы, связанные друг с другом. Мы рекомендуем использовать два центра обработки данных в одном регионе мира с высокоскоростными связями между ними. Лучше всего, если два центра обработки данных достаточно отделены друг от друга, чтобы избежать одиночной аварии одновременно.

Наличие двух центров обработки данных в регионах мира возможно, но это может привести к более высокому снижению потери данных из-за задержки в репликации данных.

При планировании того, какие пулы необходимо связать, необходимо учитывать, что поддерживаются только следующие значения:

  - Пулы корпоративных выпусков можно связать только с другими пулами Enterprise Edition. Аналогично, пулы Standard Edition можно связать только с другими пулами Standard Edition.

  - Физические пулы можно связать только с другими физическими пулами. Аналогично виртуальные пулы можно связать только с другими виртуальными пулами.

  - Пулы, Объединенные вместе, должны работать под управлением одной и той же операционной системы.

Ни построитель топологий, ни проверка топологии не будут иметь возможность связывания двух пулов без соблюдения этих рекомендаций. Например, построитель топологий позволяет связать пул Enterprise Edition с пулом Standard Edition. Однако эти типы связей не поддерживаются.

Каждый пул в каждой из них должен иметь емкость для обслуживания всех пользователей из обоих пулов в случае аварии.

Если вы объединяете пулы Enterprise Edition, вы также можете реализовать высокую доступность на внутренних серверах, но для пар пулов Standard Edition доступны только меры аварийного восстановления.

</div>

<span> </span>

</div>

</div>

</div>

