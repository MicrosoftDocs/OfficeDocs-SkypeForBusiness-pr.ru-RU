---
title: Перенос номеров доступа
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6401d847c2e0993632ad655fb43f07b0a2731ef
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48503556"
---
# <a name="migrate-dial-in-access-numbers"></a>Перенос номеров доступа

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-19_

Для переноса номеров доступа с телефонным подключением с Lync Server 2010 на Lync Server 2013 необходимо запустить командлет **Move – CsApplicationEndpoint** для переноса объектов Contact. В течение периода сосуществования Lync Server 2010 и Lync Server 2013 номера доступа по телефонной линии, созданные в Lync Server 2013, ведут себя так же, как и номера доступа по телефонной линии, созданные в Lync Server 2010, как описано в этом разделе.

Номера доступа с телефонным подключением, созданные в Lync Server 2010, но перемещенные на Lync Server 2013 или ранее созданные в Lync Server 2013, до, во время или после миграции, имеют следующие характеристики:

  - не отображаются в приглашениях на собрание Office Communications Server 2007 R2  и на странице номеров телефонного подключения;

  - отображаются в приглашениях на собрание Lync Server 2010 и на странице номеров телефонного подключения;

  - отображаются в приглашениях на собрание Lync Server 2013 и на странице номеров телефонного подключения;

  - их нельзя просматривать или изменять в средстве администрирования Office Communications Server 2007 R2;

  - их можно просматривать и изменять в панели управления Lync Server 2010 и консоли управления Lync Server 2010;

  - их можно просматривать и изменять в панели управления Lync Server 2013 и консоли управления Lync Server 2013;

  - их можно повторно упорядочивать внутри региона с помощью командлета Set-CsDialinConferencingAccessNumber с параметром Priority.

Необходимо завершить миграцию телефонных номеров доступа, указывающих на пул Lync Server 2010 перед ликвидацией пула Lync Server 2010. Если вы не завершили миграцию телефонных номеров доступа, как описано в следующей процедуре, входящие вызовы на эти номера не будут работать.

<div>


> [!IMPORTANT]  
> Эту процедуру необходимо выполнить перед списанием пула Lync Server 2010.



</div>

<div>


> [!NOTE]  
> Рекомендуется переместить телефонные номера доступа при незначительном использовании сети на случай короткого периода недоступности службы.



</div>

**Определение и перемещение телефонных номеров доступа**

1.  Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.

2.  Для перемещения каждого номера доступа с телефонным подключением в пул, размещенный на Lync Server 2013, в командной строке выполните следующую команду:
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  Откройте Панель управления Lync Server.

4.  В левой области навигации щелкните элемент **Конференция**.

5.  Перейдите на вкладку **Телефонный номер доступа**.

6.  Убедитесь, что номера доступа для телефонного подключения не сохраняются для пула Lync Server 2010, из которого выполняется миграция.
    
    <div>
    

    > [!NOTE]  
    > Если номера доступа для телефонного подключения почтовые точки в пуле Lync Server 2013, можно списать пул Lync Server 2010.

    
    </div>

**Проверка миграции телефонных номеров доступа с помощью панели управления Lync Server**

1.  В учетной записи пользователя, назначенной роли  **CsUserAdministrator** или **CsAdministrator**, выполните вход на любой компьютер во внутреннем развертывании.

2.  Откройте Панель управления Lync Server.

3.  В левой области навигации щелкните элемент **Конференция**.

4.  Перейдите на вкладку **Телефонный номер доступа**.

5.  Убедитесь, что все номера доступа для телефонного подключения перенесены в пул, размещенный на Lync Server 2013.

**Проверка миграции телефонных номеров доступа с помощью консоли управления Lync Server**

1.  Откройте консоль управления Lync Server.

2.  Чтобы вернуть все перемещенные телефонные номера доступа к конференции в командной строке выполните следующую команду:
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  Убедитесь, что все номера доступа для телефонного подключения перенесены в пул, размещенный на Lync Server 2013.

</div>

<span> </span>

</div>

</div>

</div>

