---
title: 'Lync Server 2013: Настройка параметров учетных записей пользователей'
description: 'Lync Server 2013: Настройка параметров учетных записей пользователей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e6ab4c57ba3d3e8c084314e1093736334312d0c1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577515"
---
# <a name="configure-user-account-settings-in-lync-server-2013"></a>Настройка параметров учетных записей пользователей в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-05_

Для присоединения к конференции в качестве пользователей, прошедших проверку подлинности, пользователи конференц-связи с телефонным подключением вводят номера телефонов или добавочные номера и ПИН-код. Для проверки подлинности необходим URI телефонной **линии** , указанный в учетных записях пользователей Lync Server.

В этом разделе описывается назначение **Line URI** (URI линии) отдельной учетной записи пользователя. Чтобы назначить **Line URI** (URI линии) нескольким учетным записям пользователей, создайте сценарий, использующий командлет **Set-CsUser**. Для получения дополнительных сведений об использовании примера сценария для назначения **универсального кода ресурса (URI)** для нескольких учетных записей пользователей, в разделе "Назначение URI строк нескольким пользователям" [https://go.microsoft.com/fwlink/p/?linkId=196945](https://go.microsoft.com/fwlink/p/?linkid=196945) .

<div>

## <a name="to-configure-user-account-settings"></a>Настройка параметров учетной записи пользователя

1.  Выполните вход на компьютер с учетной записью члена группы RTCUniversalServerAdmins или члена роли **Cs-UserAdministrator** или **CsAdministrator**.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В панели навигации слева щелкните **Users** (Пользователи).

4.  В поле поиска введите имя пользователя, которого нужно настроить для конференц-связи с телефонным подключением, или щелкните **Add filter** (Добавить фильтр), чтобы задать поля поиска, а затем щелкните **Find** (Поиск).

5.  Дважды щелкните имя пользователя, чтобы открыть диалоговое окно **изменение пользователя Lync Server** .

6.  В разделе **Telephony** (Телефония) введите уникальный нормализованный номер телефона в поле **Line URI** (URI линии) (пример: tel:+14255550200).
    
    <div>
    

    > [!NOTE]  
    > Вы можете указать <STRONG>URI строки</STRONG> только в том случае, если для параметра <STRONG>Телефония</STRONG> выбрано значение <STRONG>Только с одного ПК на другой</STRONG>, <STRONG>Корпоративная голосовая связь</STRONG>, <STRONG>Удаленное управление звонками</STRONG> или <STRONG>Только удаленное управление звонками</STRONG>.

    
    </div>

7.  Щелкните **Commit** (Применить).

</div>

</div>

<span> </span>

</div>

</div>

</div>

