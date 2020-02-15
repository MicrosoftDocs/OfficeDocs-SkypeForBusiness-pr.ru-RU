---
title: 'Lync Server 2013: тестирование сервера Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test the Standard Edition server
ms:assetid: b6ef67bb-9665-43e4-b8b3-eac8898eebf6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412890(v=OCS.15)
ms:contentKeyID: 48185220
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4145740f09557c8f39830dce689fa122456a28f8
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42018980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>Тестирование сервера Standard Edition в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

В следующей процедуре описывается тестирование развертывания сервера Standard Edition.

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>Проверка развертывания сервера выпуска Standard Edition

1.  Используйте "пользователи и компьютеры Active Directory", чтобы добавить объект пользователя Active Directory роли администратора для развертывания Lync Server 2013 (на котором установлена панель управления Lync Server) в группу **CSAdministrator** .

2.  Если объект-пользователь уже выполнил вход в систему, выйдите из системы, а затем повторите вход, чтобы зарегистрировать назначение новой группы.
    
    <div>
    

    > [!NOTE]  
    > Учетная запись пользователя не может быть локальным администратором сервера Lync Server 2013, Standard Edition. Если вы не добавите соответствующих пользователей и группы в группу Ксадминисторс, вы получите сообщение об ошибке при открытии панели управления Lync Server 2013, в котором указано, что "несанкционированный доступ запрещен" из-за сбоя авторизации управления доступом на основе ролей (RBAC). "

    
    </div>

3.  Используйте учетную запись администратора, чтобы войти на компьютер, на котором установлена панель управления Lync Server.

4.  Запустите Панель управления Lync Server и при необходимости укажите учетные данные. В панели управления Lync Server 2013 отображаются сведения о развертывании.

5.  В левой панели навигации щелкните Topology ( **топология**) и убедитесь, что состояние службы — значок компьютера с зеленой стрелкой, а рядом с каждой ролью сервера Lync Server, которая была развернута и переведена в оперативный режим, отображается зеленая галочка.

6.  В левой панели навигации щелкните **Пользователи**, а затем включите два пользователя для Lync Server 2013.

7.  Выполните вход с учетной записью одного пользователя на компьютер, присоединенный к домену, а с учетной записью другого пользователя — на другой компьютер домена.

8.  Установите Lync Server 2013 на каждом из двух клиентских компьютеров, а затем убедитесь, что оба пользователя могут войти в Lync Server 2013 и обмениваться мгновенными сообщениями друг с другом.

</div>

<div>

## <a name="see-also"></a>См. также


[Развертывание клиентов и устройств в Lync Server 2013](lync-server-2013-deploying-clients-and-devices.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

