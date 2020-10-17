---
title: Проверка среды Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f4107877c237abef92233dbca88cf7060fdca25
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515946"
---
# <a name="verify-office-communications-server-2007-r2-environment"></a>Проверка среды Office Communications Server 2007 R2

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-16_

Перед развертыванием Lync Server 2013 в режиме сосуществования с Office Communications Server 2007 R2 необходимо убедиться, что службы Office Communications Server 2007 R2 настроены и запущены.

**Проверка того, что пул запущен с помощью средства администрирования Office Communications Server 2007 R2**

1.  Откройте средство администрирования Office Communications Server 2007 R2.

2.  Разверните узел **Лес**, разверните узел **Серверы Standard Edition** или **Корпоративные пулы**, а затем разверните пул или сервер.

3.  Убедитесь, что службы запущены на сервере Standard Edition или в корпоративном пуле.
    
    ![Консоль администрирования Office Communications Server 2007 R2](images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Консоль администрирования Office Communications Server 2007 R2")

**Обзор пользователей, настроенных для Office Communications Server 2007 R2**

1.  Откройте средство администрирования Office Communications Server 2007 R2.

2.  Разверните узел **Лес**, разверните узел **Серверы Standard Edition** или **Корпоративные пулы**, а затем разверните пул или сервер.

3.  Щелкните **Пользователи**.

4.  Проверьте список пользователей Office Communications Server 2007 R2.
    
    ![Список пользователей в средстве администрирования OCS](images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Список пользователей в средстве администрирования OCS")

**Проверка устаревшей конфигурации федеративного партнера XMPP**

1.  Из устаревшего сервера XMPP перейдите к \\ апплету администрирование служб.

2.  Убедитесь, что служба шлюза XMPP Office Communications Server запущена.
    
    ![Служба шлюза XMPP для Office Communications Server](images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Служба шлюза XMPP для Office Communications Server")

</div>

<span> </span>

</div>

</div>

</div>

