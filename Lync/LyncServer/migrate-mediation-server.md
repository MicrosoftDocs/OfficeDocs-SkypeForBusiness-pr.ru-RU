---
title: Перенос сервера-посредника
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 581ce96b0c0a6ad0e4edd68eddbfacb160bf13f1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045861"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a>Перенос сервера-посредника

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

При запуске мастера слияния сервер-посредник объединяется с пробной топологией Lync Server 2013. Однако сервер-посредник Lync Server 2013 настраивается после миграции всех пользователей, так как пул Office Communications Server 2007 R2 не может подключиться к серверу-посреднику Lync Server 2013. Во время параллельной миграции пул Lync Server 2013 обменивается данными с сервером-посредником Office Communications Server 2007 R2.

При настройке сервера-посредника Lync Server 2013 Вы также должны обновить или заменить шлюзы Office Communications Server 2007 R2. Шлюзы Office Communications Server 2007 R2 не поддерживают сервер-посредник по Lync Server 2013. Вам необходимо развернуть шлюзы, сертифицированные для Lync Server 2013, и связать их с сервером-посредником Lync Server 2013. Этот шаг необходимо выполнить, прежде чем вы сможете полностью списать развертывание Office Communications Server 2007 R2.

В подразделах этого раздела описываются задачи настройки, которые необходимо выполнить после миграции сервера-посредника Lync Server 2013. Переход с совместно размещенного сервера-посредника на отдельный сервер-посредник является необязательным.

  - [Настройка сервера-посредника](configure-mediation-server.md)

  - [Изменение маршрутов голосовой связи для использования нового сервера-посредника Lync Server 2013](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [Перевод совмещенного сервера-посредника на автономный сервер-посредник (необязательно)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

