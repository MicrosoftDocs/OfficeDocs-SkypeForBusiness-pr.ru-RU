---
title: 'Lync Server 2013: экспорт архивных данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4974971912b0b64652aa939368f0a86e2e2484a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a>Экспорт архивных данных из Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Тема последнего изменения:** 2013-02-23_

Данные, заархивированные в архивных базах данных, не доступны для поиска или чтения, но можно использовать командлет Export-CsArchivingData для извлечения записей из базы данных и их сохранения в виде файла EML (Outlook Electronic Mail). Подробнее об экспорте архивных данных можно найти в разделе [Export-ксарчивингдата](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) в документации по эксплуатации.

При включении интеграции с Microsoft Exchange данные архивируются в хранилищах Exchange 2013. Данные, сохраненные в Exchange 2013, можно найти и обнаруживаемые. Дополнительные сведения о поддержке интегрированной связи для Exchange 2013 и Lync Server 2013 можно найти в разделе Документация по поддержке [Exchange Server и интеграции с SharePoint в Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) . Подробные сведения о доступе к данным, архивированным в Exchange, можно найти в документации по Exchange 2013.

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Экспорт данных архивации с помощью командлетов Windows PowerShell

Данные для архивации можно экспортировать с помощью командлета Export-Ксарчивингдата. Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.

**Экспорт данных архивации**

  - Эта команда экспортирует все данные архивации, внесенные в базу данных архивации atl-sql-001.litwareinc.com с 1 июня 2012 г. Получившийся выходной файл будет храниться в папке C:\\арчивинжекспортс.
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**Экспорт данных архивации для одного пользователя**

  - Следующая команда экспортирует данные архивации для одного пользователя: kenmyer@litwareinc.com. Для этого задается параметр UserUri, после которого указывается SIP-адрес пользователя. Пример:
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

Дополнительные сведения можно найти в разделе справки по командлету [Export-ксарчивингдата](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .

</div>

<div>

## <a name="see-also"></a>См. также


[Поддержка интеграции Exchange Server и SharePoint в Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[Управление архивированием Lync Server 2013](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

