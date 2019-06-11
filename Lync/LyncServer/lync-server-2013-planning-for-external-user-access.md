---
title: 'Lync Server 2013: планирование доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d76d4853e7e748128214fc93b721a59e979af03e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a>Планирование доступа внешних пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-01-19_

Взаимодействие в большинстве организаций включает в себя службы и пользователей, которые не находятся в внутренней сети. Эти службы и пользователи включают в себя сотрудников, которые временно или постоянно находятся за пределами Организации, сотрудников, использующих общедоступные службы обмена мгновенными сообщениями, и потенциальных клиентов, партнеров и анонимных пользователей, которые вы пригласили для собраний и презентаций. В этой документации эти люди обозначаются как *внешние пользователи*.

В Microsoft Lync Server 2013 пользователи в вашей организации могут использовать сообщения и сведения о присутствии для общения с внешними пользователями, а также могут принимать участие в конференциях и веб-конференциях с сотрудниками других организаций и других типов внешних пользователей. Вы также можете поддерживать внешний доступ с мобильных устройств и с помощью корпоративной голосовой связи. Внешние пользователи, которые не являются сотрудниками вашей организации, могут принимать участие в собраниях Lync Server 2013, разрешая анонимным участникам.

Для поддержки обмена сообщениями через брандмауэр организации вы развертываете сервер Lync Server 2013 EDGE в сети периметра (также называемой демилитаризованной зоной, ДМЗ или экранированной подсетью). Пограничный сервер управляет тем, как пользователи за пределами межсетевого экрана могут подключаться к внутренней среде Lync Server 2013. Она также управляет связью с внешними пользователями, исходящие из брандмауэра.

В зависимости от ваших требований вы можете развернуть один или несколько пограничных серверов в одном или нескольких расположениях. В этом разделе описаны сценарии для внешних пользователей Access в Lync Server 2013, а также объясняется, как спланировать пограничный и обратную топологию прокси-сервера.

<div>


> [!NOTE]  
> Несмотря на то что вам нужен пограничный сервер для поддержки корпоративного голосовой связи и доступа внешних пользователей, в этом разделе рассматриваются вопросы поддержки обмена мгновенными сообщениями, присутствия, интеграции, веб-конференций и Lync Mobile. Подробные сведения о поддержке корпоративной голосовой связи можно найти <A href="lync-server-2013-planning-for-enterprise-voice.md">в разделе Планирование корпоративной голосовой связи в Lync Server 2013</A> в документации по планированию.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Изменения Lync Server 2013, затрагивающие планирование пограничного сервера](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Системные требования для компонентов доступа внешних пользователей для Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Обзор доступа внешних пользователей в Lync Server 2013](lync-server-2013-overview-of-external-user-access.md)

  - [Общие сведения о автообнаружения в Lync Server 2013](lync-server-2013-understanding-autodiscover.md)

  - [Выбор топологии в Lync Server 2013](lync-server-2013-choosing-a-topology.md)

  - [Сбор данных в Lync Server 2013](lync-server-2013-data-collection.md)

  - [Определение требований DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Определение требований к внешнему брандмауэру аудио- и видеосвязи и портам для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Планирование сертификатов пограничного сервера в Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

