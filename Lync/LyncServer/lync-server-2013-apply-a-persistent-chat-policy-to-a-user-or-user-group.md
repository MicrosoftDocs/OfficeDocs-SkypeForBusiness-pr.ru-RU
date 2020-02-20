---
title: 'Lync Server 2013: применение политики сохраняемого чата к пользователю или группе пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Apply a Persistent Chat policy to a user or user group
ms:assetid: 809ef4e0-8d42-4feb-b7c0-3995f39867a7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205038(v=OCS.15)
ms:contentKeyID: 48184652
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 452028e9fb67443d92e244d2d23c65f4efa9e308
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="apply-a-persistent-chat-policy-to-a-user-or-user-group-in-lync-server-2013"></a>Применение политики сохраняемого чата к пользователю или группе пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-06_

Если для пользователя включена поддержка Lync Server 2013, вы можете применить соответствующие политики к определенным пользователям, чтобы включить или отключить их для сервера сохраняемого чата.

<div>


> [!NOTE]  
> Чтобы настроить и использовать сервер сохраняемого чата, сначала необходимо использовать построитель топологий, чтобы добавить в топологию поддержку сервера сохраняемого чата, а затем опубликовать топологию. Дополнительные сведения см. в статье <A href="lync-server-2013-adding-persistent-chat-server-to-your-deployment.md">Добавление сервера сохраняемого чата в развертывание в Lync Server 2013</A> в документации по развертыванию.<BR>Чтобы настроить параметры конфигурации сервера сохраняемого чата, ознакомьтесь со статьей <A href="lync-server-2013-configure-persistent-chat-server-options-globally-or-for-persistent-chat-server-pool.md">Настройка параметров сервера сохраняемого чата на глобальном уровне или для пула сервера сохраняемого чата в Lync server 2013</A> в документации по развертыванию.



</div>

Используйте процедуру, описанную в этом разделе, для применения ранее созданной политики пользователя сохраняемого чата к одной или нескольким учетным записям пользователей или группам пользователей.

<div>

## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>Применение политики пользователя сохраняемого чата к учетной записи пользователя

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsPersistentChatAdministrator, CsAdministrator или CsUserAdministrator.

2.  В меню **Пуск** выберите Панель управления Lync Server или откройте окно браузера и введите URL-адрес администрирования. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Пользователи**, а затем выполните поиск учетной записи пользователя, которую требуется настроить.

4.  В таблице со списком результатов поиска щелкните учетную запись пользователя, нажмите кнопку **Изменить**, а затем щелкните **Показать подробности**.

5.  В разделе **изменение пользователя Lync Server** в разделе **Политика сохраняемого чата**выберите политику пользователя сохраняемого чата, которую нужно применить.
    
    <div>
    

    > [!NOTE]  
    > Параметры <STRONG> &lt;автоматического&gt; </STRONG> применения применяют действующую политику по умолчанию. Данный параметр автоматически применяется сервером.

    
    </div>

6.  Нажмите кнопку **Сохранить**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

