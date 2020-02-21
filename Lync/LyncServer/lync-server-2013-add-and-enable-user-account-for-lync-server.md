---
title: 'Lync Server 2013: Добавление и включение учетной записи пользователя для Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Add and enable user account for Lync Server
ms:assetid: 1edd1c1c-307d-450b-abea-33aaf56bdf13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520961(v=OCS.15)
ms:contentKeyID: 48183578
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 24fe3004f588f50edbcb9428d8bece7a4b20a28a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="add-and-enable-user-account-for-lync-server-2013"></a>Добавление и включение учетной записи пользователя для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-02_

После включения учетной записи пользователя в оснастке "Active Directory — пользователи и компьютеры" можно использовать панель управления Lync Server для создания и включения новых учетных записей пользователей Lync Server 2013, добавив пользователя Active Directory в Lync Server.

<div>

## <a name="to-add-and-enable-a-new-lync-server-user"></a>Добавление и включение нового пользователя Lync Server

1.  Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните элемент **Users** (Пользователи).

4.  Щелкните элемент **Enable users** (Разрешить пользователей).

5.  В диалоговом окне **New Lync Server User** (Новый пользователь Lync Server) нажмите кнопку **Add** (Добавить).

6.  В поле **Search users** (Поиск пользователей) полностью или частично введите полное имя, отображаемое имя, имя, фамилию, имя учетной записи диспетчера учетных записей безопасности, адрес электронной почты, имя участника-пользователя или номер телефона требуемой учетной записи пользователя Active Directory, а затем нажмите кнопку **Find** (Найти).

7.  В таблице выберите учетную запись, которую нужно добавить на сервер Lync Server, а затем нажмите кнопку **ОК**.

8.  Назначьте пользователя пулу, укажите дополнительные сведения и назначьте пользователю политики, а затем щелкните элемент **Enable** (Разрешить).

</div>

<div>

## <a name="see-also"></a>См. также


[Отключение или повторное включение учетной записи пользователя для Lync Server 2013](lync-server-2013-disable-or-re-enable-user-account-for-lync-server.md)  
[Удаление учетной записи пользователя из Lync Server 2013](lync-server-2013-remove-a-user-account-from-lync-server.md)  


[Включение и отключение пользователей для Lync Server 2013](lync-server-2013-enabling-and-disabling-users-for-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

