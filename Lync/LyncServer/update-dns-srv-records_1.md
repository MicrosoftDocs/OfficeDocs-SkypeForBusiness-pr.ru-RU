---
title: Обновление записей DNS SRV
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Update DNS SRV records
ms:assetid: a29149aa-30cc-4a59-af98-fb95c2385cce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688161(v=OCS.15)
ms:contentKeyID: 49733765
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9bb3c5a3f74d3a85fbc5742514a92015df08d5c9
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755663"
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

В этом разделе описывается, как обновить записи службы доменных имен (DNS) после перехода на Lync Server 2013. После того как все пользователи будут перемещены в Lync Server 2013, но до ликвидации устаревшего пула или директора Office Communications Server 2007 R2 необходимо обновить записи DNS SRV во внутренней DNS для каждого домена SIP. В этой процедуре подразумевается, что ваша внутренняя DNS имеет зоны для доменов пользователей SIP.

**Настройка DNS-записи SRV**

1.  На DNS-сервере нажмите кнопку **Пуск**, а затем последовательно выберите пункты **Администрирование** и **DNS**.

2.  В дереве консоли для вашего домена SIP разверните узел **зоны прямого просмотра**, РАЗВЕРНИТЕ домен SIP, в котором установлен Lync Server 2013, и перейдите к параметру ** \_ TCP** .

3.  В правой области щелкните правой кнопкой мыши ** \_ сипинтерналтлс** и выберите пункт **Свойства**.

4.  В **узле, предоставляющем эту службу**, обновите полное доменное имя узла, указав пул Lync Server 2013.

5.  Нажмите кнопку **ОК**.

**Проверка возможности разрешения полного доменного имени интерфейсного пула или сервера Standard Edition**

1.  Войдите на клиентский компьютер в домене.

2.  Нажмите кнопку **Пуск** и затем выберите команду **Выполнить**.

3.  В поле **Открыть** введите **cmd** и нажмите кнопку **ОК**.

4.  В командной строки введите **nslookup** \<FQDN of the Front End pool\> или и нажмите \<FQDN of the Standard Edition server\> клавишу ВВОД.

5.  Убедитесь, что вы получили ответ, который сводится к соответствующему IP-адресу для указанного полного доменного имени.

</div>

<span> </span>

</div>

</div>

</div>

