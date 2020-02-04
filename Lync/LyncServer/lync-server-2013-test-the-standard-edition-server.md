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
ms.openlocfilehash: 00918643fcc59efc33d12dc3f8f77c7d3ac69815
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746059"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-the-standard-edition-server-in-lync-server-2013"></a>Тестирование сервера Standard Edition в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

Ниже описана процедура проверки развертывания сервера Standard Edition.

<div>

## <a name="to-test-the-deployment-of-a-standard-edition-server"></a>Тестирование развертывания стандартного сервера выпуска

1.  С помощью оснасток "пользователи и компьютеры Active Directory" можно добавить объект "пользователи Active Directory" роли "Администратор" для развертывания Lync Server 2013 (на котором установлена панель управления Lync Server) в группу **ксадминистратор** .

2.  Если объект-пользователь уже выполнил вход в систему, выйдите из системы, а затем повторите вход, чтобы зарегистрировать назначение новой группы.
    
    <div>
    

    > [!NOTE]  
    > Учетная запись пользователя не может быть локальным администратором сервера, на котором установлен Lync Server 2013, Standard Edition. Если вы не добавите соответствующих пользователей и группы в группу Ксадминисторс, то при открытии панели управления Lync Server 2013 появляется сообщение об ошибке, в котором говорится о том, что отказано в доступе из-за сбоя авторизации управления доступом на основе ролей (RBAC).

    
    </div>

3.  Войдите в систему с помощью учетной записи администратора на компьютере, на котором установлена панель управления Lync Server.

4.  Откройте панель управления Lync Server и укажите учетные данные при появлении соответствующего запроса. На панели управления Lync Server 2013 отображаются сведения о развертывании.

5.  На левой панели навигации щелкните **топология**, а затем убедитесь, что состояние службы — значок компьютера с зеленой стрелкой, и рядом с каждой ролью сервера Lync Server, которая была развернута и переведена в сеть, есть зеленая галочка.

6.  На панели навигации слева выберите пункт **Пользователи**, а затем включите два пользователя для Lync Server 2013.

7.  Зарегистрируйте одного пользователя на компьютере, подключенном к домену, и на другой пользователь в домене.

8.  Установите Lync Server 2013 на каждом из двух клиентских компьютеров, а затем убедитесь, что оба пользователя могут входить в Lync Server 2013 и обмениваться мгновенными сообщениями друг с другом.

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

