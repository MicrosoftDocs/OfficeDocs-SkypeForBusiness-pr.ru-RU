---
title: 'Lync Server 2013: развертывание серверов-посредников и определение одноранговых узлов'
description: 'Lync Server 2013: развертывание серверов-посредников и определение одноранговых узлов.'
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
ms.openlocfilehash: fc3afce038371920beea1cc52549d8d027429e08
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545235"
---
# <a name="deploying-mediation-servers-and-defining-peers-in-lync-server-2013"></a>Развертывание серверов-посредников и определение одноранговых узлов в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Рабочая нагрузка корпоративной голосовой связи, Конференц-связь с телефонным подключением и расширенные приложения для корпоративной голосовой связи (приложение группы ответа, приложение парковки вызовов, контроль допуска звонков и т. д.) доступны в интерфейсных пулах. В Lync Server 2013 функциональные возможности сервера-посредника встроены в интерфейсный сервер. Отдельный изолированный сервер-посредник больше не нужен. Интерфейсные пулы могут напрямую связываться с поддерживаемыми шлюзами (шлюзом телефонной сети общего пользования (PSTN) или IP-УАТС), что отменяет потребность сервера-посредника в качестве посредника.

Единственное исключение из данного правила — настройка магистрали SIP для подключения к пограничному контроллеру сеансов для поставщика услуг интернет-телефонии. Чтобы подключить инфраструктуру корпоративной голосовой связи к поставщику магистрали SIP, необходимо развернуть отдельный сервер-посредник.

Подключение между Lync Server (компонент сервера-посредника в интерфейсном пуле или на изолированном сервере-посреднике) и шлюз определяется как логическая связь, называемая *магистральной*линией. В этом разделе даны инструкции по определению магистрали и развертыванию отдельного сервера-посредника при подключении к магистрали SIP.

<div>

## <a name="in-this-section"></a>Содержание

  - [Определение сервера-посредника в построителе топологий в Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md)

  - [Определение шлюза в построителе топологий в Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md)

  - [Установка файлов для сервера-посредника в Lync Server 2013](lync-server-2013-install-the-files-for-mediation-server.md)

  - [Определение дополнительных магистральных линий в построителе топологий в Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md)

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

