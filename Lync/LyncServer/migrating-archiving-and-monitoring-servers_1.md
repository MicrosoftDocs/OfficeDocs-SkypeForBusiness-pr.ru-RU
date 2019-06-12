---
title: Перенос серверов архивирования и мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 902970548d4bd9e95e1bd4e7d6eba75e2fe405d3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849014"
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

Если вы развернули сервер архивации и сервер мониторинга в Office Communications Server 2007 R2, вы можете развернуть эти серверы в среде Lync Server 2013 после миграции пулов переднего плана. Тем не менее, если функции архивации и мониторинга важны для вашей организации, необходимо добавить архивацию и мониторинг в пилотный пул перед переходом, чтобы обеспечить доступность функций в процессе миграции.

Если вы хотите выполнять архивацию и мониторинг на этапе миграции и сосуществования, учитывайте указанные ниже моменты.

  - Архивирование данных и данных мониторинга не переносятся в развертывание Lync Server 2013. Данные, которые вы заархивированы перед списанием устаревшей среды, будут журналом активности Office Communications Server 2007 R2.

  - Версия архивации сервера и сервера мониторинга Office Communications Server 2007 R2 может быть связана только с внешним интерфейсом пула Office Communications Server 2007 R2. В Lync Server 2013 возможности архивации и мониторинга больше не являются серверными ролями, но службы, интегрированные в пул переднего плана Lync Server 2013.

  - В течение времени существования устаревших развертываний и сред Lync Server 2013 версия Office Communications Server 2007 R2 сервера архивации и мониторинг сервера собирают данные для пользователей, размещенных на пулах Office Communications Server 2007 R2. Версия Lync Server 2013 для архивации сервера и сервера мониторинга собирают данные для пользователей, которые хранятся в пулах Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > На этапе миграции при использовании устаревшего пограничного сервера с новым пулом Lync Server 2013 Pilot версия сервера архивации Office Communications Server 2007 R2 продолжает собирать данные для пользователей, размещенных на сервере Office Communications Server 2007 Пулы R2 и Lync Server 2013 версия сервера архивации собирает данные для пользователей, которые хранятся в пулах Lync Server 2013.

    
    </div>

  - Если вы используете стороннее решение для архивации и мониторинга в сочетании с сервером архивирования и мониторинга, обратитесь к своему поставщику о том, когда и как следует интегрировать сторонние решения с Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

