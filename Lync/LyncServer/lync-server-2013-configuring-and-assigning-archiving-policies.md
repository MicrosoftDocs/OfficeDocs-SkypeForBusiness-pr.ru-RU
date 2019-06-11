---
title: 'Lync Server 2013: Настройка и назначение политик архивации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e8b3b4f1f9465684d7c9139b8cd548caacf91c41
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841289"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a>Настройка и назначение политик архивации в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

В Lync Server 2013 вы используете политики для включения и отключения архивирования для внутренних коммуникаций и внешней связи для пользователей, которые размещены на Lync Server 2013. К ним относятся следующие политики архивации:

  - Глобальная политика, созданная по умолчанию при развертывании Lync Server 2013.

  - Необязательные политики уровня сайта и уровня пользователя, которые можно создавать и использовать для определения способа реализации архивации для конкретных сайтов или пользователей.

Изначально политики архивации были настроены при развертывании архивации, но вы можете изменить, добавить и удалить политики после развертывания. В панели управления Lync Server 2013 вы можете управлять политиками на глобальном уровне, уровне сайта и на уровне пользователей с помощью страницы **политики архивации** в группе **Архивация и мониторинг** .

<div>


> [!NOTE]  
> Чтобы управлять реализацией архивации, необходимо указать параметры в конфигурациях архивации, например, следует ли архивировать сообщения или конференции, использовать критический режим и параметры очистки. По умолчанию параметры не включены в глобальной конфигурации архивации или конфигурации архивации сайта или пула. Прежде чем включать архивирование для внутренних или внешних сообщений в политиках архивации, необходимо задать все соответствующие параметры в параметрах конфигурации архивации. Дополнительные сведения можно найти в разделе <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайты и пулы</A> в документации по эксплуатации.<BR>Если вы интегрирует хранилище данных Lync Server с хранилищем Exchange 2013, политики пользователей Exchange имеют приоритет над политиками архивации Lync Server 2013, но только для тех пользователей, которые подключены к серверу Exchange 2013, на котором были помещены почтовые ящики, на хранение на месте.



</div>

Сведения о том, как реализованы политики, в том числе об иерархии политик, описаны [в разделе Работа с архивацией в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям. Подробнее об управлении политиками после развертывания можно узнать в разделе [Управление архивацией внутренней и внешней связи в Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) в документации по эксплуатации.

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка глобальной политики архивации в Lync Server 2013](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [Настройка политик сайта для архивации в Lync Server 2013](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [Настройка политик архивации для пользователей в Lync Server 2013](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

