---
title: Создание записи DNS SRV для интеграции с размещенной единой системой обмена сообщениями
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
ms.openlocfilehash: c8cc5072e122d553007a2b4e095c58988aca390d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740459"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-dns-srv-record-for-integration-with-hosted-exchange-um"></a>Создание записи DNS SRV для интеграции с размещенной единой системой обмена сообщениями

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-20_

В этой статье описано, как настроить запись SRV службы доменных имен (DNS), необходимую для того, чтобы сервер Lync Server 2013 Edge направлялся на размещенную службу Exchange, например Microsoft Exchange Online.

<div>

## <a name="to-create-an-external-dns-srv-record-for-the-hosted-exchange-service"></a>Создание внешней записи SRV DNS для размещенной службы Exchange

1.  Войдите на внешний DNS-сервер в качестве участника группы Днсадминс.

2.  Нажмите кнопку **Пуск**, выберите пункт **Администрирование**, а затем — **DNS**.

3.  В дереве консоли для вашего домена SIP разверните раздел **зоны прямого просмотра**и выберите домен SIP, в который будет установлен Lync Server 2013.
    
    <div>
    

    > [!IMPORTANT]
    > Вы должны создать SRV-запись DNS в домене SIP, в котором установлен или будет устанавливаться сервер Lync Server. Когда вы создаете SRV-запись, полное доменное имя, используемое узлом для этого поля службы, должно быть внешним доменным именем пограничного пула. Например, если внешнее полное доменное имя пограничного пула — edge01.contoso.net, введите это значение. Этот элемент также должен находиться в том же домене, что и DNS-записи HOSTS (A).

    
    </div>

4.  Щелкните выбранный домен правой кнопкой мыши и выберите пункт **другие новые записи**.

5.  В списке **тип записи ресурсов**выберите пункт **расположение службы (SRV)** и нажмите кнопку **создать запись**.

6.  В **новой записи ресурса**выберите пункт **Служба**, а затем введите ** \_сипфедератионтлс**.

7.  Выберите **протокол**и введите ** \_TCP**.

8.  Нажмите **Номер порта** и введите значение **5061**.

9.  Щелкните **узел, предлагающий эту службу**, и введите полное доменное имя (FQDN) пула lync Server 2013 EDGE, который предоставляет доступ к системе lync Server 2013 для доверенных внешних клиентов.
    
    <div>
    

    > [!NOTE]
    > Кроме того, домен необходимо настроить в качестве полномочного, обслуживаемого домена в параметрах Exchange Online. Дополнительные сведения можно найти в разделе Создание обслуживаемых доменов по адресу <A href="http://go.microsoft.com/fwlink/p/?linkid=229762">http://go.microsoft.com/fwlink/p/?linkId=229762</A>.

    
    </div>

10. Нажмите кнопку **ОК**, а затем нажмите кнопку **Готово**.

</div>

<div>

## <a name="to-verify-that-the-dns-srv-record-was-created-successfully"></a>Проверка успешности создания DNS SRV-записи

1.  Войдите в домен на клиентском компьютере.

2.  В меню **Пуск** выберите пункт **Выполнить**.

3.  В командной строке выполните следующую команду:
    
        nslookup <FQDN Lync Edge Pool>

4.  Убедитесь в том, что вы получили ответ на соответствующий IP-адрес для полного доменного имени.

</div>

<div>

## <a name="see-also"></a>См. также


[Создание DNS-записей для обратных прокси-серверов в Lync Server 2013](lync-server-2013-create-dns-records-for-reverse-proxy-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

