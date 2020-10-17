---
title: Перемещение нескольких пользователей в пилотный пул
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Move multiple users to the pilot pool
ms:assetid: 9492797f-2a26-4773-8ad2-97cb53fa68fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688143(v=OCS.15)
ms:contentKeyID: 49733745
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ffd0fbebffea5553cc461f71cf67843dae0a8ae6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500226"
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

Можно переместить несколько пользователей из пула Office Communications Server 2007 R2 в пилотный пул Lync Server 2013 с помощью панели управления Lync Server 2013 или консоли управления Lync Server 2013.

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-control-panel"></a>Перемещение нескольких пользователей с помощью панели управления Lync Server 2013

1.  Откройте **Панель управления Lync Server**.

2.  На вкладке **Поиск пользователей** щелкните кнопку **Поиск**.

3.  Затем щелкните **Добавить фильтр**.

4.  Создайте фильтр, в котором для параметра **Пользователь Office Communications Server** установлено значение **True**.

5.  Нажмите кнопку **найти** , чтобы найти устаревших пользователей Office Communications Server 2007 R2.

6.  Выберите двух пользователей, которых нужно переместить в пул Lync Server 2013. В этом примере мы переместим пользователей Chen Yang и Claus Hansen.
    
    ![Список пользователей, отображаемый при поиске пользователей OCS](images/JJ688143.76beb4fa-72e0-41ef-b96e-3553e96645c0(OCS.15).jpg "Список пользователей, отображаемый при поиске пользователей OCS")  

7.  В меню **Макрокоманда** выберите **Переместить выбранных пользователей в пул**.

8.  В раскрывающемся списке выберите пул Lync Server 2013.

9.  Щелкните **Макрокоманда** и затем выберите **Переместить выбранных пользователей в пул**. Нажмите кнопку "ОК".
    
    ![Диалоговое окно "перемещение пользователей" и "целевой пул регистратора"](images/JJ205401.8a375003-dc00-4541-b578-4d88f2010601(OCS.15).png "Диалоговое окно "перемещение пользователей" и "целевой пул регистратора"")  

10. Убедитесь, что столбец **пул регистратора** для пользователей теперь содержит пул Lync Server 2013, указывающий, что пользователи успешно перемещены.

</div>

<div>

## <a name="to-move-multiple-users-by-using-the-lync-server-2013-management-shell"></a>Перемещение нескольких пользователей с помощью командной консоли Lync Server 2013

1.  Откройте консоль управления Lync Server 2013.

2.  В командной строке введите следующую команду и замените **Пользователь1** и **Пользователь2** на конкретные имена пользователей, которые требуется переместить и заменить ** \_ полным доменным именем пула** на имя целевого пула. В этом примере мы переместим пользователей Hao Chen и Katie Jordan.
    
        Get-CsUser -Filter {DisplayName -eq "User1" -or DisplayName - eq "User2"} | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Пример командлета для перемещения устаревшего пользователя](images/JJ688143.57cfc28e-3df5-459f-83ef-8b0edf182a25(OCS.15).jpg "Пример командлета для перемещения устаревшего пользователя")  

3.  В командной строке введите следующую команду
    
        Get-CsUser -Identity "User1"

4.  Теперь удостоверение **пула регистратора** должно указывать на пул, указанный в предыдущем шаге в качестве ** \_ полного доменного имени пула** . Присутствие этого удостоверения подтверждает, что пользователь успешно перемещен. Повторите этот шаг, чтобы убедиться, что пользователь **User2** перемещен.
    
    ![Выходные данные командлета PowerShell Get-UsUser — Identity](images/JJ205096.8ff04c67-37a0-4156-bfbc-28f9f7b137c8(OCS.15).jpg "Выходные данные командлета PowerShell Get-UsUser — Identity")  

</div>

<div>

## <a name="to-move-all-users-at-the-same-time-by-using-the-lync-server-2013-management-shell"></a>Перемещение всех пользователей одновременно с помощью командной консоли Lync Server 2013

В этом примере все пользователи возвращены в пул Office Communications Server 2007 R2 (pool01.contoso.net). С помощью командной консоли Lync Server 2013 мы одновременно перейдем всех пользователей в пул Lync Server 2013 (pool02.contoso.net).

1.  Откройте **консоль управления Lync Server 2013**.

2.  Введите в командной строке следующую команду:
    
        Get-CsUser -OnOfficeCommunicationServer | Move-CsLegacyUser -Target "pool_FQDN"
    
    ![Пример командлета для перемещения всех пользователей прежних версий в пул](images/JJ688143.e6a2d578-296e-476c-bd45-d757917ea853(OCS.15).jpg "Пример командлета для перемещения всех пользователей прежних версий в пул")  

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

