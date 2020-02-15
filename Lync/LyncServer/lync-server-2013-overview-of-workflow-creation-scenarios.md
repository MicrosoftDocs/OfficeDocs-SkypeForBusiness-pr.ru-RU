---
title: 'Lync Server 2013: Обзор сценариев создания рабочих процессов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of workflow creation scenarios
ms:assetid: 05e0c175-0f1a-4bb1-b048-c68584d00649
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204646(v=OCS.15)
ms:contentKeyID: 48183309
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27383db13176150078bf4855dee4df57cb1615af
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2020
ms.locfileid: "41989884"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a>Обзор сценариев создания рабочих процессов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-17_

Существует два возможных сценария создания рабочих процессов.

  - **Администратор создает и настраивает рабочий процесс**. Участник роли CsResponseGroupAdministrator (или эквивалентной роли) создает и активирует рабочий процесс и все элементы в этом рабочем процессе, такие как группы агентов, очереди, выходные дни, рабочие часы, воспроизведение музыки на удержании и т. д.

  - **Администратор создает рабочий процесс, а менеджер настраивает параметры**. Участник роли CsResponseGroupAdministrator (или эквивалентной роли) задает основной SIP URI, отображаемое имя, назначает хотя бы одного участника роли CsResponseGroupManager и выбирает очередь. Администратор устанавливает рабочий процесс, но не активирует его. Затем участник роли CsResponseGroupManager может войти и изменить конфигурацию рабочего процесса, создав группы агентов и назначив эти группы в очередь, настроив телефонный номер, выходные дни, рабочие часы, воспроизведение музыки на удержании и другие параметры.
    
    <div>
    

    > [!NOTE]  
    > Если нужно создать управляемый рабочий процесс, рабочий процесс необходимо создать как активный. После сохранения активный управляемый процесс можно изменить и отключить.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

