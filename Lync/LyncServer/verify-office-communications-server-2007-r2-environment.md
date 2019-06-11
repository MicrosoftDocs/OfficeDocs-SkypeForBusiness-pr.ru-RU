---
title: Проверка среды Office Communications Server 2007 R2
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify Office Communications Server 2007 R2 environment
ms:assetid: e051bdd5-e7ef-4754-8705-900b2c57f37c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721906(v=OCS.15)
ms:contentKeyID: 49733840
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9369ad631b772e0a73677ab3214e24083426148a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848880"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-office-communications-server-2007-r2-environment"></a>Проверка среды Office Communications Server 2007 R2

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-16_

Перед развертыванием Lync Server 2013 в состоянии сосуществования с помощью Office Communications Server 2007 R2 необходимо убедиться, что службы Office Communications Server 2007 R2 настроены и запущены.

**Проверка того, что пул запущен с помощью средства администрирования Office Communications Server 2007 R2**

1.  Откройте средство администрирования Office Communications Server 2007 R2.

2.  Разверните узел **леса** , разверните узел **Стандартные серверы выпуска** или **Пулы предприятий** , а затем разверните имя пула или сервера.

3.  Убедитесь, что службы запущены на сервере Standard Edition или корпоративном пуле.
    
    ![Консоль администрирования Office Communications Server 2007 R2] (images/JJ721906.76897b6d-f433-47d2-930d-0816fc30a3c2(OCS.15).jpg "Консоль администрирования Office Communications Server 2007 R2")

**Просмотр пользователей, настроенных для Office Communications Server 2007 R2**

1.  Откройте средство администрирования Office Communications Server 2007 R2.

2.  Разверните узел **леса** , разверните узел **Стандартные серверы выпуска** или **Пулы предприятий** , а затем разверните имя пула или сервера.

3.  Нажмите кнопку **Пользователи**.

4.  Проверьте список пользователей Office Communications Server 2007 R2.
    
    ![Список пользователей в средстве администрирования OCS] (images/JJ721906.f6bb7c4f-cbed-4389-8d0a-69a28577f17a(OCS.15).jpg "Список пользователей в средстве администрирования OCS")

**Проверка конфигурации устаревшего КСМПП федеративного партнера**

1.  Из устаревшего сервера КСМПП перейдите на вкладку Администрирование\\служб.

2.  Убедитесь, что служба шлюза Office Communications Server КСМПП запущена.
    
    ![Служба шлюза Office Communications Server КСМПП] (images/JJ721906.23223724-3c4b-4cb9-ace2-1cab2c3c91c3(OCS.15).jpg "Служба шлюза Office Communications Server КСМПП")

</div>

<span> </span>

</div>

</div>

</div>

