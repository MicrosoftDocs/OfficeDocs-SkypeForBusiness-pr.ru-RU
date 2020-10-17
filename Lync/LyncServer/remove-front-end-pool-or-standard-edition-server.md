---
title: Удаление пула переднего плана или сервера Standard Edition
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove Front End pool or Standard Edition server
ms:assetid: 83c39a36-49a1-4ac6-9cc5-b0e441b1fdec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688115(v=OCS.15)
ms:contentKeyID: 49733713
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69a1c36de9aa3cbd4a46dc0bba4c862734b382ef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500056"
---
# <a name="remove-front-end-pool-or-standard-edition-server"></a>Удаление пула переднего плана или сервера Standard Edition

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-04_

В этом разделе описывается процесс удаления интерфейсного пула или сервера переднего плана Standard Edition. При удалении пула переднего плана необходимо удалить каждый сервер переднего плана, который входит в состав пула, в процессе удаления пула. При удалении сервера переднего плана Standard Edition необходимо удалить определение хранилища SQL из построителя топологий.

<div>

## <a name="to-remove-a-front-end-server-pool"></a>Удаление пула интерфейсных серверов

1.  Откройте построитель топологий.

2.  Перейдите к узлу Lync Server 2010.

3.  Разверните **Пулы переднего плана Enterprise Edition**, разверните пул переднего плана, щелкните правой кнопкой мыши интерфейсный пул, который требуется удалить, и выберите команду **Удалить**.

4.  Опубликуйте топологию, проверьте состояние репликации, а затем при необходимости запустите мастер развертывания Lync Server.

</div>

<div>

## <a name="to-remove-a-standard-edition-front-end-server"></a>Удаление интерфейсного сервера Standard Edition

1.  Откройте построитель топологий.

2.  Перейдите к узлу Lync Server 2010.

3.  Разверните узел **серверы Standard Edition Standard Edition**, щелкните правой кнопкой мыши сервер переднего плана, который нужно удалить, и выберите команду **Удалить**.

4.  Разверните узел **хранилища SQL**, щелкните правой кнопкой мыши базу данных SQL Server, связанную с сервером переднего плана Standard Edition, а затем выберите команду **Удалить**.
    
    <div>
    

    > [!IMPORTANT]  
    > Необходимо удалить определение размещенных баз данных SQL Server с сервера переднего плана Standard Edition.

    
    </div>

5.  Опубликуйте топологию, проверьте состояние репликации, а затем при необходимости запустите мастер развертывания Lync Server.

</div>

</div>

<span> </span>

</div>

</div>

</div>

