---
title: Миграция сервера обновлений
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fc35a7641b4acb42578ec4e75375e171ae905e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849028"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a>Миграция сервера обновлений

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-28_

После запуска мастера слияния сервер, на котором работает ваш компьютер, будет объединен с пробной топологией Lync Server 2013. Однако настройка сервера обновлений Lync Server 2013 выполняется после миграции всех пользователей, так как пул Office Communications Server 2007 R2 не может взаимодействовать с сервером обновлений Lync Server 2013. В ходе параллельной миграции сервер Lync Server 2013 взаимодействует с сервером Office Communications Server 2007 R2.

При настройке сервера исправлений Lync Server 2013 Вы также должны обновить или заменить шлюзы Office Communications Server 2007 R2. Шлюзы Office Communications Server 2007 R2 не поддерживают сервер обновлений Lync Server 2013. Необходимо развернуть шлюзы, сертифицированные для Lync Server 2013, и связать их с сервером обновлений Lync Server 2013. Этот этап необходим для того, чтобы можно было полностью списать развертывание Office Communications Server 2007 R2.

В этом разделе описаны задачи настройки, которые необходимо выполнить после миграции сервера обновлений Lync Server 2013. Переход на размещенный сервер исправлений на отдельном сервере — это необязательная задача.

  - [Настройка сервера обновлений](configure-mediation-server.md)

  - [Изменение маршрутов голосовой связи для использования нового сервера исправлений Lync Server 2013](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [Переход размещенного сервера исправлений на отдельный сервер-посредник (необязательно)](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

