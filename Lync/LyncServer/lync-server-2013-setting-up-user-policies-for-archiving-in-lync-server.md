---
title: 'Lync Server 2013: Настройка политик пользователей для архивации в Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3921956949f38390277328495398970203993377
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849684"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a>Настройка политик пользователей для архивации в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-10_

Включение и отключение архивации для конкретных пользователей, размещенных на Lync Server 2013, требует создания и настройки одной или нескольких политик пользователей, а затем применения соответствующей политики к определенным пользователям или группам пользователей. Политики пользователей переопределяют сайты и глобальные политики, но только для пользователей, размещенных на Lync Server 2013.

Пользователи всегда будут размещены в Lync Server. Если включена интеграция Microsoft Exchange, то для пользователей, чьи почтовые ящики находятся в Microsoft Exchange Server 2013, они не нуждаются в политиках архивации в Lync Server. Эти пользователи с архивацией будут управляться хранением на месте.

Сведения о том, как работают политики архивации, в том числе иерархия глобальных, сайтов и пользовательских политик, описаны в разделе [Использование архивации в Lync Server 2013](lync-server-2013-how-archiving-works.md) в документации по планированию, документации по развертыванию или документации по эксплуатации.

<div>


> [!NOTE]  
> Если вы включили интеграцию Microsoft Exchange для развертывания, политики хранения на месте Exchange определяют, включено ли архивирование для пользователей, использующих Exchange 2013. Для архивации данных пользователей необходимо, чтобы их почтовые ящики были размещены на месте. Подробности можно найти в разделе <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Настройка политик архивации в Lync server 2013 при использовании интеграции с Exchange Server</A> в документации по развертыванию.<BR>Перед включением архивации необходимо указать все соответствующие параметры в разделе конфигурации архивации. Подробности можно найти <A href="lync-server-2013-configuring-archiving-options.md">в разделе Настройка параметров архивации в Lync Server 2013</A> в документации по развертыванию.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Создание и Настройка политик пользователей для архивации в Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [Применение политики архивации в Lync Server к пользователю в Lync Server 2013](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

