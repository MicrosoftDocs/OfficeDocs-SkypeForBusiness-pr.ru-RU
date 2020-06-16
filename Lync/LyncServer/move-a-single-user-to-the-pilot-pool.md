---
title: Перемещение одного пользователя в пилотный пул
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: e9de81a8-40dd-4446-81e7-a2b810eaea50
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205401(v=OCS.15)
ms:contentKeyID: 48185905
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f3bd233f610d340c1854cf18337183e5f988426
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755843"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Перемещение одного пользователя в пилотный пул

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-26_

Вы можете переместить пользователя из пула Lync Server 2010 в пилотный пул Lync Server 2013 с помощью панели управления Lync Server 2013 или консоли управления Lync Server 2013. В приведенном ниже примере в столбце пул регистратора **pool01.contoso.NET** — пул Lync Server 2010, а все шесть этих пользователей подключены к этому пулу. Используйте следующие процедуры для перемещения пользователя в пул Lync Server 2013 с помощью панели управления Lync Server 2013 и командной консоли Lync Server.

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Перемещение пользователя с помощью панели управления Lync Server 2013

**Список пользователей в панели управления Lync Server 2013**

![Панель управления Lync Server, диалоговое окно перемещения пользователя](images/JJ721870.a2bce284-0392-4db3-9bb2-9f12699738e7(OCS.15).jpg "Панель управления Lync Server, диалоговое окно перемещения пользователя")

1.  Войдите на сервер переднего плана с помощью учетной записи, являющейся членом группы RTCUniversalServerAdmins или членом административной роли CsAdministrator или CsUserAdministrator.

2.  Откройте **Панель управления Lync Server**.

3.  Щелкните **Пользователи**, затем выберите поиск и нажмите кнопку **Найти**.

4.  Выберите пользователя, которого нужно переместить в пул Lync Server 2013. В данном примере мы перемещаем пользователя с именем Sara Davis.

5.  В меню **Действие** выберите команду **Переместить выбранных пользователей в пул**.

6.  В раскрывающемся списке выберите пул Lync Server 2013.

7.  Щелкните **Действие** и выберите **Переместить выбранных пользователей в пул**. Нажмите кнопку **ОК**.
    
    ![Диалоговое окно "перемещение пользователей" и "целевой пул регистратора"](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Диалоговое окно "перемещение пользователей" и "целевой пул регистратора"")  

8.  Убедитесь, что столбец **пул регистратора** для пользователя теперь содержит пул Lync Server 2013, указывающий, что пользователь успешно перемещен.

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Перемещение пользователя с помощью командной консоли Lync Server 2013

1.  Откройте командную консоль Lync Server.

2.  В командной строке введите следующую команду:
    
        Move-CsUser -Identity "David Pelton" -Target "pool02.contoso.net"

3.  Затем в командной строке введите следующую команду:
    
        Get-CsUser -Identity "David Pelton"

4.  Удостоверение **RegistrarPool** теперь указывает на пул Lync Server 2013. Наличие этого идентификатора подтверждает успешное перемещение пользователя.
    
    ![Выходные данные командлета Get – CsUser с фильтром Identity](images/JJ205401.bc5d4672-8068-4475-b882-dbd305c801a9(OCS.15).jpg "Выходные данные командлета Get – CsUser с фильтром Identity")  
    
    <div>
    

    > [!NOTE]  
    > Для получения сведений о командлете <STRONG>Get-CsUser</STRONG> выполните следующую команду: <STRONG>Get-Help Get-CsUser –Detailed</STRONG>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

