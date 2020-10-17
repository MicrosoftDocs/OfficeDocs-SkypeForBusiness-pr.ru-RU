---
title: Проверка возможности совместного использования пилотного и старого пула
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205420(v=OCS.15)
ms:contentKeyID: 48185964
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8958fbf22e096a1d9fef03afd3aac3b4656ed0e8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515936"
---
# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Проверка возможности совместного использования пилотного и старого пула

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-29_

После развертывания пилотного пула вам требуется проверить сосуществование двух пулов, воспользовавшись средствами администрирования для просмотра информации о пуле. Для пулов Lync Server 2013 и устаревших пулов необходимо использовать инструменты панели управления Lync Server 2013 и построитель топологий.

<div>

## <a name="verify-that-lync-server-2013-services-have-started"></a>Проверка того, что службы Lync Server 2013 запущены

1.  На сервере переднего плана Lync Server 2013 перейдите к компоненту "Администрирование \\ служб".

2.  Убедитесь, что на сервере переднего плана запущены следующие службы:

**Службы Lync Server 2013**

![Список запущенных служб Lync Server](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "Список запущенных служб Lync Server")

</div>

<div>

## <a name="open-the-lync-server-2013-control-panel"></a>Открытие панели управления Lync Server 2013

На сервере переднего плана в развертывании Lync Server 2013 откройте панель управления Lync Server 2013 и выберите пул Lync Server 2010. Повторите процедуру, чтобы открыть пул Lync Server 2013.

**Открытие панели управления Lync Server 2013**

![Диалоговое окно "Выбор URL-адреса"](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "Диалоговое окно "Выбор URL-адреса"")

<div>


> [!IMPORTANT]  
> В Lync Server 2013 необходимо обновить Silverlight до Silverlight версии 5, прежде чем использовать панель управления Lync Server.



</div>

Эта топология теперь включает роли сервера Lync Server 2010 и Lync Server 2013.

**Страница топологии в панели управления Lync Server 2013**

![Панель управления Lync Server — страница топологии](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Панель управления Lync Server — страница топологии")

</div>

<div>

## <a name="dont-attempt-to-open-the-topology-in-lync-server-2010-topology-builder"></a>Не пытайтесь открыть топологию в построителе топологий Lync Server 2010

При попытке открыть топологию с помощью построителя топологий Lync Server 2010 вы увидите следующее сообщение об ошибке. Топологию можно просмотреть только с помощью построителя топологий Lync Server 2013. Для создания пулов для Lync Server 2013 и Lync Server 2010 необходимо использовать построитель топологий Lync Server 2013.

**Сообщение об ошибке в построителе топологий Lync Server 2010**

![Ошибка привязки консоли управления "Построитель топологий Lync Server"](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Ошибка привязки консоли управления "Построитель топологий Lync Server"")

</div>

</div>

<span> </span>

</div>

</div>

</div>

