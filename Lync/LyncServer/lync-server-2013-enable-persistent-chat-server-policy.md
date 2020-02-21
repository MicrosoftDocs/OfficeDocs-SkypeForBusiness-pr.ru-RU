---
title: 'Lync Server 2013: Включение политики сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2bfc0f8ed1160d29eb68fc00172c77b466692327
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42187892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>Включение политики сервера сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-06_

В панели управления Lync Server 2013 вы можете использовать страницу **Политика сохраняемого** чата для группы **сохраняемого чата** для управления политиками на глобальном уровне, уровне пула, сайта или пользователя, включая настройку глобальной политики по умолчанию и создание одной или нескольких дополнительных политик для пользователей и сайтов для развертывания. Если для пользователя включена политика для сервера сохраняемого чата, среда сервера сохраняемого чата отображается в своем клиенте Lync 2013.

<div>


> [!NOTE]  
> В топологии политики сайта сервера сохраняемого чата применяются глобально, на пул пользователей или на сайт пользователя или на каждого пользователя.



</div>

Глобальная политика создается автоматически при развертывании сервера сохраняемого чата и может быть настроена, но не удалена. Поскольку глобальная политика применяется ко всем пользователям, ее не требуется задавать для отдельных пользователей.

Вы можете создать и настроить несколько политик сайтов и пользователей, которые вместе с глобальной политикой позволяют пользователям использовать сервер сохраняемого чата. Политики сервера сохраняемого чата для пула и сайта переопределяют глобальную политику сервера сохраняемого чата, но только для пользователей этого сайта. Политики пользователей переопределяют как глобальную политику, так и политики пулов и сайтов для тех пользователей, кому назначены такие политики пользователей.

<div>


> [!NOTE]  
> Чтобы настроить и использовать сервер сохраняемого чата, сначала необходимо использовать построитель топологий, чтобы добавить в топологию поддержку сервера сохраняемого чата, а затем опубликовать топологию. Дополнительные сведения см. в статье <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Добавление сервера сохраняемого чата в развертывание в Lync Server 2013</A> в документации по развертыванию.



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Настройка глобальной политики для сохраняемого чата в Lync Server 2013](lync-server-2013-configure-the-global-policy-for-persistent-chat.md)

  - [Создание политики сайта для сохраняемого чата в Lync Server 2013](lync-server-2013-create-a-site-policy-for-persistent-chat.md)

  - [Создание пользовательской политики для сохраняемого чата в Lync Server 2013](lync-server-2013-create-a-user-policy-for-persistent-chat.md)

  - [Применение политики сохраняемого чата к пользователю или группе пользователей в Lync Server 2013](lync-server-2013-apply-a-persistent-chat-policy-to-a-user-or-user-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

