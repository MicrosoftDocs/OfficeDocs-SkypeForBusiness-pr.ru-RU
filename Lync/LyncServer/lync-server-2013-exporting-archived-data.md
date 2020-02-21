---
title: 'Lync Server 2013: экспорт архивных данных'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Exporting archived data
ms:assetid: 09450d54-769b-4741-924b-e390664d506f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204657(v=OCS.15)
ms:contentKeyID: 48183347
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cc93d529c5f93ad020634d631c94c09e0a94df1a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202325"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a>Экспорт архивных данных из Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Последнее изменение темы:** 2013-02-23_

Данные, архивные в базах данных архивации, не могут быть доступны для поиска или в удобочитаемом формате, но вы можете использовать командлет Export-CsArchivingData для извлечения записей из базы данных и сохранения их в виде файла электронной почты Outlook (EML). Подробные сведения об экспорте архивных данных можно найти в статье [Export – CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) в документации по операциям.

Если вы включаете интеграцию Microsoft Exchange, данные архивируются в хранилищах Exchange 2013. Данные, архивные в Exchange 2013, являются доступными для поиска и обнаружения. Для получения дополнительных сведений о поддержке интегрированных коммуникаций для Exchange 2013 и Lync Server 2013, ознакомьтесь со статьей [Поддержка интеграции Exchange Server и SharePoint в Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) в документации по поддержке. Сведения о доступе к данным, архивированным в Exchange, можно найти в документации по Exchange 2013.

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a>Экспорт данных архивации с помощью командлетов Windows PowerShell

Архивированные данные можно экспортировать с помощью командлета Export-CSArchivingData. Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell. Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.

**Экспорт данных архивации**

  - Эта команда экспортирует все данные atl-sql-001.litwareinc.com, архивированные с 1 июня 2012 г. Полученный выходной файл будет храниться в папке C:\\арчивинжекспортс.
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

**Экспорт данных архивации для одного пользователя**

  - Следующая команда экспортирует архивированные данные для одного пользователя: kenmyer@litwareinc.com. Для этого задается параметр UserUri, за которым указывается SIP-адрес пользователя. Пример:
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Export – CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .

</div>

<div>

## <a name="see-also"></a>См. также


[Поддержка интеграции Exchange Server и SharePoint в Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[Export — CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[Управление архивированием Lync Server 2013](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

