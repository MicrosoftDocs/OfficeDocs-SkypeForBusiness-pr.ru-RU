---
title: Проверка возможности совместного использования пилотного и старого пула
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe3b3e04940c90cba4e46fc165c2494f77105667
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Проверка возможности совместного использования пилотного и старого пула

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-29_

После развертывания пилотного пула необходимо проверить сосуществование двух пулов с помощью средств администрирования для просмотра сведений о пуле. Для пулов и стандартных пулов Lync Server 2013 необходимо использовать инструменты панели управления и Topology Builder сервера Lync Server 2013.

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a>Проверка того, что службы Lync Server 2013 запущены

1.  На сервере Lync Server 2013 с интерфейсом front end перейдите к апплету\\администрирование служб.

2.  Убедитесь в том, что на сервере переднего плана запущены следующие службы:

**Lync Server 2013 Services**

![Список запущенных служб Lync Server](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Список запущенных служб Lync Server")

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a>Открытие панели управления Lync Server 2013

На сервере переднего плана в среде Lync Server 2013 откройте панель управления Lync Server 2013 и выберите пул Lync Server 2010. Повторите процедуру, чтобы открыть пул Lync Server 2013.

**Открытие панели управления Lync Server 2013**

![Диалоговое окно "Выбор URL-адреса"](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Диалоговое окно "Выбор URL-адреса"")

<div>


> [!IMPORTANT]  
> На Lync Server 2013 необходимо обновить Silverlight до Silverlight версии 5, прежде чем использовать панель управления Lync Server.



</div>

Теперь эта топология включает в себя серверные роли Lync Server 2010 и Lync Server 2013.

**Страница топологии панели управления Lync Server 2013**

![Страница топологии на панели управления сервера Lync Server](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Страница топологии на панели управления сервера Lync Server")

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a>Не пытайтесь открыть топологию в Lync Server 2010 Topology Builder

Если вы попытаетесь открыть топологию с помощью Lync Server 2010 Topology Builder, вам появятся описанные ниже ошибки. Топологию можно просмотреть только с помощью построителя Lync Server 2013 Topology. Для создания пулов как для Lync Server 2013, так и для Lync Server 2010 необходимо использовать строитель топологии Lync Server 2013.

**Сообщение об ошибке в Lync Server 2010 Topology Builder**

![Ошибка привязки консоли управления "Построитель топологии Lync Server"](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Ошибка привязки консоли управления "Построитель топологии Lync Server"")

</div>

</div>

<span> </span>

</div>

</div>

</div>

