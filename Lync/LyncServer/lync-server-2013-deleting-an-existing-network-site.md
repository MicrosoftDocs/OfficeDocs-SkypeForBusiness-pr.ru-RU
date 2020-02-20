---
title: 'Lync Server 2013: удаление существующего сетевого сайта'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bf46820309937cb6c5b45ef7e25341335e833e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151379"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a>Удаление существующего сетевого сайта в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-11-01_

Сетевые узлы — это офисы или места, настроенные в каждой области развертывания контроля допуска звонков (CAC) или Enhanced 9-1-1. С помощью панели управления Lync Server 2013 можно настраивать сайты и связывать их с областями. Например, сетевую область для Северной Америки можно связать с такими сетевыми узлами, как Чикаго, Редмонд и Ванкувер. Сетевой узел CAC необходимо создать для каждого узла в организации, даже если у этого узла нет ограничений по пропускной способности. С помощью панели управления Lync Server вы можете создавать, изменять и удалять сетевые сайты. Используйте следующую процедуру для удаления существующего сетевого сайта. Дополнительные сведения о создании или изменении сетевых сайтов можно найти [в статье Создание или изменение сетевых сайтов в Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)

<div>

## <a name="to-delete-a-network-site"></a>Удаление сетевого узла

1.  Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.

2.  Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server. Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).

3.  В левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Узел**.

4.  На странице **Узел** щелкните узел, который требуется удалить.
    
    <div>
    

    > [!NOTE]  
    > Вы можете удалить несколько узлов за раз. Для этого нажмите клавишу CTRL и выберите несколько узлов, удерживая клавишу CTRL нажатой. Или, чтобы выбрать все узлы, щелкните <STRONG>Выбрать все</STRONG> в меню <STRONG>Правка</STRONG>.

    
    </div>

5.  В меню **Правка** выберите команду **Удалить**.

6.  Нажмите кнопку **ОК**.
    
    <div>
    

    > [!WARNING]  
    > Сетевой сайт нельзя удалить, если он связан с подсетью. При попытке удаления сайта, связанного с подсетью, появится сообщение об ошибке. Чтобы проверить, связан ли сайт с подсетями, щелкните сайт и выберите <STRONG>Подробнее</STRONG> в меню <STRONG>Изменить</STRONG>.

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

