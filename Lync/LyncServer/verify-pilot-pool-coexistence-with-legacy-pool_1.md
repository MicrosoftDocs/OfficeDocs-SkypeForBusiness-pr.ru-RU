---
title: Проверка совместного использования пилотного пула с устаревшим пулом
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify pilot pool coexistence with legacy pool
ms:assetid: 597d0fa6-ca04-4521-b1c2-72d7f35ecd08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204914(v=OCS.15)
ms:contentKeyID: 48184209
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4952640d6f6e938b460855118163d98e001f6a77
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42188862"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-pilot-pool-coexistence-with-legacy-pool"></a>Проверка совместного использования пилотного пула с устаревшим пулом

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

<div>

## <a name="verify-the-pool-in-office-communications-server-2007-r2-administrative-tool"></a>Проверка пула в средстве администрирования Office Communications Server 2007 R2

1.  Откройте средство администрирования Office Communications Server 2007 R2.

2.  Разверните узел **Лес**, разверните узел **Серверы Standard Edition** или **Корпоративные пулы**, а затем разверните пул или сервер.

3.  Убедитесь, что службы Office Communications Server 2007 R2 запущены в пуле.
    
    ![Консоль администрирования Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Консоль администрирования Office Communications Server 2007 R2")  

</div>

<div>

## <a name="verify-the-pilot-pool-in-lync-server-2013-control-panel"></a>Проверка пилотного пула в панели управления Lync Server 2013

1.  Войдите на сервер переднего плана Lync Server 2013 с учетной записью пользователя, которая является участником роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Щелкните пункт **Топология**.

4.  Убедитесь, что все развернутые серверы присутствуют в пилотном пуле.
    
    ![Страница топологии панели управления Lync Server](images/JJ204914.a3d1ba5f-c1a7-45e8-b9a5-7cb07b01af8c(OCS.15).jpg "Страница топологии панели управления Lync Server")  

</div>

<div>

## <a name="verify-lync-server-2013-services-have-started"></a>Проверка того, что службы Lync Server 2013 запущены

1.  На сервере переднего плана Lync Server 2013 откройте приложение **службы** из группы " **Администрирование** ".

2.  Убедитесь, что отображенные службы соответствуют службам в следующем списке.
    
    ![Страница служб, на которой запущены службы Lync](images/JJ204914.fd35d54a-2ab6-4c09-b5e9-fd5bf10f6f51(OCS.15).jpg "Страница служб, на которой запущены службы Lync")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

