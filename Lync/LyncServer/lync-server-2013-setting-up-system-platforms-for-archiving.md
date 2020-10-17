---
title: 'Lync Server 2013: Настройка системных платформ для архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up system platforms for Archiving
ms:assetid: 2df40fdf-0e32-46d4-9fb2-1ce1d7bfa328
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204768(v=OCS.15)
ms:contentKeyID: 48183716
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac0a0e39a65b32b42398aab832e7010573534807
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497556"
---
# <a name="setting-up-system-platforms-for-archiving-in-lync-server-2013"></a>Настройка системных платформ для архивации в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-09_

Прежде чем начинать развертывание компонента архивации, вам следует установить требуемую операционную систему и все остальное требуемое программное обеспечение на оборудовании, соответствующем требованиям к системе:

  - Платформа Lync Server **2013**     В развертываниях Lync Server 2013 нет серверов архивации. Вместо этого на серверах переднего плана и серверах Standard Edition запускаются унифицированные агенты по сбору данных для архивации, поэтому для размещения архивации отдельная системная платформа не требуется.

  - **Платформа**     хранения данных В Lync Server 2013 можно хранить данные, используя один из следующих вариантов:
    
      - Интеграция с Microsoft **Exchange**     Если вы хотите хранить данные архивации Lync Server 2013 с помощью развертывания Exchange 2013, а не или в дополнение к настройке отдельной базы данных для хранения данных архивации, развертывание Exchange должно работать под управлением Exchange 2013. Подробные сведения о настройке системных платформ для Exchange 2013 вы найдете в документации по продукту Exchange.
    
      - **SQL Server**     Если вы хотите использовать отдельную базу данных SQL Server для хранения данных архивации, а не или вместе с интеграцией Microsoft Exchange, перед развертыванием архивации необходимо настроить системную платформу для базы данных. Требования к конкретной платформе системы зависят от того, используете ли вы Microsoft SQL Server 2008 R2 или Microsoft SQL Server 2012 для базы данных архивации. Дополнительные сведения о настройке системных платформ для этих баз данных можно найти в документации по продукту Microsoft SQL Server 2008 R2 и Microsoft SQL Server 2012.

  - Платформа файлового **сервера**     Lync Server 2013 сохраняет файлы архивации Lync Server в том же расположении, что и для хранения файлов при настройке серверов переднего плана или сервера Standard Edition. Вы не можете указать отдельное расположение для хранения архивных файлов, поэтому соответствующая отдельная системная платформа не требуется. Если вы используете интеграцию с Microsoft Exchange, Exchange 2013 файлы для архивированных коммуникаций Lync хранятся на серверах Exchange 2013 для пользователей, размещенных на этих серверах Exchange.

</div>

<span> </span>

</div>

</div>

</div>

