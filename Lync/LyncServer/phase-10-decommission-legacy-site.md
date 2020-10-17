---
title: 'Этап 10: списание устаревшего сайта'
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a8a2871659747b68e7a0dec6a945c6f987219a8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48533766"
---
# <a name="phase-10-decommission-legacy-site"></a>Этап 10: списание устаревшего сайта

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2012-10-16_

В следующих разделах представлены рекомендации по списанию пулов, а также отключению и удалению серверов и пулов из устаревшего развертывания Office Communications Server 2007 R2. Не требуется выполнять все процедуры, представленные в этом разделе. Изучите информацию, представленную в каждом из разделов, чтобы определить, какие процедуры вывода из эксплуатации следует использовать.

<div>


> [!WARNING]  
> Если вы импортировали каталоги конференций для конференц-связи с телефонным подключением в Lync Server 2013, перед началом списания пулов важно перевести его в Lync Server 2013. Если вы выводите пул из эксплуатации без предварительного переноса права владения, функция телефонного подключения для всех перенесенных собраний больше не будет работать. Необходимо выполнять процедуру переноса прав владения однократно для каждого каталога конференц-связи в устаревшем пуле.



</div>

<div>


> [!IMPORTANT]  
> Сведения о переносе и обновлении приложений Microsoft Unified Communications Managed API (UCMA), предшествующих списанию устаревшей среды, приведены в разделе <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A>



</div>

<div>

## <a name="in-this-section"></a>Содержание

  - [Перемещение каталогов конференций](move-conference-directories.md)

  - [Обновление записей DNS SRV](update-dns-srv-records_1.md)

  - [Списание серверов и пулов](decommissioning-servers-and-pools.md)

  - [Удаление BackCompatSite](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

