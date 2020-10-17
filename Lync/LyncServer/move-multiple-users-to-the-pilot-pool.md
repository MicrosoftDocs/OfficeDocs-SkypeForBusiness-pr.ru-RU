---
title: Перемещение нескольких пользователей в пилотный пул
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be7fd473b858c6a35b23f8aaa0c525875218d3f7
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500236"
---
# <a name="move-multiple-users-to-the-pilot-pool"></a>Перемещение нескольких пользователей в пилотный пул

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-02_

Можно переместить несколько пользователей из пула Lync Server 2010 в пилотный пул Lync Server 2013 с помощью панели управления Lync Server 2013 или консоли управления Lync Server 2013.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Перемещение нескольких пользователей с помощью панели управления Lync Server 2013

1.  Откройте **Панель управления Lync Server**.

2.  Щелкните **Пользователи**, затем выберите поиск и нажмите кнопку **Найти**.

3.  Выберите двух пользователей, которых нужно переместить в пул Lync Server 2013. В этом примере мы переместим пользователей Chen Yang и Claus Hansen.
    
    ![Перемещение пользователей в определенный пул регистров](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Перемещение пользователей в определенный пул регистров")  

4.  В меню **Макрокоманда** выберите **Переместить выбранных пользователей в пул**.

5.  В раскрывающемся списке выберите пул Lync Server 2013.

6.  Щелкните **Макрокоманда** и затем выберите **Переместить выбранных пользователей в пул**. Нажмите кнопку "ОК".
    
    ![Диалоговое окно "перемещение пользователей" и "целевой пул регистратора"](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Диалоговое окно "перемещение пользователей" и "целевой пул регистратора"")  

7.  Убедитесь, что столбец **пул регистратора** для пользователей теперь содержит пул Lync Server 2013, указывающий, что пользователи успешно перемещены.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Перемещение нескольких пользователей с помощью командной консоли Lync Server 2013

1.  Откройте консоль управления Lync Server 2013.

2.  В командной строке введите следующую команду и замените **Пользователь1** и **Пользователь2** на конкретные имена пользователей, которые требуется переместить и заменить ** \_ полным доменным именем пула** на имя целевого пула. В этом примере мы переместим пользователей Hao Chen и Katie Jordan.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![Пример командлета Get-CsUser PowerShell](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Пример командлета Get-CsUser PowerShell")  

3.  В командной строке введите следующую команду
    
        Get-CsUser -Identity "User1"

4.  Теперь удостоверение **пула регистратора** должно указывать на пул, указанный в предыдущем шаге в качестве ** \_ полного доменного имени пула** . Присутствие этого удостоверения подтверждает, что пользователь успешно перемещен. Повторите этот шаг, чтобы убедиться, что пользователь **User2** перемещен.
    
    ![Выходные данные командлета PowerShell Get-UsUser — Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Выходные данные командлета PowerShell Get-UsUser — Identity")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Перемещение всех пользователей одновременно с помощью командной консоли Lync Server 2013

В этом примере все пользователи возвращены в пул Lync Server 2010 (pool01.contoso.net). С помощью командной консоли Lync Server 2013 мы одновременно перейдем всех пользователей в пул Lync Server 2013 (pool02.contoso.net).

1.  Откройте **консоль управления Lync Server 2013**.

2.  Введите в командной строке следующую команду:
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![Командлет PowerShell и результаты в командной консоли](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Командлет PowerShell и результаты в командной консоли")  

3.  Затем выполните командлет **Get-CsUser** для одного из пробных пользователей.
    
        Get-CsUser -Identity "Hao Chen"

4.  Удостоверение **пула регистратора** для каждого пользователя теперь указывает на пул, указанный \_ в предыдущем шаге как "полное доменное имя пула". Наличие этого идентификатора подтверждает успешное перемещение пользователя.

5.  Кроме того, можно просмотреть список пользователей в панели управления Lync Server 2013 и проверить, что значение пула регистратора теперь указывает на пул Lync Server 2013.
    
    ![Список пользователей в панели управления Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Список пользователей в панели управления Lync Server 2013")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

