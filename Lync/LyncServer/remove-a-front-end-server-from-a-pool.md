---
title: Удаление сервера переднего плана из пула
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b798674173d14c2bd3f5638f6049c3a723786f91
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848917"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a>Удаление сервера переднего плана из пула

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-04_

Сервер переднего плана Microsoft Lync Server 2010 Enterprise Edition не может существовать как автономный компьютер. Он должен быть определен как пул переднего плана, даже если в пуле есть только один компьютер.

В этой статье описывается процесс удаления отдельного сервера переднего плана из существующего пула переднего плана. Если сервер переднего плана является последним в пуле или полностью удален, ознакомьтесь со сведениями [Удаление пула переднего плана или сервера Standard Edition](remove-front-end-pool-or-standard-edition-server.md). Перед удалением пула переднего плана вам не нужно удалять отдельные серверы переднего плана. При удалении пула удаляется каждый сервер переднего плана.

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a>Удаление сервера переднего плана из пула

1.  Откройте сервер клиентского доступа Lync Server 2013, откройте построитель топологии.

2.  Перейдите на узел Lync Server 2010.

3.  Разверните **Пулы переднего плана Enterprise Edition**, разверните пул переднего плана с сервером переднего плана, который вы хотите удалить, щелкните правой кнопкой мыши сервер переднего плана, который вы хотите удалить, и выберите команду **Удалить**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

