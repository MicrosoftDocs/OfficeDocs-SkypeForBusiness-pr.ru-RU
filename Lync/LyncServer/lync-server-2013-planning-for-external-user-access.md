---
title: 'Lync Server 2013: Планирование доступа внешних пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for external user access
ms:assetid: ea098933-eff5-461e-aba3-e7f128784dc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399048(v=OCS.15)
ms:contentKeyID: 48185903
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57ff8418c468e2f2d09ca0f072be318fa486f9a4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201945"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-external-user-access-in-lync-server-2013"></a>Планирование доступа внешних пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-01-19_

Коммуникации в большинстве организаций включают службы и пользователей, которые находятся за пределами внутренней сети. Эти службы и пользователи могут быть представлены сотрудниками, временно или постоянно работающими вне офиса, сотрудниками организаций клиентов или партнеров, лицами, использующими общедоступные службы мгновенных сообщений, а также потенциальными клиентами, партнерами и анонимными пользователями, которые были приглашены принять участие в собраниях и презентациях. В данной документации все эти лица называются *внешними пользователями*.

С помощью Microsoft Lync Server 2013 пользователи в организации могут использовать обмен мгновенными сообщениями и сведения о присутствии для связи с внешними пользователями, а также могут участвовать в конференциях аудио-и видеосвязи и конференц-связи с внешними сотрудниками и другими типами внешних пользователей. Кроме того, можно поддерживать внешний доступ с мобильных устройств и с помощью корпоративной голосовой связи. Внешние пользователи, которые не входят в вашу организацию, могут участвовать в собраниях Lync Server 2013, разрешая анонимным участникам.

Для поддержки обмена данными между брандмауэром организации необходимо развернуть пограничный сервер Lync Server 2013 в сети периметра (также известной как DMZ, демилитаризованная зона и экранированная подсеть). Пограничный сервер управляет тем, как пользователи, не входящие в брандмауэр, могут подключаться к внутреннему развертыванию Lync Server 2013. Он также управляет взаимодействием с внешними пользователями, инициированным в границах брандмауэра.

В зависимости от ваших потребностей, можно разворачивать один или несколько пограничных серверов в одном или нескольких расположениях. В этом разделе описываются сценарии доступа внешних пользователей в Lync Server 2013, а также описано, как спланировать пограничный и обратную топологию прокси-сервера.

<div>


> [!NOTE]  
> Несмотря на то, что для поддержки доступа к корпоративной голосовой связи и внешним пользователям необходим пограничный сервер, этот раздел посвящен поддержке мгновенных сообщений, присутствия, аудио-и видеоконференций, Федерации, веб-конференций и Lync Mobile. Подробные сведения о поддержке корпоративной голосовой связи можно найти <A href="lync-server-2013-planning-for-enterprise-voice.md">в статье Планирование корпоративной голосовой связи в Lync Server 2013</A> в документации по планированию.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Изменения в Lync Server 2013, затрагивающие планирование пограничных серверов](lync-server-2013-changes-in-lync-server-that-affect-edge-server-planning.md)

  - [Требования к системе для компонентов доступа внешних пользователей для Lync Server 2013](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [Обзор доступа внешних пользователей в Lync Server 2013](lync-server-2013-overview-of-external-user-access.md)

  - [Общие сведения о службе автообнаружения в Lync Server 2013](lync-server-2013-understanding-autodiscover.md)

  - [Выбор топологии в Lync Server 2013](lync-server-2013-choosing-a-topology.md)

  - [Сбор данных в Lync Server 2013](lync-server-2013-data-collection.md)

  - [Определение требований к DNS для Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Определение требований к внешнему брандмауэру аудио-и видеоданных для Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

  - [Планирование сертификатов пограничного сервера в Lync Server 2013](lync-server-2013-plan-for-edge-server-certificates.md)

  - [Сценарии доступа внешних пользователей в Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

