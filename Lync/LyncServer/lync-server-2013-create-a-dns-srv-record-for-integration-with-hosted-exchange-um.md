---
title: Создание записи DNS SRV для интеграции с размещенной единой системой обмена сообщениями Exchange
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a DNS SRV record for integration with hosted Exchange UM
ms:assetid: 8ea590ae-58ea-4ca5-9853-e0708b3ea760
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh500728(v=OCS.15)
ms:contentKeyID: 48184770
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c30164813619a271f2321db3ff3e8019067193c0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42198962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>Создание записи DNS SRV для интеграции с размещенной единой системой обмена сообщениями Exchange

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-20_

В этом разделе описывается настройка записи SRV службы доменных имен (DNS), которая требуется для маршрутизации сервера Lync Server 2013, для маршрутизации в размещенную службу Exchange, например Microsoft Exchange Online.

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>Создание внешней записи SRV DNS для размещенной службы Exchange

1.  Войдите на внешний сервер DNS как член группы DnsAdmins.

2.  Нажмите кнопку **Пуск**, а затем последовательно выберите пункты **Администрирование** и **DNS**.

3.  В дереве консоли для вашего домена SIP разверните узел **зоны прямого просмотра**и выберите домен SIP, в котором будет установлен Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]
    > Необходимо создать запись SRV DNS в том домене SIP, в котором установлен или будет установлен Lync Server. При создании записи SRV полное доменное имя, которое указывается в поле узла этой службы, должно быть внешним полным доменным именем пограничного пула. Например, если внешнее полное доменное имя пограничного пула edge01.contoso.net, то введите это значение. Кроме того, это должен быть тот же домен, который указан в записи узлов DNS (A).

    
    </div>

4.  Щелкните правой кнопкой мыши выбранный домен, а затем выберите пункт **Другие новые записи**.

5.  В разделе **Тип записи ресурса** выберите **Расположение службы (запись SRV)**, а затем нажмите **Создать запись**.

6.  В **новой записи ресурса**щелкните **Служба**и введите ** \_сипфедератионтлс**.

7.  Щелкните **протокол**, а затем введите ** \_TCP**.

8.  Нажмите **Номер порта** и введите **5061**.

9.  Щелкните **узел, предоставляющий эту службу**, а затем введите полное доменное имя (FQDN) пограничного пула lync Server 2013, который предоставляет доступ к системе lync Server 2013 для доверенных внешних клиентов.
    
    <div>
    

    > [!NOTE]
    > Этот домен также должен быть настроен в параметрах Exchange Online как заслуживающий доверия обслуживающий домен. Для получения дополнительных сведений обратитесь к разделу <A href="https://go.microsoft.com/fwlink/p/?linkid=229762">https://go.microsoft.com/fwlink/p/?linkId=229762</A>Создание обслуживаемых доменов на сайте.

    
    </div>

10. Нажмите кнопку **ОК**, а затем нажмите кнопку **Готово**.

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>Проверка успешности создания записи SRV DNS

1.  Войдите на клиентский компьютер в домене.

2.  Нажмите кнопку **Пуск** и выберите команду **Выполнить**.

3.  В командной строке введите следующую команду:
    
        nslookup <FQDN Lync Edge Pool>

4.  Убедитесь, что вы получили ответ, который сводится к соответствующему IP-адресу для указанного полного доменного имени.

</div>

<div>

## <a name="see-also"></a>См. также


[Создание записей DNS для обратных прокси-серверов в Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

