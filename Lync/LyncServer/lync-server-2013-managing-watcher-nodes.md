---
title: 'Lync Server 2013: Управление узлами наблюдения'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e7edddd1a1bb67dc4bf3df5b7809aa76b2397e56
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a>Управление узлами наблюдения в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-20_

Помимо изменения искусственных транзакций, которые выполняются на узле-наблюдателе, администраторы также могут использовать командлет **Set-ксватчернодеконфигуратион** , чтобы выполнить две другие важные задачи: Включение и отключение узла-наблюдателя, а также Настройка узла-наблюдателя на использование внутренних URL или внешних URL-адресов при выполнении тестов.

По умолчанию узлы-наблюдатели периодически запускают все включенные искусственные транзакции. Однако иногда вам может потребоваться приостановить эти транзакции. Например, если узел-наблюдатель временно отключился от сети, у него больше нет причин запускать искусственные транзакции. При отсутствии подключения к сети эти транзакции гарантировано завершаются сбоем. Если вы хотите временно отключить узел наблюдателя, выполните следующую команду в командной консоли Lync Server.

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

Эта команда отключит выполнение виртуальных транзакций на узле наблюдателя ATL-Watch-001.litwareinc.com. Чтобы возобновить выполнение искусственных транзакций, снова задайте для свойства Enabled значение True ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> Свойство Enabled может использоваться для включения или отключения узлов-наблюдателей. Если нет необходимости временно удалять узел-наблюдатель, используйте командлет <STRONG>Remove-CsWatcherNodeConfiguration</STRONG>:<BR>Remove-Ксватчернодеконфигуратион – Identity "atl-watcher-001.litwareinc.com"<BR>Эта команда удаляет все параметры конфигурации узла-наблюдателя с указанного компьютера, что предотвращает автоматическое выполнение виртуальных транзакций на компьютере. Тем не менее, команда не удаляет файлы агента System Center и системные файлы Lync Server 2013.



</div>

По умолчанию узлы-наблюдатели используют внешние URL-адреса организации при проведении тестов. Однако узлы-наблюдатели также могут быть настроены на использование внутренних URL в Организации. Это позволит администраторам проверить доступ к URL-адресам тех пользователей, которые находятся внутри сети периметра. Чтобы настроить узел наблюдателя для использования внутренних URL-адресов вместо внешних URL-адресов, задайте для свойства Усеинтерналвебурлс значение true ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

Если вы переустановили для этого свойства значение по умолчанию, равное false ($False), наблюдатель будет использовать внешние URL-адреса:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

