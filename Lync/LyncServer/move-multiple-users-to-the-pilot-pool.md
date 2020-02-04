---
title: Перемещение нескольких пользователей в пилотный пул
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 90d0590c-922c-4933-b778-9dd850b59310
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205096(v=OCS.15)
ms:contentKeyID: 48184838
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8e347658d73405d7125eb439daff7eeb84e6ea7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="move-multiple-users-to-the-pilot-pool"></a>Перемещение нескольких пользователей в пилотный пул

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-02_

Вы можете переместить нескольких пользователей из пула Lync Server 2010 на сервер Lync Server 2013 для пилотного пула с помощью панели управления Lync Server 2013 или консоли управления Lync Server 2013.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Перемещение нескольких пользователей с помощью панели управления Lync Server 2013

1.  Откройте **Панель управления Lync Server**.

2.  Нажмите **Пользователи**, затем "Поиск" и **Найти**.

3.  Выберите двух пользователей, которых вы хотите переместить в пул Lync Server 2013. В этом примере мы перейдем пользователей Чена Маслов и предложения Хансен.
    
    ![Перемещение пользователей в определенную группу регистров](images/JJ205096.70d510e1-8e6b-40a5-a80b-27cbc63fc337(OCS.15).jpg "Перемещение пользователей в определенную группу регистров")  

4.  В меню **действия** выберите пункт **переместить выбранных пользователей в пул**.

5.  В раскрывающемся списке выберите пул Lync Server 2013.

6.  Нажмите **Макрокоманда** и затем **Переместить выбранных пользователей в пул**. Нажмите OK.
    
    ![Перемещение пользователей, диалоговое окно «пул конечных регистраторов»](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Перемещение пользователей, диалоговое окно «пул конечных регистраторов»")  

7.  Убедитесь в том, что столбец **пула регистратора** для пользователей теперь содержит пул Lync Server 2013, указывающий на то, что пользователи успешно перемещены.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Перемещение нескольких пользователей с помощью управляющей оболочки Lync Server 2013

1.  Откройте консоль управления Lync Server 2013.

2.  В командной строке введите следующую команду и замените **Пользователь1** и **Пользователь2** именами пользователей, которым вы хотите переместить и заменить **FQDN пула\_** именем конечного пула. В этом примере мы перейдем пользователей Хао Чен и Katie Иордания.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsUser -Target "pool_FQDN"
    
    ![Пример командлета Get-CsUser PowerShell](images/JJ205096.767ff9fc-755d-4a80-a710-5b1367aecbe0(OCS.15).jpg "Пример командлета Get-CsUser PowerShell")  

3.  В командной строке введите следующую команду:
    
        Get-CsUser -Identity "User1"

4.  Удостоверение **пула регистратора** теперь должно указывать на пул, указанный в предыдущем шаге, в качестве **\_полного доменного имени пула** . Присутствие этого удостоверения подтверждает, что пользователь успешно переместился. Повторите действия, чтобы проверить, был ли перемещен **Пользователь2** .
    
    ![Вывод командлета PowerShell Get-Усусер-Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Вывод командлета PowerShell Get-Усусер-Identity")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Перемещение всех пользователей одновременно с помощью управляющей оболочки Lync Server 2013

В этом примере все пользователи возвращены в пул Lync Server 2010 (pool01.contoso.net). С помощью командной консоли Lync Server 2013 мы одновременно перейдем всех пользователей к группе Lync Server 2013 (pool02.contoso.net).

1.  Откройте **консоль управления Lync Server 2013**.

2.  В командной строке введите следующую команду:
    
        Get-CsUser -OnLyncServer | Move-CsUser -Target "pool_FQDN"
    
    ![Командлет PowerShell и результаты в командной консоли](images/JJ205096.1e57ccb1-9378-4dc7-82b7-dcaa63a285c6(OCS.15).png "Командлет PowerShell и результаты в командной консоли")  

3.  Затем выполните **Get-CsUser** для одного из пилотных пользователей.
    
        Get-CsUser -Identity "Hao Chen"

4.  Удостоверение **пула регистраторов** для каждого пользователя теперь указывает на пул, указанный в предыдущем шаге\_в качестве полного доменного имени пула. Присутствие этого удостоверения подтверждает, что пользователь успешно переместился.

5.  Кроме того, вы можете просмотреть список пользователей на панели управления Lync Server 2013 и убедиться, что значение пула регистратора теперь указывает на пул Lync Server 2013.
    
    ![Список пользователей панели управления Lync Server 2013](images/JJ205096.3f2e87a7-ec59-43c5-82cb-e770108bfb04(OCS.15).jpg "Список пользователей панели управления Lync Server 2013")  

</div>

</div>

<span> </span>

</div>

</div>

</div>

