---
title: 'Lync Server 2013: Настройка записей узла DNS'
description: 'Lync Server 2013: Настройка записей узла DNS.'
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
ms.openlocfilehash: 7fd403402d0d2f089d7fc92a62296a56df0cf2e6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553435"
---
# <a name="configure-dns-host-records-for-lync-server-2013"></a>Настройка записей узла DNS для Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-01_

Чтобы успешно выполнить процедуру, необходимо выполнить вход на сервер или в домен по крайней мере с правами члена группы "Администраторы домена" или DnsAdmins.

<div>

## <a name="to-configure-dns-host-a-records"></a>Настройка записей A узла DNS

1.  На сервере DNS в меню **Пуск** выберите пункт **Администрирование** и щелкните **DNS**.

2.  В дереве консоли для своего домена разверните узел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен, в котором будет установлен Lync Server 2013.

3.  Выберите команду **Создать узел (A или AAAA)**.

4.  Щелкните поле **Имя** и введите имя узла пула (имя домена принимается соответствующим зоне, в которой определяется запись, и его не нужно вводить как часть записи A).

5.  Щелкните **IP-адрес**, введите виртуальный IP-адрес подсистемы балансировки нагрузки для пула переднего плана.
    
    <div>
    

    > [!IMPORTANT]  
    > В развертываниях, в которых используется пул Директоров, записи узлов (A) для простых URL-адресов должны указывать на виртуальный IP-адрес балансировщика нагрузки Директоров.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Если вы развертываете только один сервер Enterprise Edition или Директор, который подключен к топологии без балансировщика нагрузки, или если вы развертываете сервер Standard Edition, введите IP-адрес сервера Enterprise Edition, Standard Edition или Директора. Балансировщик нагрузки требуется, если вы развертываете несколько серверов Enterprise Edition или Директоров в пуле. С серверами Standard Edition балансировщики нагрузки не используются.

    
    </div>

6.  Щелкните **Добавить узел**, а затем нажмите кнопку **ОК**.

7.  Чтобы создать еще одну запись A, повторите действия 4 и 5.

8.  Создав все нужные записи A, нажмите кнопку **Готово**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

