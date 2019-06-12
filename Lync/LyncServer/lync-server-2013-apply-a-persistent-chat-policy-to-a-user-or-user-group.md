---
title: 'Lync Server 2013: применение политики сохраняемого чата к пользователю или группе пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7a2fbed0a752c1bf97bab5a4f67fadf12d8077a6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849767"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a>Применение политики сохраняемого чата к пользователю или группе пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-06_

Если у пользователя есть разрешение на доступ к Lync Server 2013, вы можете применять соответствующие политики к определенным пользователям, чтобы включить или отключить их для постоянного сервера чата.

<div>


> [!NOTE]  
> Чтобы настроить и использовать сохраняемый сервер чата, необходимо сначала использовать Topology Builder, чтобы добавить в топологию постоянную поддержку сервера чата, а затем опубликовать топологию. Подробные сведения о том, <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">как добавить сохраняемый сервер чата в развертывание в среде Lync server 2013, можно</A> найти в документации по развертыванию.<BR>Чтобы настроить параметры конфигурации сервера для сохраняемого чата, ознакомьтесь с разстройкой <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Параметры сервера сохраняемого чата глобально или для постоянного пула серверов чатов в Lync server 2013</A> в документации по развертыванию.



</div>

С помощью описанной в этом разделе процедуры примените ранее созданную политику постоянного чата к одной или нескольким учетным записям пользователей или группам пользователей.

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Применение политики пользователя сохраняемого чата к учетной записи пользователя

1.  Войдите в систему на любом компьютере во внутреннем развертывании с помощью учетной записи пользователя, которому назначена роль CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.

2.  В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администратора. Дополнительные сведения о различных способах запуска панели управления Lync Server можно найти в разделе [Открытие средства администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации нажмите **Пользователи** и выполните поиск учетной записи, которую вы хотите настроить.

4.  В таблице с результатами поиска выберите нужную учетную запись, нажмите кнопку **Изменить** и выберите пункт **Показать сведения**.

5.  В диалоговом окне **изменение пользователя Lync Server** в разделе **Политика сохраняемого чата**выберите политику пользователей сохраняемого чата, которую вы хотите применить.
    
    <div>
    

    > [!NOTE]  
    > Автоматические параметры применяются к действующей политике по умолчанию. <STRONG> &lt;&gt; </STRONG> Данные параметры автоматически применяются сервером.

    
    </div>

6.  Нажмите **Исполнить**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

