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
ms.openlocfilehash: f5758d5e28610906b743888d25197385ef542717
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a><span data-ttu-id="ef439-102">Экспорт архивных данных из Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef439-102">Exporting archived data from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ef439-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="ef439-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="ef439-104">Данные, заархивированные в архивных базах данных, не доступны для поиска или чтения, но можно использовать командлет Export-CsArchivingData для извлечения записей из базы данных и их сохранения в виде файла EML (Outlook Electronic Mail).</span><span class="sxs-lookup"><span data-stu-id="ef439-104">Data archived in Archiving databases is not searchable or in a readable format, but you can use the Export-CsArchivingData cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span> <span data-ttu-id="ef439-105">Подробнее об экспорте архивных данных можно найти в разделе [Export-ксарчивингдата](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) в документации по эксплуатации.</span><span class="sxs-lookup"><span data-stu-id="ef439-105">For details about exporting archived data, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in the Operations documentation.</span></span>

<span data-ttu-id="ef439-106">При включении интеграции с Microsoft Exchange данные архивируются в хранилищах Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ef439-106">If you enable Microsoft Exchange integration, data is archived in Exchange 2013 stores.</span></span> <span data-ttu-id="ef439-107">Данные, сохраненные в Exchange 2013, можно найти и обнаруживаемые.</span><span class="sxs-lookup"><span data-stu-id="ef439-107">Data archived in Exchange 2013 is searchable and discoverable.</span></span> <span data-ttu-id="ef439-108">Дополнительные сведения о поддержке интегрированной связи для Exchange 2013 и Lync Server 2013 можно найти в разделе Документация по поддержке [Exchange Server и интеграции с SharePoint в Lync server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) .</span><span class="sxs-lookup"><span data-stu-id="ef439-108">For details about support for integrated communications for Exchange 2013 and Lync Server 2013, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="ef439-109">Подробные сведения о доступе к данным, архивированным в Exchange, можно найти в документации по Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="ef439-109">For details about accessing data that is archived in Exchange, see the Exchange 2013 documentation.</span></span>

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="ef439-110">Экспорт данных архивации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="ef439-110">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="ef439-111">Данные для архивации можно экспортировать с помощью командлета Export-Ксарчивингдата.</span><span class="sxs-lookup"><span data-stu-id="ef439-111">Archiving data can be exported by using the Export-CSArchivingData cmdlet.</span></span> <span data-ttu-id="ef439-112">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef439-112">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="ef439-113">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ef439-113">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="ef439-114">**Экспорт данных архивации**</span><span class="sxs-lookup"><span data-stu-id="ef439-114">**To export archiving data**</span></span>

  - <span data-ttu-id="ef439-115">Эта команда экспортирует все данные архивации, внесенные в базу данных архивации atl-sql-001.litwareinc.com с 1 июня 2012 г.</span><span class="sxs-lookup"><span data-stu-id="ef439-115">This command exports all the archiving data written to the archiving database atl-sql-001.litwareinc.com since June 1, 2012.</span></span> <span data-ttu-id="ef439-116">Получившийся выходной файл будет храниться в папке C:\\арчивинжекспортс.</span><span class="sxs-lookup"><span data-stu-id="ef439-116">The resulting output file will be stored in the folder C:\\ArchivingExports.</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

<span data-ttu-id="ef439-117">**Экспорт данных архивации для одного пользователя**</span><span class="sxs-lookup"><span data-stu-id="ef439-117">**To export archiving data for a single user**</span></span>

  - <span data-ttu-id="ef439-118">Следующая команда экспортирует данные архивации для одного пользователя: kenmyer@litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="ef439-118">The following command exports archiving data for a single user: kenmyer@litwareinc.com.</span></span> <span data-ttu-id="ef439-119">Для этого задается параметр UserUri, после которого указывается SIP-адрес пользователя.</span><span class="sxs-lookup"><span data-stu-id="ef439-119">This is done by including the UserUri parameter followed by the user’s SIP address.</span></span> <span data-ttu-id="ef439-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="ef439-120">For example:</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="ef439-121">Дополнительные сведения можно найти в разделе справки по командлету [Export-ксарчивингдата](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .</span><span class="sxs-lookup"><span data-stu-id="ef439-121">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ef439-122">См. также</span><span class="sxs-lookup"><span data-stu-id="ef439-122">See Also</span></span>


[<span data-ttu-id="ef439-123">Поддержка интеграции Exchange Server и SharePoint в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef439-123">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[<span data-ttu-id="ef439-124">Export-CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="ef439-124">Export-CsArchivingData</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[<span data-ttu-id="ef439-125">Управление архивированием Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ef439-125">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

