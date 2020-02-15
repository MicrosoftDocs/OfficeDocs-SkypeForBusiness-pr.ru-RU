---
title: Перенос серверов архивации и мониторинга
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrating Archiving and Monitoring servers
ms:assetid: 8d879253-ad76-42b7-8386-e44b110239cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688124(v=OCS.15)
ms:contentKeyID: 49733722
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 100ec85b345a744232e9bfab37a2ee11c7f84430
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036117"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrating-archiving-and-monitoring-servers"></a>Перенос серверов архивации и мониторинга

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

Если вы развернули сервер архивации и сервер мониторинга в Office Communications Server 2007 R2, вы можете развернуть эти серверы в среде Lync Server 2013 после миграции пулов переднего плана. Но если функции архивации и мониторинга важны для вашей организации, следует добавить архивацию и мониторинг в пилотный пул перед миграцией, чтобы эти функции были доступны во время переноса.

Если функции архивации и мониторинга должны быть доступны во время миграции и на этапе сосуществования, помните о следующем.

  - Архивирование данных и данных мониторинга не переносятся в развертывание Lync Server 2013. Данные, которые вы создаете перед списанием устаревшей среды, будут храниться в истории активности Office Communications Server 2007 R2.

  - Версия сервера архивирования и сервера мониторинга Office Communications Server 2007 R2 может быть связана только с интерфейсным пулом Office Communications Server 2007 R2. В Lync Server 2013 Архивация и мониторинг больше не являются ролями серверов, но службы, интегрированные в интерфейсный пул Lync Server 2013.

  - Во время совместного использования устаревших развертываний и развертываний Lync Server 2013 в Office Communications Server 2007 R2 сервер архивации и сервер мониторинга собирает данные для пользователей, размещенных в пулах Office Communications Server 2007 R2. Lync Server 2013 версии сервера архивации и сервера мониторинга собирают данные для пользователей, размещенных в пулах Lync Server 2013.
    
    <div>
    

    > [!NOTE]  
    > На этапе миграции, когда вы по-прежнему используете старый пограничный сервер с новым пилотным пулом Lync Server 2013, версия сервера архивации Office Communications Server 2007 R2 продолжает собирать данные для пользователей, размещенных на сервере Office Communications Server 2007 Пулы R2 и Lync Server 2013 версии сервера архивации собирает данные для пользователей, размещенных в пулах Lync Server 2013.

    
    </div>

  - Если вы используете решение для архивации и мониторинга стороннего производителя вместе с сервером архивации и сервером мониторинга, обратитесь к поставщику за сведениями о том, когда и как следует интегрировать стороннее решение с Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

