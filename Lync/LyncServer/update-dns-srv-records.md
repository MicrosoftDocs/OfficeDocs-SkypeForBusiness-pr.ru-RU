---
title: Обновление записей DNS SRV
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: 9542b91a-108c-4980-89ec-634905cbbf26
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688139(v=OCS.15)
ms:contentKeyID: 49733739
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40abfa35892b09b3bdc4824a35f0697142980854
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>Обновление записей DNS SRV

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-09-29_

Для успешного выполнения этой процедуры необходимо войти на сервер или в домен как участник группы администраторов домена или DnsAdmins.

В этом разделе описывается, как обновить записи службы доменных имен (DNS) после перехода на Lync Server 2013. После того как все пользователи будут перемещены в Lync Server 2013, но до того, как старый пул или директор Lync Server 2010 не будут списаны, необходимо обновить записи DNS SRV во внутренней DNS для каждого домена SIP. В этой процедуре подразумевается, что ваша внутренняя DNS имеет зоны для доменов пользователей SIP.

**Настройка DNS-записи SRV**

1.  На DNS-сервере нажмите кнопку **Пуск**, а затем последовательно выберите пункты **Администрирование** и **DNS**.

2.  В дереве консоли для вашего домена SIP разверните узел **зоны прямого просмотра**, разверните домен SIP, в котором установлен Lync Server 2013, и перейдите к параметру ** \_TCP** .

3.  В правой области щелкните ** \_** правой кнопкой мыши сипинтерналтлс и выберите пункт **Свойства**.

4.  В **узле, предоставляющем эту службу**, обновите полное доменное имя узла, указав пул Lync Server 2013.

5.  Нажмите кнопку **ОК**.

**Проверка возможности разрешения полного доменного имени интерфейсного пула или сервера Standard Edition**

1.  Войдите на клиентский компьютер в домене.

2.  Нажмите кнопку **Пуск** и затем выберите команду **Выполнить**.

3.  В поле **Открыть** введите **cmd** и нажмите кнопку **ОК**.

4.  В командной строки введите **nslookup** \<FQDN переднего плана\> или \<полное доменное имя сервера\>Standard Edition, а затем нажмите клавишу ВВОД.

5.  Убедитесь, что вы получили ответ, который сводится к соответствующему IP-адресу для указанного полного доменного имени.

</div>

<span> </span>

</div>

</div>

</div>

