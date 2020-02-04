---
title: 'Lync Server 2013: Настройка управления допуском звонков'
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
ms.openlocfilehash: 62f6858aa84309a268e8fc55af6cc0a63e6010a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757793"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-call-admission-control-in-lync-server-2013"></a>Настройка управления допуском звонков в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-21_

Система контроля допуска звонков обеспечивает проверку возможности установления сеанса связи в реальном времени без ухудшения качества видео- и голосовой связи в перегруженных сетях. Управление трафиком в реальном времени осуществляется только для звуковых и видеофайлов и не влияет на трафик данных. CAC может перенаправлять Звонок через Интернет-путь, если путь к глобальной сети по умолчанию не имеет необходимой пропускной способности. Подробнее смотрите в разделе [Планирование управления допуском звонков в Lync Server 2013](lync-server-2013-planning-for-call-admission-control.md) в документации по планированию.

В этом разделе представлен набор примеров процедур, демонстрирующих способы развертывания и управления CAC в сети.

<div>


> [!IMPORTANT]  
> Перед развертыванием CAC необходимо собрать все необходимые данные для топологии корпоративной сети, как описано в <A href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">примере. сбор требований для управления допуском звонков в Lync Server 2013</A> в документации по планированию. Кроме того, убедитесь, что компоненты CAC установлены и активированы, как описано в разделе <A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Определение и Настройка внешнего пула и сервера Standard Edition в Lync server 2013</A> в документации по развертыванию.



</div>

<div>


> [!NOTE]  
> Все примеры развертывания и управления CAC в этом разделе выполняются с помощью командной консоли Lync Server Management Shell. Кроме того, вы можете использовать раздел " <STRONG>Настройка сети</STRONG> " панели управления Lync Server для управления CAC.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка регионов сети для CAC в Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md)

  - [Создание профилей политики пропускной способности в Lync Server 2013](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [Настройка сетевых сайтов для CAC в Lync Server 2013](lync-server-2013-configure-network-sites-for-cac.md)

  - [Связывание подсетей с сетевыми сайтами для CAC в Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [Создание ссылок на сетевой регион в Lync Server 2013](lync-server-2013-create-network-region-links.md)

  - [Создание маршрутов между межсетевыми регионах в Lync Server 2013](lync-server-2013;-create-network-interregion-routes.md)

  - [Создание политик межсайтовой сети в Lync Server 2013](lync-server-2013-create-network-intersite-policies.md)

  - [Включение управления допуском звонков в Lync Server 2013](lync-server-2013-enable-call-admission-control.md)

  - [Контрольный список развертывания управления допуском звонков для Lync Server 2013](lync-server-2013-call-admission-control-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

