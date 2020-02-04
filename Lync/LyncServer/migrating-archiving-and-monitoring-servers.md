---
title: Перенос серверов архивирования и мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 77831579-df45-4697-b8c5-207b74a07a40
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205015(v=OCS.15)
ms:contentKeyID: 48184550
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 572cbee046ed960017a3b60b7ae68c58ec67cf23
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762887"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>Перенос серверов архивирования и мониторинга

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-02_

Если вы развернули сервер архивации и сервер мониторинга в среде Lync Server 2010, вы можете развернуть эти серверы в среде Lync Server 2013 после миграции пулов переднего плана. Тем не менее, если функции архивации и мониторинга критически важны для вашей организации, необходимо добавить архивацию и мониторинг в пул Lync Server 2013 Pilot, прежде чем вы сможете выполнить миграцию, чтобы они были доступны в процессе миграции.

Если вы хотите использовать функции архивации и наблюдения в процессе миграции, имейте в виду следующие моменты.

  - Архивирование данных и данных мониторинга не переносятся в развертывание Lync Server 2013. Данные, которые вы заархивированы перед списанием устаревшей среды, будут журналом действий в среде Lync Server 2010.

  - Версия Lync Server 2010 для архивации сервера и сервера мониторинга может быть связана только с интерфейсом front end сервера Lync Server 2010. В Lync Server 2013 возможности архивации и мониторинга больше не являются серверными ролями, но службы, интегрированные в пул переднего плана Lync Server 2013.

  - В течение времени существования устаревших развертываний и сред Lync Server 2013 версия сервера архивации и мониторинга сервера Lync Server 2010 собирает данные для пользователей, размещенных в пулах Lync Server 2010. Архивация и мониторинг в Lync Server 2013 сбор данных для пользователей, размещенных в пулах Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > На этапе миграции при использовании устаревшего пограничного сервера с новым пулом Lync Server 2013 Pilot версия сервера архивирования для Lync Server 2010 продолжает собирать данные для пользователей, размещенных на Lync Server 2010 пулов и архивации в Lync Server 2013 сбор данных для пользователей, размещенных в пулах Lync Server 2013.

    
    </div>

  - Если вы используете сторонние решения для архивации и мониторинга в сочетании с архивацией и мониторингом в Lync Server 2013, обратитесь к своему поставщику о том, когда и как следует интегрировать сторонние решения с Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

