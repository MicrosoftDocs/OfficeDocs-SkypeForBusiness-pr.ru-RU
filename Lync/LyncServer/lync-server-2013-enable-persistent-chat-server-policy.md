---
title: 'Lync Server 2013: включение политики сервера сохраняемого чата'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enable Persistent Chat Server policy
ms:assetid: 87063d6c-2e38-4970-b76d-2aa15f0de29e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205056(v=OCS.15)
ms:contentKeyID: 48184718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e58e71cd92182fc9f68d272ba23079677983b399
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834282"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enable-persistent-chat-server-policy-in-lync-server-2013"></a>Включение политики сервера сохраняемого чата в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-06_

На панели управления Lync Server 2013 вы можете управлять политиками на уровне глобального, пула, сайта или пользователя с помощью страницы " **Политика сохраняемого чата** " группы " **сохраняемый чат** ", в том числе настроить глобальную политику по умолчанию и создать одну или несколько Дополнительные политики пользователей и сайтов для развертывания. Если пользователю разрешено ведение постоянного сервера чата с помощью политики, в клиенте Lync 2013 появится среда сервера сохраняемого чата.

<div>


> [!NOTE]  
> В топологии политики сайтов сервера сохраняемого чата применяются глобально, в пул пользователей или на сайт пользователя или на каждого пользователя.



</div>

Глобальная политика создается автоматически при развертывании сервера сохраняемого чата и может быть настроена, но не удалена. Поскольку глобальная политика применяется ко всем пользователям, ее не требуется задавать для отдельных пользователей.

Вы можете создать и настроить несколько политик сайта и пользователей, которые вместе с глобальной политикой позволяют пользователям использовать сохраняемый сервер чата. Политики сервера для работы с сохраненными разчатами для пула и сайтов переопределяют глобальную политику сервера сохраняемого чата, но только для пользователей этого сайта. Политики пользователей переопределяют как глобальную политику, так и политики пулов и сайтов для тех пользователей, кому назначены такие политики пользователей.

<div>


> [!NOTE]  
> Чтобы настроить и использовать сохраняемый сервер чата, необходимо сначала использовать Topology Builder, чтобы добавить в топологию постоянную поддержку сервера чата, а затем опубликовать топологию. Подробные сведения о том, <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">как добавить сохраняемый сервер чата в развертывание в среде Lync server 2013, можно</A> найти в документации по развертыванию.



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

