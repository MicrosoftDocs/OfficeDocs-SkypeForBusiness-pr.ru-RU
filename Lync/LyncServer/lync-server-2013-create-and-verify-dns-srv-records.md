---
title: 'Lync Server 2013: создание и проверка записей DNS SRV'
description: 'Lync Server 2013: создание и проверка записей DNS SRV.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create and verify DNS SRV records
ms:assetid: 86888c7e-1401-458f-9a7b-08ac726deeec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398680(v=OCS.15)
ms:contentKeyID: 48184714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a71c876d0b26b9305feed7146fa6321a3983588d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562385"
---
# <a name="create-and-verify-dns-srv-records-in-lync-server-2013"></a>Создание и проверка записей DNS SRV в Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-21_

Чтобы успешно выполнить данную процедуру, вы должны войти на сервер или в домен хотя бы в качестве члена группы администраторов домена или группы DnsAdmins.

В этом разделе описывается, как настроить записи службы доменных имен (DNS), необходимые для создания в среде Lync Server 2013, и те, которые необходимы для автоматического входа клиента. При создании пула переднего плана программа установки создает объекты и параметры Active Directory для пула, включая полное доменное имя пула. Аналогичные объекты и параметры создаются для сервера Standard Edition. Чтобы клиенты могли подключаться к пулу или серверу Standard Edition, необходимо зарегистрировать полное доменное имя пула или сервера Standard Edition в DNS. Вам следует создать DNS-записи SRV во внутренней DNS для каждого домена SIP. В этой процедуре подразумевается, что ваша внутренняя DNS имеет зоны для доменов пользователей SIP.

<div>

## <a name="to-configure-a-dns-srv-record"></a>Настройка DNS-записи SRV

1.  На DNS-сервере нажмите кнопку **Пуск**, а затем последовательно выберите пункты **Администрирование** и **DNS**.

2.  В дереве консоли для вашего домена SIP разверните узел **зоны прямого просмотра**и щелкните правой кнопкой мыши домен SIP, в котором будет установлен сервер Lync Server 2013.

3.  Щелкните элемент **Other New Records** (Другие новые записи).

4.  В разделе **Выбор типа записи ресурса** выберите **Service Location (SRV) (Расположение службы (запись SRV))**, а затем нажмите кнопку **Создать запись**.

5.  Выберите пункт **Служба**и введите ** \_ сипинтерналтлс**.

6.  Щелкните **протокол**, а затем введите ** \_ TCP**.

7.  Нажмите **Номер порта** и введите **5061**.

8.  Щелкните **узел, предоставляющий эту службу**, а затем введите полное доменное имя пула или сервера Standard Edition.

9.  Нажмите кнопку **ОК**, а затем нажмите кнопку **Готово**.

</div>

<div>

## <a name="to-verify-the-creation-of-a-dns-srv-record"></a>Проверка создания DNS-записи SRV

1.  Выполните вход на клиентский компьютер с использованием учетной записи, которая является членом группы прошедших проверку пользователей или имеет эквивалентные разрешения.

2.  Нажмите кнопку **Пуск** и затем выберите команду **Выполнить**.

3.  В поле **Открыть** введите **cmd** и нажмите кнопку **ОК**.

4.  Введите **nslookup** в командной строке, а затем нажмите клавишу ВВОД.

5.  Введите **set type=srv**, а затем нажмите клавишу ВВОД.

6.  Введите ** \_ сипинтерналтлс. \_ tcp.contoso.com**, а затем нажмите клавишу ВВОД. Для записи TLS отображаются следующие выходные данные:
    
    Сервер: \<dns server\> . contoso.com
    
    Address \<IP address of DNS server\>
    
    Неофициальный ответ:
    
    \_сипинтерналтлс. \_ расположение службы tcp.contoso.com SRV:
    
    приоритет = 0
    
    Вес = 0
    
    порт = 5061
    
    SVR hostname = poolname.contoso.com (или запись сервера Standard Edition)
    
    адрес Интернета poolname.contoso.com = \<virtual IP Address of the load balancer\> или \<IP address of a single Enterprise Edition server for pools with only one Enterprise Edition server\>\<IP address of the Standard Edition server\>

7.  По завершении введите **exit** в командной строке и нажмите клавишу ВВОД.

</div>

<div>

## <a name="to-verify-that-the-fqdn-of-the-front-end-pool-or-standard-edition-server-can-be-resolved"></a>Проверка возможности разрешения для полного доменного имени интерфейсного пула или сервера Standard Edition

1.  Войдите на клиентский компьютер в домене.

2.  Нажмите кнопку **Пуск** и затем выберите команду **Выполнить**.

3.  В поле **Открыть** введите **cmd** и нажмите кнопку **ОК**.

4.  В командной строки введите **nslookup** \<FQDN of the Front End pool\> или и нажмите \<FQDN of the Standard Edition server\> клавишу ВВОД.

5.  Убедитесь, что вы получили ответ, который сводится к соответствующему IP-адресу для указанного полного доменного имени.

</div>

</div>

<span> </span>

</div>

</div>

</div>

