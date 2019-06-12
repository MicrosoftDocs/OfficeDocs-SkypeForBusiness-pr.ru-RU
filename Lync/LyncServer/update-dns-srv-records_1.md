---
title: Обновление записей DNS SRV
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97ff3eed81a90960444b260bd0ca5b9c4c67022e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848889"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="update-dns-srv-records"></a>Обновление записей DNS SRV

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-09-29_

Для успешного выполнения этой процедуры необходимо войти на сервер или домен в группу администраторов домена или в группу пользователей Днсадминс.

В этой статье описано, как обновить записи DNS после перехода на Lync Server 2013. После того как все пользователи будут перемещены на Lync Server 2013, но перед удалением устаревшего пула или режиссера Office Communications Server 2007 R2 необходимо обновить записи DNS SRV во внутренней службе DNS для каждого домена SIP. В этой процедуре предполагается, что в вашей внутренней DNS-зоне есть зоны для доменов пользователей SIP.

**Настройка DNS-записи SRV**

1.  На DNS-сервере нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.

2.  В дереве консоли для вашего домена SIP разверните раздел **зоны прямого просмотра**, разверните домен SIP, в котором установлен Lync Server 2013, и перейдите к параметру ** \_TCP** .

3.  В правой области щелкните ** \_** правой кнопкой мыши сипинтерналтлс и выберите пункт **Свойства**.

4.  В **узле, предлагающем эту службу**, обновите полное доменное имя узла, чтобы оно указывало на пул Lync Server 2013.

5.  Нажмите кнопку **ОК**.

**Проверка возможности разрешения полных доменных имен в пуле или сервере Standard Edition**

1.  Войдите в домен на клиентском компьютере.

2.  В меню **Пуск** выберите пункт **Выполнить**.

3.  В поле **Открыть** введите **cmd**и нажмите кнопку **ОК**.

4.  В командной строке введите **nslookup** \<FQDN для пула\> переднего плана или \<полное доменное имя сервера\>Standard Edition, а затем нажмите клавишу ВВОД.

5.  Убедитесь в том, что вы получили ответ на соответствующий IP-адрес для полного доменного имени.

</div>

<span> </span>

</div>

</div>

</div>

