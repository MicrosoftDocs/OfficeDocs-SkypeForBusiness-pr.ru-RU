---
title: Удаление сервера переднего плана из пула
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove a Front End Server from a pool
ms:assetid: 767225c9-7c0b-4d54-a407-d77134ba2abe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688095(v=OCS.15)
ms:contentKeyID: 49733694
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ef9df56c094bb5d7a3972a7c062905cbc4a844a
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757160"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-a-front-end-server-from-a-pool"></a>Удаление сервера переднего плана из пула

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-04_

Сервер переднего плана Microsoft Lync Server 2010 Enterprise Edition не может существовать как изолированный компьютер. Он должен быть определен как интерфейсный пул, даже если в пуле только один компьютер.

В этом разделе описывается процесс удаления отдельного сервера переднего плана из существующего интерфейсного пула. Если сервер переднего плана является последним в пуле или если вы полностью удаляете пул, обратитесь к разделу [Удаление пула переднего плана или сервера Standard Edition](remove-front-end-pool-or-standard-edition-server.md). Перед удалением интерфейсного пула нет необходимости удалять отдельные серверы переднего плана. При удалении пула необходимо удалить все серверы переднего плана.

<div>

## <a name="to-remove-a-front-end-server-from-a-pool"></a>Удаление сервера переднего плана из пула

1.  Откройте сервер переднего плана Lync Server 2013, откройте построитель топологий.

2.  Перейдите к узлу Lync Server 2010.

3.  Разверните **Пулы переднего плана Enterprise Edition**, разверните пул переднего плана с сервером переднего плана, который требуется удалить, щелкните правой кнопкой мыши сервер переднего плана, который нужно удалить, и выберите команду **Удалить**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

