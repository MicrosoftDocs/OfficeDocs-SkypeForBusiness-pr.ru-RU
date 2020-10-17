---
title: 'Lync Server 2013: Проверка развертывания парковки вызовов (необязательно)'
description: 'Lync Server 2013: (необязательно) Проверка развертывания парковки вызовов.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Verify Call Park deployment
ms:assetid: fcfe0962-1a9c-4cbd-847c-fed40e3b1480
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413076(v=OCS.15)
ms:contentKeyID: 48185952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772392a3a791ed57c3220d80e9bd510d8803debb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541935"
---
# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a>Необязательно Проверка развертывания парковки вызовов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-11_

После установки и настройки парковки вызовов необходимо проверить конфигурацию, чтобы убедиться, что стоянки и получение вызовов работают должным образом. Следует проверить по крайней мере следующее:

  - Вызовите пользователя с включенным Парковким вызовов и приостановить вызов.
    
    <div>
    

    > [!NOTE]  
    > Если вы включили приостановку вызовов в политике голосовой связи непосредственно перед выполнением этого теста, пользователь, который подключается к серверу Lync Server, должен выйти из Lync Server, а затем снова войти, чтобы увидеть параметр парковки вызовов в списке передаваемых вызовов.

    
    </div>

  - Dial the orbit number to retrieve the call.

  - Запаркуйте другой звонок, дождитесь истечения его времени ожидания и не берите трубку при переключении на удерживаемого абонента. Убедитесь, что звонок с истекшим временем ожидания правильно перенаправляется в резервное назначение, указанное для **OnTimeoutURI**.

</div>

<span> </span>

</div>

</div>

</div>

