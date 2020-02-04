---
title: 'Lync Server 2013: настройка записей узлов DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b74da23cb0139a982a30207b61032f043f795b76
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>Настройка записей узлов DNS для Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-01_

Для успешного выполнения этой процедуры необходимо войти на сервер или домен, как минимум, с учетной записью члена группы администраторов домена или пользователя, который является членом группы Днсадминс.

<div>

## <a name="to-configure-dns-host-a-records"></a>Настройка записей узла DNS

1.  На сервере доменных имен (DNS) нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.

2.  В дереве консоли для вашего домена разверните раздел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором будет установлен Lync Server 2013.

3.  Выберите команду **создать узел (A или AAAA)**.

4.  Щелкните **Name (имя**), введите имя узла для пула (доменное имя будет указано в той зоне, в которой она определена, и ее не нужно вводить как часть записи A).

5.  Щелкните **IP-адрес**, введите виртуальный IP-протокол для подсистемы балансировки нагрузки для пула переднего плана.
    
    <div>
    

    > [!IMPORTANT]  
    > В развертываниях, использующих пул каталогов, записи узла (A) для простых URL-адресов должны указывать на VIP подсистемы балансировки нагрузки.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Если вы развертываете только один сервер выпуска Enterprise Edition или режиссер, подключенный к топологии без подсистемы балансировки нагрузки, а также при развертывании сервера Standard Edition, введите IP-адрес сервера Enterprise Edition, сервера Standard Edition или Director. Подсистема балансировки нагрузки требуется при развертывании более одного сервера выпуска Enterprise Edition или режиссера в пуле. Подсистема балансировки нагрузки не используется для серверов Standard Edition.

    
    </div>

6.  Нажмите кнопку **Добавить узел**и нажмите кнопку **ОК**.

7.  Чтобы создать дополнительную запись, повторите шаги 4 и 5.

8.  Завершив создание всех необходимых записей, нажмите кнопку **Готово**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

