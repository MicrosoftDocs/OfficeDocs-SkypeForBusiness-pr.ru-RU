---
title: 'Lync Server 2013: настройка параметров учетных записей пользователей'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure user account settings
ms:assetid: b7c74ecc-b924-4efc-8a56-3a5f94a9ef13
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412896(v=OCS.15)
ms:contentKeyID: 48185200
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4d06405d2f80aef5decb69d564ae399401d4328
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841303"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-user-account-settings-in-lync-server-2013"></a>Настройка параметров учетных записей пользователей в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-05_

Для присоединения к конференции в качестве пользователей, прошедших проверку подлинности, пользователи конференц-связи с телефонным подключением вводят номера телефонов или добавочные номера и ПИН-код. Для проверки подлинности требуется **универсальный код ресурса (URI)** телефонной линии, указанный в учетных записях пользователей Lync Server.

В этом разделе описывается назначение **URI линии** отдельной учетной записи пользователя. Чтобы назначить **URI линии** нескольким учетным записям пользователей, можно создать сценарий, использующий командлет **Set-CsUser**. Подробнее об использовании примера сценария для назначения универсального **кода ресурса (URI)** для нескольких учетных записей пользователей можно узнать в [http://go.microsoft.com/fwlink/p/?linkId=196945](http://go.microsoft.com/fwlink/p/?linkid=196945)разделе "Назначение URI для разных строк нескольким пользователям".

<div>

## <a name="to-configure-user-account-settings"></a>Настройка параметров учетной записи пользователя

1.  Выполните вход на компьютер с учетной записью члена группы RTCUniversalServerAdmins или члена роли **Cs-UserAdministrator** или **CsAdministrator**.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На левой панели навигации щелкните **Пользователи**.

4.  В поле поиска введите имя пользователя, которого нужно настроить для конференц-связи с телефонным подключением, или щелкните **Добавить фильтр**, чтобы задать поля поиска, а затем щелкните **Поиск**.

5.  Дважды щелкните имя пользователя, чтобы открыть диалоговое окно " **изменение пользователя Lync Server** ".

6.  В разделе **Телефония** введите уникальный нормализованный номер телефона в поле **URI линии** (пример: tel:+14255550200).
    
    <div>
    

    > [!NOTE]  
    > Вы можете указать <STRONG>URI линии</STRONG>, только если для параметра <STRONG>Телефония</STRONG> выбрано значение <STRONG>Только с одного ПК на другой</STRONG>, <STRONG>Корпоративная голосовая связь</STRONG>, <STRONG>Удаленное управление звонками</STRONG> или <STRONG>Только удаленное управление звонками</STRONG>.

    
    </div>

7.  Нажмите **Исполнить**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

