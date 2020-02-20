---
title: 'Lync Server 2013: Настройка и назначение политик архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7db876d03f7322fae5f3a55f88708fe4165a20ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a>Настройка и назначение политик архивации в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

В Lync Server 2013 вы используете политики для включения и отключения архивации для внутренних коммуникаций и внешних коммуникаций для пользователей, размещенных в Lync Server 2013. Доступны следующие политики архивации:

  - Глобальная политика, которая создается по умолчанию при развертывании Lync Server 2013.

  - Политики на уровне сайта и пользователя (необязательные), которые можно создать и использовать для указания параметров архивации для определенных сайтов или пользователей.

Первичная настройка политик архивации выполняется при развертывании архивации, однако изменение, добавление и удаление политик доступно только после развертывания. В панели управления Lync Server 2013 вы можете использовать страницу **Политика архивации** в группе **Архивация и мониторинг** для управления политиками на глобальном уровне, уровне сайта и на уровне пользователя.

<div>


> [!NOTE]  
> Для управления реализацией архивации необходимо указать параметры в конфигурациях архивации, например, задающие архивацию обмена мгновенными сообщениями или конференц-связи, использование критического режима и параметры очистки. По умолчанию в глобальной конфигурации архивации и во всех конфигурациях архивации на уровне сайта и на уровне пула не включен ни один параметр. Перед включением архивации для внутренних или внешних коммуникаций в политиках архивации необходимо указать все соответствующие параметры в конфигурациях архивации. Дополнительные сведения: <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов</A> в документации по операциям.<BR>Если вы интегрируете хранилище Lync Server с хранилищем Exchange 2013, то политики пользователей Exchange имеют приоритет над политиками архивации Lync Server 2013, но только для тех пользователей, которые размещены в Exchange Server 2013, для которых их почтовые ящики размещаются на хранение на месте.



</div>

Для получения дополнительных сведений о реализации политик, включая иерархию политик, ознакомьтесь с [разработкой архивов в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям. Дополнительные сведения об управлении политиками после развертывания приведены в статье [Управление архивацией внутренних и внешних коммуникаций в Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) в документации по операциям.

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка глобальной политики для архивации в Lync Server 2013](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Настройка политик сайта для архивации в Lync Server 2013](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Настройка политик архивации для пользователей в Lync Server 2013](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

