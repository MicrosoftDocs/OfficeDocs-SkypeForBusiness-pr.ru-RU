---
title: Перенос серверов архивирования и мониторинга
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba86de15ea86844b677db1abb0f47f7e1995c7e8
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755309"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>Перенос серверов архивирования и мониторинга

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

Если вы развернули сервер архивации и сервер мониторинга в среде Lync Server 2010, вы можете развернуть эти серверы в среде Lync Server 2013 после миграции пулов переднего плана. Если функции архивации и мониторинга критически важны для вашей организации, следует добавить архивацию и мониторинг в пилотный пул Lync Server 2013 перед переносом, чтобы обеспечить доступность функций в процессе миграции.

Если функции архивации и мониторинга должны быть доступны во время миграции, помните о следующем.

  - Архивирование данных и данных мониторинга не переносятся в развертывание Lync Server 2013. Данные, резервные копии которых были созданы перед ликвидацией старой среды, будут указаны в журнале действий в среде Lync Server 2010.

  - Lync Server 2010 версии сервера архивации и сервера мониторинга можно связать только с интерфейсным пулом Lync Server 2010. В Lync Server 2013 Архивация и мониторинг больше не являются ролями серверов, но службы, интегрированные в интерфейсный пул Lync Server 2013.

  - Во время совместного использования устаревших развертываний и развертываний Lync Server 2013 версия сервера архивации и сервера мониторинга Lync Server 2010 собирает данные для пользователей, размещенных в пулах Lync Server 2010. Архивация и мониторинг в Lync Server 2013 сбор данных для пользователей, размещенных в пулах Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > На этапе миграции, когда вы по-прежнему используете старый пограничный сервер с новым пилотным пулом Lync Server 2013, версия сервера архивации для Lync Server 2010 продолжает собирать данные для пользователей, размещенных на сервере Lync Server 2010 Pools и архивация в Lync Server 2013 собирает данные для пользователей, размещенных в пулах Lync Server 2013.

    
    </div>

  - Если вы используете решение для архивации и мониторинга стороннего производителя в сочетании с архивацией и мониторингом в Lync Server 2013, обратитесь к поставщику за сведениями о том, когда и как следует интегрировать стороннее решение с Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

