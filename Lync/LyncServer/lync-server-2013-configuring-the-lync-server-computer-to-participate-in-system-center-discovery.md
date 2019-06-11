---
title: Настройка компьютера Lync Server для участия в обнаружении System Center
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the Lync Server computer to participate in System Center discovery
ms:assetid: 2f9c9cb0-3120-4571-9cd2-657c2123fe21
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204776(v=OCS.15)
ms:contentKeyID: 48183731
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4b50fad3e0d197259847db9a94bf9e64618d7e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-lync-server-2013-computer-to-participate-in-system-center-discovery"></a>Настройка компьютера Lync Server 2013 для участия в обнаружении System Center

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-20_

Чтобы убедиться в том, что новый агент сервера Lync участвует в процессе обнаружения для System Center Operations Manager, необходимо выполнить описанные ниже действия для каждого компьютера, на котором установлена консоль System Center Operations Manager.

1.  На вкладке **Администрирование** выберите пункт **управляемая агентом**.

2.  Right-click the name of the computer, and then click **Properties**. В диалоговом окне **Свойства** на вкладке **Безопасность** выберите **Разрешить этому агенту выступать в качестве прокси-сервера и найдите управляемые объекты на других компьютерах**, а затем нажмите кнопку **ОК**.

После завершения действия 2 перезапустите службу агента работоспособности. (При перезагрузке служба будет "принудительно" обнаружение нового компьютера. Если вы не перезапускает службу, она может занять до 4 часов, прежде чем новый компьютер будет обнаружен с помощью System Center Operations Manager.). После перезагрузки службы убедитесь в том, что в журнале событий Operations Manager на этом компьютере не записываются события ошибок.

</div>

<span> </span>

</div>

</div>

</div>

