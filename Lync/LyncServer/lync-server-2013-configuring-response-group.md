---
title: 'Lync Server 2013: Настройка группы ответа'
description: 'Lync Server 2013: Настройка группы ответа.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Response Group
ms:assetid: c56db929-cb21-4af0-be3f-c8f807b78a5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205249(v=OCS.15)
ms:contentKeyID: 48185359
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 92674bb971ec5216051d75d788dc58b9c7ca641c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547935"
---
# <a name="configuring-response-group-in-lync-server-2013"></a>Настройка группы ответа в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-30_

Группа ответа — это функция корпоративной голосовой связи, которая выполняет маршрутизацию и очередность входящих звонков в группы людей, называемых *агентами*, например службой поддержки или службой поддержки клиентов.

Компоненты, необходимые для группы ответа, устанавливаются и включаются автоматически на сервере переднего плана или сервере Standard Edition при развертывании корпоративной голосовой связи. Чтобы предоставить доступ к группе ответа пользователям, необходимо настроить группы агентов, затем очереди и рабочие процессы. Кроме того, администратор группы ответа может делегировать настройку существующего рабочего процесса диспетчеру группы ответа, который может изменить и изменить рабочий процесс и связанные с ним группы агентов и очереди.

В этом разделе описывается настройка группы ответа Lync Server 2013. Предполагается, что вы уже прочитали разделы планирования, связанные с группой ответа и развернули сервер Enterprise Edition или сервер Standard Edition с корпоративной голосовой связью.

<div>


> [!TIP]  
> Для получения дополнительных сведений о создании группы ответа с помощью командной консоли Lync Server, в том числе примера скрипта, обратитесь к разделу "Создание первой группы ответа с помощью командной консоли Lync Server" <A href="https://go.microsoft.com/fwlink/p/?linkid=204108">https://go.microsoft.com/fwlink/p/?linkId=204108</A> .



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Разрешения и необходимые условия для настройки группы ответа в Lync Server 2013](lync-server-2013-response-group-configuration-permissions-and-prerequisites.md)

  - [Процесс развертывания для группы ответа в Lync Server 2013](lync-server-2013-deployment-process-for-response-group.md)

  - [Обзор сценариев создания рабочих процессов в Lync Server 2013](lync-server-2013-overview-of-workflow-creation-scenarios.md)

  - [Создание групп агентов группы ответа Lync Server 2013](lync-server-2013-create-response-group-agent-groups.md)

  - [Создание очередей группы ответа в Lync Server 2013](lync-server-2013-create-response-group-queues.md)

  - [Необязательно Определение рабочих часов для группы ответа в Lync Server 2013](lync-server-2013-optional-define-response-group-business-hours.md)

  - [Необязательно Определение наборов праздников группы ответа в Lync Server 2013](lync-server-2013-optional-define-response-group-holiday-sets.md)

  - [Создание рабочих процессов группы ответа в Lync Server 2013](lync-server-2013-create-response-group-workflows.md)

  - [Необязательно Проверка развертывания группы ответа в Lync Server 2013](lync-server-2013-optional-verify-response-group-deployment.md)

</div>

<div>

## <a name="see-also"></a>См. также


[Планирование функций управления звонками в Lync Server 2013](lync-server-2013-planning-for-call-management-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

