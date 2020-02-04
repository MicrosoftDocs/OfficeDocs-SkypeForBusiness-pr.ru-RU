---
title: 'Lync Server 2013: обзор сценариев создания рабочих процессов'
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
ms.openlocfilehash: 08ecb210ea937184039587d289c5c9c57cb4fa4d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755413"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-workflow-creation-scenarios-in-lync-server-2013"></a>Обзор сценариев создания рабочих процессов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-17_

Существует два возможных сценария создания рабочих процессов.

  - **Администратор создает и настраивает рабочий процесс**. Участник роли CsResponseGroupAdministrator (или равнозначной роли) создает и активирует рабочий процесс и все его элементы, включая группы агентов, очереди, выходные дни, рабочие часы, музыку в режиме удержания и т. п.

  - **Администратор создает рабочий процесс, а руководитель настраивает параметры**. Участник роли CsResponseGroupAdministrator (или равнозначной роли) задает основной универсальный код ресурса SIP, отображаемое имя, назначает хотя бы одного участника роли CsResponseGroupManager, выбирает очередь и активирует рабочий процесс. После этого участник роли CsResponseGroupManager может войти и изменить конфигурацию рабочего процесса: создать группы агентов и назначать их очереди, задать телефонный номер, выходные дни, рабочие часы, музыку в режиме удержания и т. п.
    
    <div>
    

    > [!NOTE]  
    > Если нужно создать управляемый рабочий процесс, рабочий процесс необходимо создать как активный. После сохранения активный управляемый процесс можно изменить и отключить.

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

