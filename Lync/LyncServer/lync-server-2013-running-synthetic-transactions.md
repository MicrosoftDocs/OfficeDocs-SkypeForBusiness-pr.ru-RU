---
title: 'Lync Server 2013: выполнение искусственных транзакций'
description: 'Lync Server 2013: выполнение искусственных транзакций.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Running synthetic transactions
ms:assetid: 2b56c7bd-8956-4fa1-8232-1876b959b258
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720911(v=OCS.15)
ms:contentKeyID: 63969593
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26b0c26024f361dac196319eaf849c1847033cc9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569355"
---
# <a name="running-synthetic-transactions-in-lync-server-2013"></a>Выполнение искусственных транзакций в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-08-18_

Искусственные транзакции обычно выполняются двумя способами. Командлеты CsHealthMonitoringConfiguration можно использовать для настройки тестовых пользователей для каждого из пулов регистраторов. Эти тестовые пользователи являются пользователями, предварительно настроенными для использования с искусственными транзакциями. (Как правило, это тестовые учетные записи, а не учетные записи, принадлежащие реальным пользователям.) При использовании тестовых пользователей, настроенных для пула, можно выполнить искусственную транзакцию для этого пула без необходимости указывать удостоверения (и предоставлять учетные данные) для учетных записей пользователей, участвующих в тестировании.

Вы также можете выполнить искусственную транзакцию с помощью фактических учетных записей пользователей. Например, если два пользователя не могут обмениваться мгновенными сообщениями, можно выполнить искусственную транзакцию с использованием этих двух учетных записей пользователей (а не из двух тестовых учетных записей), а затем попробовать диагностировать и устранить эту проблему. Если вы решили провести искусственную транзакцию с использованием фактических учетных записей пользователей, необходимо указать имена и пароли для входа для каждого пользователя.

<div>

## <a name="see-also"></a>См. также


[Настройка тестовых пользователей и параметров конфигурации узла-наблюдателя в Lync Server 2013](lync-server-2013-configuring-watcher-node-test-users-and-configuration-settings.md)  
[Специальные инструкции по настройке для искусственных транзакций в Lync Server 2013](lync-server-2013-special-setup-instructions-for-synthetic-transactions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

