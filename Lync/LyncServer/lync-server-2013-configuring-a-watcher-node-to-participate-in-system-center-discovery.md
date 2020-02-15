---
title: Настройка узла-наблюдателя для участия в обнаружении System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring a watcher node to participate in System Center discovery
ms:assetid: 15c5dcfd-603b-47ea-af1b-8714c2ec08af
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204704(v=OCS.15)
ms:contentKeyID: 48183500
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a90f07b445da792e0bc3b22967e41d8cd8d2fcc
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049211"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-a-watcher-node-in-lync-server-2013-to-participate-in-system-center-discovery"></a>Настройка узла-наблюдателя в Lync Server 2013 для участия в обнаружении System Center

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-22_

Чтобы убедиться, что узел-наблюдатель участвует в процессе обнаружения для System Center Operations Manager, необходимо выполнить следующую процедуру на компьютере с установленной консолью System Center Operations Manager:

1.  На вкладке **Администрирование** выберите **Управляемые агентом**.

2.  Щелкните правой кнопкой компьютер узла-наблюдателя и выберите пункт **Свойства**. В диалоговом окне **Свойства** перейдите на вкладку **Безопасность**, установите флажок **Разрешить агенту работать как прокси и обнаруживать управляемые объекты на других компьютерах** и нажмите кнопку **ОК**.

После настройки узла-наблюдателя для работы в качестве прокси-сервера необходимо перезагрузить компьютер этого узла-наблюдателя. После перезагрузки компьютера убедитесь, что события ошибок не записываются в журнал событий Operations Manager на этом компьютере. После запуска компьютера в течение 15 минут или, с помощью консоли Operations Manager убедитесь, что компьютеры Lync Server указаны в категории **Lync** .

</div>

<span> </span>

</div>

</div>

</div>

