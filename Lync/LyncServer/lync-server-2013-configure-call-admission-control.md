---
title: 'Lync Server 2013: Настройка контроля допуска звонков'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure call admission control
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398870(v=OCS.15)
ms:contentKeyID: 48185464
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad0d297981bec3fe133e88a090a3c60a97f1ec9d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146522"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a>Настройка контроля допуска звонков в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-21_

Контроль допуска звонков (CAC) — это решение, которое определяет, можно ли установить сеанс реального времени на основе доступной полосы пропускания, чтобы предотвратить плохое качество звука и видео для пользователей в перегруженных сетях. CAC управляет трафиком в режиме реального времени только для аудио и видео и не влияет на трафик данных. С помощью функции CAC можно направить вызов через Интернет, если по умолчанию для канала глобальной сети нет необходимой пропускной способности. Дополнительные сведения приведены в статье [Планирование контроля допуска звонков в Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) в документации по планированию.

В этом разделе представлен набор примеров процедур, иллюстрирующих развертывание и Управление CAC в сети.

<div>


> [!IMPORTANT]  
> Перед развертыванием CAC необходимо собрать всю необходимую информацию для топологии корпоративной сети, как описано в <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">примере: сбор требований для контроля допуска звонков в Lync Server 2013</A> в документации по планированию. Кроме того, убедитесь, что компоненты CAC установлены и активированы, как описано в статье <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Определение и Настройка пула переднего плана или сервера Standard Edition в Lync server 2013</A> в документации по развертыванию.



</div>

<div>


> [!NOTE]  
> Все примеры развертывания и управления CAC, описанные в этом разделе, выполняются с помощью командной консоли Lync Server. В качестве альтернативы вы также можете использовать раздел <STRONG>Конфигурация сети</STRONG> в панели управления Lync Server для управления CAC.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка сетевых регионов для CAC в Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)

  - [Создание профилей политики пропускной способности в Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Настройка сетевых сайтов для контроля допуска звонков в Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md)

  - [Связывание подсетей с сетевыми сайтами для контроля допуска звонков в Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Создание связей между областями сети в Lync Server 2013](lync-server-2013-create-network-region-links.md)

  - [Создание маршрутов между межсетевыми областями в Lync Server 2013](lync-server-2013;-create-network-interregion-routes.md)

  - [Создание межсайтовых политик для сети в Lync Server 2013](lync-server-2013-create-network-intersite-policies.md)

  - [Включение контроля допуска звонков в Lync Server 2013](lync-server-2013-enable-call-admission-control.md)

  - [Контрольный список развертывания контроля допуска звонков для Lync Server 2013](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

