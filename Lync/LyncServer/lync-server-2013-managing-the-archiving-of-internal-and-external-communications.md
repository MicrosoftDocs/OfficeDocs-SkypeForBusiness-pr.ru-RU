---
title: Управление архивацией внутренних и внешних коммуникаций
description: Управление архивацией внутренних и внешних коммуникаций.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 857e4772d93ead01c3914b2ee04b71bddb1feed4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564135"
---
# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a>Управление архивацией внутренних и внешних коммуникаций в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-09_

В Lync Server 2013 политики архивирования используются для включения и отключения архивации для внутренних коммуникаций и внешних коммуникаций, если вы не используете интеграцию с Microsoft Exchange или у вас нет пользователей, которые не размещены в Exchange 2013 с их почтовыми ящиками на In-Place удержания. Доступны следующие политики архивации:

  - Глобальная политика, которая создается по умолчанию при развертывании Lync Server 2013.

  - Политики на уровне сайта и пользователя (необязательные), которые можно создать и использовать для указания параметров архивации для определенных сайтов или пользователей.

Первичная настройка политик архивации выполняется при развертывании архивации, однако изменение, добавление и удаление политик доступно только после развертывания. В панели управления Lync Server 2013 вы можете использовать страницу **Политика архивации** в группе **Архивация и мониторинг** для управления политиками на глобальном уровне, уровне сайта и на уровне пользователя. Если вы интегрируете хранилище Lync Server с хранилищем Exchange 2013, политики пользователей Exchange имеют приоритет над политиками архивации Lync Server 2013.

Для получения дополнительных сведений о реализации политик, включая иерархию политик, ознакомьтесь с [разработкой архивов в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по операциям.

<div>


> [!NOTE]
> Для управления реализацией архивации необходимо указать параметры в конфигурациях архивации, например, задающие архивацию обмена мгновенными сообщениями или конференц-связи, использование критического режима и параметры очистки. По умолчанию в глобальной конфигурации архивации и во всех конфигурациях архивации на уровне сайта и на уровне пула не включен ни один параметр. Перед включением архивации для внутренних или внешних коммуникаций в политиках архивации необходимо указать все соответствующие параметры в конфигурациях архивации. Дополнительные сведения: <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Управление параметрами конфигурации архивации в Lync Server 2013 для Организации, сайтов и пулов</A> в документации по операциям.<BR>Если вы включаете интеграцию Microsoft Exchange для развертывания, политики Exchange контролируют, включена ли архивация для пользователей, размещенных в Exchange 2013, и почтовые ящики помещаются на In-Place удержание. Дополнительные сведения: <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Создание политики архивации в Lync Server 2013 для включения или отключения архивации внутренних или внешних коммуникаций для определенных сайтов или пользователей](lync-server-2013-create-archiving-policy-sites-users.md)

  - [Изменение политики архивации в Lync Server 2013 для включения или отключения архивации внутренних или внешних коммуникаций для Организации, сайтов или пользователей](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [Применение политики архивации к пользователям в Lync Server 2013](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [Настройка политик архивации в Lync Server 2013 при использовании интеграции с Exchange Server](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [Удаление политики архивации в Lync Server 2013](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

