---
title: 'Этап 10: списание устаревшего сайта'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a04054c158f1c97f5090328e1277dcdb63b1d823
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848980"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a>Этап 10: списание устаревшего сайта

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2012-10-16_

В следующих разделах приведены рекомендации по удалению пулов и отключению серверов и пулов из устаревшего развертывания Office Communications Server 2007 R2. Не все процедуры, перечисленные в этом разделе, являются обязательными. Ознакомьтесь со сведениями в каждом из этих разделов, чтобы определить, какую процедуру списания следует использовать.

<div>


> [!WARNING]  
> Если вы импортировали каталоги конференций для конференц-связи с телефонным подключением на Lync Server 2013, важно перейти в каталог конференции на Lync Server 2013, прежде чем приступить к списанию пулов. Если вы списать пул без предварительного перехода в каталог конференц-связи, функция телефонного подключения для всех перенесенных собраний перестанет работать. Вы должны выполнить шаг для смены владельца для каждой из каталогов конференции в пуле старого.



</div>

<div>


> [!IMPORTANT]  
> Сведения о переносе и обновлении приложений для управляемых API Microsoft Unified Communications (УКМА) перед списанием устаревшей среды можно найти в разделе<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A>



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Перемещение каталогов конференций](move-conference-directories.md)

  - [Обновление записей DNS SRV](update-dns-srv-records_1.md)

  - [Списание серверов и групп](decommissioning-servers-and-pools.md)

  - [Удалить Бакккомпатсите](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

