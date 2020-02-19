---
title: 'Lync Server 2013: изменение или Настройка простых URL-адресов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edit or configure simple URLs
ms:assetid: 0008aeea-4ae9-4e36-83cd-ef7ff7b6e128
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398063(v=OCS.15)
ms:contentKeyID: 48183216
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1618ca331b66612051b2a824aa5ebd2adfac043a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edit-or-configure-simple-urls-in-lync-server-2013"></a>Изменение или Настройка простых URL-адресов в Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2014-02-04_

Для этой процедуры не требуется членство в локальной группе администраторов или группе привилегированного домена. Вы должны войти на компьютер в качестве обычного пользователя.

Lync Server 2013 использует простые URL-адреса для направления внутренних и внешних вызовов служб на сервере переднего плана или в директоре, если она была развернута. Более подробную информацию об простых URL-адресах можно узнать [в статье Планирование простых URL-адресов в Lync Server 2013](lync-server-2013-planning-for-simple-urls.md) в документации по планированию. Можно выбрать формат для простых URL-адресов из нескольких вариантов. Подробнее об этих параметрах можно узнать в статье [требования к DNS для простых URL-адресов в Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md) в документации по планированию.

По умолчанию простые URL-адреса будут настроены в форме (например, простой URL-адрес для телефонного подключения) https://dialin.\<SIP : domain\>

<div>

## <a name="to-configure-simple-urls"></a>Настройка простых URL-адресов

1.  В построителе топологий щелкните узел **Lync Server** правой кнопкой мыши и выберите команду **изменить свойства**.

2.  В области **простые URL-адреса** выберите **URL-адреса для доступа к телефонной линии:** (с телефонным подключением) или **URL-адреса собраний:** (соответствие), а затем щелкните **изменить URL-адрес**.

3.  Задайте для URL-адреса требуемое значение и нажмите кнопку **ОК**, чтобы сохранить изменения. В приведенном здесь примере изменился URL-адрес для телефонного подключения на https://pool01.contoso.net/dialin.

4.  При необходимости тем же способом измените URL-адрес Meet.

</div>

<div>

## <a name="to-define-the-optional-admin-simple-url"></a>Определение дополнительного URL-адреса Admin

1.  В построителе топологий щелкните узел **Lync Server** правой кнопкой мыши и выберите команду **изменить свойства**.

2.  В поле **URL-адрес административного доступа** введите простой URL-адрес, который требуется использовать для административного доступа к панели управления Lync Server 2013, а затем нажмите кнопку **ОК**.
    
    <div>
    

    > [!TIP]  
    > Рекомендуется использовать самый простой URL-адрес для административного доступа. Самый простой вариант — <STRONG> https://admin.</STRONG> &lt;Domain&gt;(домен).

    
    </div>
    
    <div>
    

    > [!IMPORTANT]  
    > Если простые URL-адреса меняются после развертывания, то необходимо подумать о том, какие изменения простых URL-адресов повлияют на записи DNS и сертификаты. Если изменение касается базового простого URL-адреса, то придется также изменить записи DNS и сертификаты. Например, изменение с https://lync.contoso.com/Meet для https://meet.contoso.com изменения базового URL-адреса с Lync.contoso.com на Meet.contoso.com, поэтому необходимо изменить записи DNS и сертификаты, чтобы они ссылались на Meet.contoso.com. Если вы изменили простой URL- https://lync.contoso.com/Meet адрес https://lync.contoso.com/Meetingsс на, то базовый URL-адрес Lync.contoso.com остается прежним, поэтому не требуются изменения DNS или сертификата. Однако при изменении простого URL-адреса необходимо выполнить командлет <STRONG>Enable-CsComputer</STRONG> на каждом директоре и сервере переднего плана, чтобы зарегистрировать изменение.

    
    </div>

</div>

<div>

## <a name="see-also"></a>См. также


[Планирование простых URL-адресов в Lync Server 2013](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

