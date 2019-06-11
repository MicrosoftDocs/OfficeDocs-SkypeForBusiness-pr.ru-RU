---
title: 'Lync Server 2013: редактирование схемы конфигурации сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Editing the network configuration diagram
ms:assetid: 47425ab1-5645-4d6f-b202-64bcce43e3ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558643(v=OCS.15)
ms:contentKeyID: 51541469
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2772cad1d1a16aa0363b1ab50d0bcaadacb91a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834319"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="editing-the-network-configuration-diagram-in-lync-server-2013"></a>Изменение схемы конфигурации сети в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-21_

Большая часть работы, которую делает разработчик в Lync Server 2013, средство планирования состоит из определения записей для IP-адресов и полных доменных имен (FQDN) для записей в сетевом графике. Данные, введенные на этой странице, переносятся в отчеты и другие сведения, содержащиеся в инструменте "планирование".

![Сетевая схема инструмента "Планирование] " (images/Gg558643.eeabee2d-698c-4b79-baa5-caa4cfb7edb3(OCS.15).jpg "Сетевая схема инструмента \"Планирование") "

Средство планирования создает сетевую схему с текстом по умолчанию для IP-адресов и полных доменных имен.

Изменение схемы сети и входных значений:

1.  Выберите раздел сети, работу над которым хотите начать. Например, дважды щелкните текст **access1.contoso.com**. В открывшемся диалоговом окне введите фактическое полное доменное имя сервера access1.contoso.com и фактически IP-адрес, заменив значение 131.107.155.3.

2.  Нажмите кнопку **OK** (ОК), чтобы сохранить записи.

3.  Продолжайте изменять IP-адреса и полные доменные имена, указывая виртуальные IP-адреса для устройств балансировки нагрузки или записи сервера для подсистемы балансировки нагрузки службы доменных имен (DNS) для серверов в пулах.

Удобной особенность средства планирования является то, что оно может поэтапно назначать диапазон IP-адресов и имен узла сервера, не требуя от проектировщика изменения каждого отдельного сервера в пуле. Например:

1.  Дважды щелкните входящие в состав пула серверы переднего плана. После открытия диалогового окна выберите элемент **Do you want to use the IPs and FQDN as starting points for all equivalent servers in this cluster?** (Использовать IP-адреса и полное доменное имя в качестве исходных точек для всех эквивалентных серверов в этом кластере?).

2.  Например, начальное значение для первого сервера: fe0101.contoso.com и IP-адрес 192.168.21.122.

3.  Введите значение **fe0.contoso.com** в поле **Front End Server FQDN** (Полное доменное имя сервера переднего плана), введите значение **192.168.21.131** в поле **Front End Server IP address** (IP-адрес сервера переднего плана), а затем нажмите кнопку **OK** (ОК).

4.  Компонент автоматического приращения обновляет все серверы в пуле с fe01 по fe06 и все IP-адреса с 192.168.21.131 по 136.

После внесения всех правок сохраните топологию, выполнив следующие действия:

Чтобы сохранить структуру средства планирования, нажмите кнопку **файл**, а затем выберите команду **Сохранить топологию** или **Сохранить топологию как**. If a **Save Planning Tool As** dialog box appears, type a name for the file in **File name**, and then click **Save**.

<div>

## <a name="see-also"></a>См. также


[Изменение структуры в Lync Server 2013](lync-server-2013-editing-the-design.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

