---
title: 'Lync Server 2013: развертывание единого хранилища контактов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying unified contact store
ms:assetid: 68959d58-ac8a-45de-afcd-b9de2c36799c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204963(v=OCS.15)
ms:contentKeyID: 48184373
ms.date: 06/06/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 94f4c52eb3adda31f32de410f139154788fa37e9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834509"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-unified-contact-store-in-lync-server-2013"></a>Развертывание единого хранилища контактов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2016-06-06_

Для включения единого магазина контактов в Lync Server 2013 не требуется никаких параметров топологии. Чтобы включить единое хранилище контактов для пользователей, необходимо следующее:

  - Включена политика единого магазина контактов (по умолчанию включена).

  - Пользователи, которые входят в состав Lync 2013 хотя бы один раз.

После того как контакты пользователей будут перенесены, что происходит автоматически, когда пользователь входит в систему с помощью Lync 2013, пользователь может получить доступ к своим контактам Lync и управлять ими из Lync 2013, Outlook 2013 или Outlook Web Access. Пользователю не нужно входить в Lync для управления контактами из Outlook или Outlook Web Access.

<div>


> [!IMPORTANT]  
> Если пользователь входит в Lync 2010 после миграции, контакты и группы доступны и обновляются, но пользователи не могут управлять ими (то есть добавлять, удалять, перемещать, помечать, присвоенной или изменять).



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Включение для пользователей единого хранилища контактов в Lync Server 2013](lync-server-2013-enable-users-for-unified-contact-store.md)

  - [Перенос пользователей в единое хранилище контактов в Lync Server 2013](lync-server-2013-migrate-users-to-unified-contact-store.md)

  - [Откат перенесенных пользователей в Lync Server 2013](lync-server-2013-roll-back-migrated-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

