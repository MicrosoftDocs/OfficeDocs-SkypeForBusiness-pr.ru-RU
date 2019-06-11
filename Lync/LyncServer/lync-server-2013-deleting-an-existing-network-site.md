---
title: 'Lync Server 2013: удаление существующего сетевого сайта'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting an existing network site
ms:assetid: 2762149b-3572-4513-b838-beda7fa9e81e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688001(v=OCS.15)
ms:contentKeyID: 49733589
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 772d653e0bde803f47a5742a4f3824bdef01c3f1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-an-existing-network-site-in-lync-server-2013"></a>Удаление существующего сетевого сайта в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-11-01_

Сетевые сайты — это офисы или места, настроенные в каждом регионе управления допуском звонков (CAC) или Улучшенное развертывание 9-1-1. Вы можете настроить сайты и связать их с областями с помощью панели управления Lync Server 2013. Например, сетевой регион для Северной Америки может быть связан с сайтами сети, например в Чикаго, Redmond и Vancouver. Сайт сети CAC должен создаваться для каждого сайта в Организации, даже если на нем нет ограничений по пропускной способности. На панели управления Lync Server вы можете создавать, изменять и удалять сетевые сайты. Чтобы удалить существующий сайт сети, выполните указанные ниже действия. Сведения о создании и изменении сайтов сети можно найти [в разделе Создание или изменение сетевых сайтов в Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)

<div>

## <a name="to-delete-a-network-site"></a>Удаление сайта сети

1.  Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.

2.  Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server. Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  На панели навигации слева выберите пункт **Настройка сети** , а затем — **сайт**.

4.  На странице **сайта** выберите сайт, который вы хотите удалить.
    
    <div>
    

    > [!NOTE]  
    > За один раз можно удалить сразу несколько сайтов. Для этого нажмите клавишу CTRL и, удерживая нажатой клавишу CTRL, щелкните несколько сайтов. Кроме того, чтобы выбрать все сайты, в меню <STRONG>Правка</STRONG> выберите команду <STRONG>выделить все</STRONG> .

    
    </div>

5.  В меню **Правка** выберите команду **Удалить**.

6.  Нажмите кнопку **ОК**.
    
    <div>
    

    > [!WARNING]  
    > Вы не можете удалить сайт сети, если он связан с сетевой подсетью. При попытке удалить сайт, связанный с подсетью, появится сообщение об ошибке. Чтобы проверить, связан ли сайт с подсетями, щелкните его, а затем в меню <STRONG>Правка</STRONG> выберите команду <STRONG>Показать подробности</STRONG> .

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

