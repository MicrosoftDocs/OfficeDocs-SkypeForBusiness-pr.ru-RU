---
title: 'Lync Server 2013: Управление узлами-наблюдателями'
description: 'Lync Server 2013: Управление узлами-наблюдателями.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1795b09bbca73d8157cf796ceeaaeafb9cc2ebc5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556615"
---
# <a name="managing-watcher-nodes-in-lync-server-2013"></a>Управление узлами-наблюдателями в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-20_

В дополнение к изменению искусственных транзакций, выполняемых на узле-наблюдателе, администраторы могут также использовать командлет **Set-CsWatcherNodeConfiguration** для выполнения двух других важных задач: включение/отключение узла-наблюдателя и настройка узла-наблюдателя для использования внутренних URL-адресов или внешних URL-адресов при проведении тестирования.

По умолчанию узлы-наблюдатели периодически запускают все включенные искусственные транзакции. Однако иногда они могут приостановить выполнение транзакций. Например, если узел-наблюдатель временно отключился от сети, у него больше нет причин запускать искусственные транзакции. Без сетевого подключения эти транзакции заведомо завершатся со сбоем. Если вы хотите временно отключить узел-наблюдатель, выполните следующую команду в командной консоли Lync Server:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

Эта команда приведет к отключению выполнения искусственных транзакций на узле-наблюдателе. Чтобы возобновить выполнение искусственных транзакций, снова задайте для свойства Enabled значение True ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> Свойство Enabled может использоваться для включения или отключения узлов-наблюдателей. Если нет необходимости временно удалять узел-наблюдатель, используйте командлет <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>:<BR>Remove-CsWatcherNodeConfiguration –Identity "atl-watcher-001.litwareinc.com"<BR>Эта команда удаляет с указанного компьютера все параметры конфигурации узла-наблюдателя, что препятствует автоматическому запуску на этом компьютере искусственных транзакций. Однако команда не удаляет файлы агента System Center и системные файлы Lync Server 2013.



</div>

По умолчанию узлы-наблюдатели используют при проведении тестов внешние URL-адреса. Однако узлы-наблюдатели можно настроить для использования внутренних URL-адресов организации. Это позволит администраторам проверить доступ к URL-адресам тех пользователей, которые находятся внутри сети периметра. Чтобы настроить узел-наблюдатель для использования внутренних URL-адресов вместо внешних URL-адресов, задайте для свойства UseInternalWebUrls значение True ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

Если сбросить это свойство до значения по умолчанию False ($False), наблюдатель будет использовать внешние URL-адреса:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

