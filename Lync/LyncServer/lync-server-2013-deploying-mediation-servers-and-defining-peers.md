---
title: 'Lync Server 2013: развертывание серверов-посредников и определение одноранговых узлов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Mediation Servers and defining peers
ms:assetid: a684f1da-6671-4011-adf6-2db49e2528e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412780(v=OCS.15)
ms:contentKeyID: 48185077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b20f5e733dddd34971ca3a5070e99364785e147a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757643"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>Развертывание серверов-посредников и определение одноранговых узлов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Корпоративная рабочая нагрузка, Конференц-связь с телефонным подключением и сложные приложения для корпоративной голосовой связи (приложение группы ответа, приложение для допуска звонков (CAC) и т. д.) можно использовать в пулах интерфейсного сервера. При использовании Lync Server 2013 функциональность сервера обновлений встроена в сервер переднего плана. На отдельном изолированном сервере обновлений больше нет необходимости. Пулы переднего плана могут взаимодействовать непосредственно с поддерживаемыми шлюзами (коммутируемые коммутируемые телефонные сети (PSTN) или IP-УАТС), устраняя необходимость в использовании сервера-посредника для использования в качестве посредника.

Единственным исключением является настройка магистральной магистрали SIP для подключения к контроллеру границ сеанса для поставщика услуг телефонной связи через Интернет. Чтобы подключить корпоративную инфраструктуру голосовой связи к провайдеру магистральной магистрали SIP, необходимо развернуть отдельный сервер-посредник.

Соединение между Lync Server (компонент сервера-посредника в пуле переднего плана или отдельного сервера-посредника) и шлюз определено как логическая связь, называемая *магистральной*. В этом разделе объясняется, как определить магистраль и как развернуть отдельный сервер-посредник, если вы подключаетесь к магистрали SIP.

<div>

## <a name="in-this-section"></a>Содержание

  - [Определение сервера-посредника в построителе топологии в Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Определение шлюза в построителе топологии в Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Установка сервера исправлений в Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Определение дополнительных каналов в построителе топологии в Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)

</div>

<div>

## <a name="related-sections"></a>Связанные разделы

[Настройка конференц-связи с телефонным подключением в Lync Server 2013](lync-server-2013-configuring-dial-in-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

