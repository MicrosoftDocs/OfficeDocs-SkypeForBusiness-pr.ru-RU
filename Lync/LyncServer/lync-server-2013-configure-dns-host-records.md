---
title: 'Lync Server 2013: Настройка записей узла DNS'
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
ms.openlocfilehash: 54ae1e2502ec1618f007ba76255ae6d01ebb66f5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42028590"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a>Настройка записей узла DNS для Lync Server 2013

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

