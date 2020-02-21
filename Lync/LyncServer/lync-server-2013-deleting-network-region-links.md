---
title: 'Lync Server 2013: удаление связей между сетевыми областями'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network region links
ms:assetid: 839273cd-d23f-4b38-84e6-d2dc972f49cd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688114(v=OCS.15)
ms:contentKeyID: 49733712
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a19835235921c10c0b3fe2be7d9c269a36dff7b6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179686"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-network-region-links-in-lync-server-2013"></a>Удаление связей между областями сети в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Вы можете настроить канал между двумя областями сети как часть контроля допуска звонков (CAC). Регионы в сети связываются с помощью физического подключения глобальной сети. Вы можете удалить существующую ссылку между двумя областями сети с помощью панели управления Lync Server. Дополнительные сведения о создании или изменении связи между областями сети см [в разделе Настройка связей между областями сети в Lync Server 2013](lync-server-2013-configuring-network-region-links.md)

<div>

## <a name="to-delete-a-network-region-link"></a>Удаление канала области сети

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Связь между областями**.

4.  На странице **Канал области** щелкните канал области, который нужно удалить.
    
    <div>
    

    > [!NOTE]  
    > За один раз вы можете удалить несколько каналов. Для этого нажмите клавишу CTRL и, удерживая ее, выберите несколько каналов. Чтобы выбрать все каналы, щелкните пункт <STRONG>Выбрать все</STRONG> в меню <STRONG>Правка</STRONG>.

    
    </div>

5.  В меню **Правка** щелкните пункт **Удалить**.

6.  Нажмите кнопку **ОК**.

</div>

<div>

## <a name="see-also"></a>См. также


[Настройка связей между областями сети в Lync Server 2013](lync-server-2013-configuring-network-region-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

