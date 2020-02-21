---
title: Перемещение одного пользователя в пилотный пул
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Move a single user to the pilot pool
ms:assetid: 80d5b365-f153-4c61-a148-f9e18ce6e027
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688109(v=OCS.15)
ms:contentKeyID: 49733708
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 20f4e85c2f34a2e4319b14f310d2a9360cb274d1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189898"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="move-a-single-user-to-the-pilot-pool"></a>Перемещение одного пользователя в пилотный пул

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-28_

Вы можете переместить пользователя из пула Office Communications Server 2007 R2 в пилотный пул Lync Server 2013 с помощью панели управления Lync Server 2013 или консоли управления Lync Server 2013. В приведенном ниже примере в столбце пул регистратора ** \<Office Communications Server\> ** является пулом Office Communications Server 2007 R2, а все шесть этих пользователей подключены к этому пулу. Используйте следующие процедуры для перемещения пользователя в пул Lync Server 2013 с помощью панели управления Lync Server 2013 и командной консоли Lync Server.

![Поиск пользователей OCS в панели управления Lync Server](images/JJ688109.d2008fd6-868b-4f26-84cf-57bb69e073d3(OCS.15).jpg "Поиск пользователей OCS в панели управления Lync Server")

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-control-panel"></a>Перемещение пользователя с помощью панели управления Lync Server 2013

1.  Войдите на сервер переднего плана с использованием учетной записи, входящей в группу RTCUniversalServerAdmins или связанной с административной ролью CsAdministrator или CsUserAdministrator.

2.  Откройте Панель управления Lync Server.

3.  Щелкните **Пользователи**.

4.  На вкладке **Поиск пользователей** щелкните кнопку **Поиск**.

5.  Затем щелкните **Добавить фильтр**.

6.  Создайте фильтр, в котором для параметра **Пользователь Office Communications Server** установлено значение **True**.

7.  Нажмите кнопку **найти** , чтобы найти устаревших пользователей Office Communications Server 2007 R2.
    
    ![Поиск пользователей OCS в панели управления Lync Server](images/JJ688109.09528349-7915-41e1-91b4-6ab5c12b1b38(OCS.15).jpg "Поиск пользователей OCS в панели управления Lync Server")  

8.  Выберите пользователя, которого нужно переместить в пул Lync Server 2013. В данном примере мы перемещаем пользователя с именем Sara Davis.

9.  В меню **Действие** выберите команду **Переместить выбранных пользователей в пул**.

10. В раскрывающемся списке выберите пул Lync Server 2013.

11. Щелкните **Действие** и выберите **Переместить выбранных пользователей в пул**. Нажмите кнопку **ОК**.
    
    ![Настройка конечного пула в диалоговом окне "перемещение пользователей"](images/JJ688109.d7dc0759-87c5-4c23-938f-361576621504(OCS.15).jpg "Настройка конечного пула в диалоговом окне "перемещение пользователей"")  

12. Убедитесь, что столбец **пул регистратора** для пользователя теперь содержит пул Lync Server 2013, указывающий, что пользователь успешно перемещен

</div>

<div>

## <a name="to-move-a-user-by-using-the-lync-server-2013-management-shell"></a>Перемещение пользователя с помощью командной консоли Lync Server 2013

1.  Откройте командную консоль Lync Server.

2.  В командной строке введите следующую команду:
    
        Move-CsLegacyUser -Identity "David Pelton" -Target "pool02.contoso.net"

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

