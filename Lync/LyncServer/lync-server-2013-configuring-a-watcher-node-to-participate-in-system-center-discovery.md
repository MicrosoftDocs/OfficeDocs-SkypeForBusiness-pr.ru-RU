---
title: Настройка узла-наблюдателя для участия в обнаружении System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66be6bd0336471626f2ca4e41a89c3a45b073f05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841296"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a>Настройка узла-наблюдателя в Lync Server 2013 для участия в обнаружении System Center

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-22_

Чтобы убедиться в том, что узел-наблюдатель участвует в процессе обнаружения для System Center Operations Manager, необходимо выполнить описанные ниже действия на компьютере с установленной консолью System Center Operations Manager.

1.  На вкладке **Администрирование** выберите пункт **управляемая агентом**.

2.  Щелкните правой кнопкой мыши имя компьютера узла-наблюдателя и выберите пункт **Свойства**. В диалоговом окне **Свойства** на вкладке **Безопасность** выберите **Разрешить этому агенту выступать в качестве прокси-сервера и найдите управляемые объекты на других компьютерах**, а затем нажмите кнопку **ОК**.

После того как вы настраиваете узел наблюдателя для работы в качестве прокси-сервера, перезагрузите компьютер с узлом-наблюдателем. После перезагрузки компьютера убедитесь в том, что в журнал событий Operations Manager на этом компьютере не записываются события об ошибках. После запуска компьютера в течение 15 минут или с помощью консоли Operations Manager убедитесь, что компьютеры Lync Server указаны в категории **Lync** .

</div>

<span> </span>

</div>

</div>

</div>

