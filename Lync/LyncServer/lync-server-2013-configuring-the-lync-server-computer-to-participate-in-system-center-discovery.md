---
title: Настройка компьютера Lync Server для участия в обнаружении System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b59622306fbde12eb570b72c95b37cec7885c7f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040928"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>Настройка компьютера Lync Server 2013 для участия в обнаружении System Center

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-20_

Чтобы убедиться, что новый агент Lync Server участвует в процессе обнаружения для System Center Operations Manager, необходимо выполнить следующую процедуру на каждом компьютере, на котором установлена консоль System Center Operations Manager:

1.  На вкладке **Администрирование** щелкните элемент **Управляемый агентом**.

2.  Щелкните правой кнопкой мыши имя компьютера и выберите пункт **Свойства**. В диалоговом окне **Свойства** на вкладке **Безопасность** выберите **Разрешить агенту работать как прокси и обнаруживать управляемые объекты на других компьютерах**, а затем нажмите кнопку **ОК**.

После выполнения действия 2 перезапустите службу агента работоспособности. (При перезапуске службы будет автоматически выполнено обнаружение нового компьютера. Если не перезапустить службу, обнаружение нового компьютера агентом System Center Operations Manager может занять до 4 часов.) После перезапуска службы проверьте журнал событий Operations Manager и убедитесь, что в нем не были записаны ошибки для данного компьютера.

</div>

<span> </span>

</div>

</div>

</div>

