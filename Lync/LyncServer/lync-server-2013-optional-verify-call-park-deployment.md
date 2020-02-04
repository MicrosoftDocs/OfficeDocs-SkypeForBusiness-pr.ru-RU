---
title: 'Lync Server 2013: (необязательно) Проверка развертывания для остановки вызова'
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
ms.openlocfilehash: 5cfc0d62bcfabe1a5bcddfb069d95b18aa0d30d4
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755723"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-verify-call-park-deployment-in-lync-server-2013"></a>Необязательно Проверка развертывания парковки звонков в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-11_

После установки и настройки парковки звонка необходимо проверить конфигурацию, чтобы убедиться, что стоянки и получение вызовов работают должным образом. At minimum, verify the following:

  - Позвоните пользователю, для которого установлен флажок "припаркованный Звонок", и приостановить Звонок абонентом.
    
    <div>
    

    > [!NOTE]  
    > Если вы включили переадресацию звонков в голосовой политике прямо перед выполнением этого теста, пользователь, который применяет приостановку, должен выйти из Lync Server, а затем снова войти, чтобы можно было видеть параметр "дозвониться" в списке "передача звонков".

    
    </div>

  - Для извлечения вызова наберите номер орбиты.

  - Приостановите другой вызов, дождитесь истечения времени ожидания и не поднимайте трубку при переключении на удерживаемого абонента. Убедитесь в том, что вызов с истекшим временем ожидания перенаправляется в резервное место назначения, заданное параметром **OnTimeoutURI**.

</div>

<span> </span>

</div>

</div>

</div>

