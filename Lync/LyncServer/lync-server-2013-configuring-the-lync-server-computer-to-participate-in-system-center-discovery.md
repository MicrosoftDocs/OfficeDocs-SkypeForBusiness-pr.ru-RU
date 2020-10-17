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
ms.openlocfilehash: 9783b8054c74b071c927cc42f32d05700877daad
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48532376"
---
# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>Настройка компьютера Lync Server 2013 для участия в обнаружении System Center

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



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

