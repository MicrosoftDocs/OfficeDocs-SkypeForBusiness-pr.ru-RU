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
ms.openlocfilehash: a91ff8cbd2d6952ba4cfff8a4c5bbeb63475c342
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134595"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="exporting-archived-data-from-lync-server-2013"></a><span data-ttu-id="50525-102">Экспорт архивных данных из Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50525-102">Exporting archived data from Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50525-103">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="50525-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="50525-104">Данные, архивные в базах данных архивации, не могут быть доступны для поиска или в удобочитаемом формате, но вы можете использовать командлет Export-CsArchivingData для извлечения записей из базы данных и сохранения их в виде файла электронной почты Outlook (EML).</span><span class="sxs-lookup"><span data-stu-id="50525-104">Data archived in Archiving databases is not searchable or in a readable format, but you can use the Export-CsArchivingData cmdlet to extract records from the database and save them as an Outlook Electronic Mail (EML) file.</span></span> <span data-ttu-id="50525-105">Подробные сведения об экспорте архивных данных можно найти в статье [Export – CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) в документации по операциям.</span><span class="sxs-lookup"><span data-stu-id="50525-105">For details about exporting archived data, see [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) in the Operations documentation.</span></span>

<span data-ttu-id="50525-106">Если вы включаете интеграцию Microsoft Exchange, данные архивируются в хранилищах Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="50525-106">If you enable Microsoft Exchange integration, data is archived in Exchange 2013 stores.</span></span> <span data-ttu-id="50525-107">Данные, архивные в Exchange 2013, являются доступными для поиска и обнаружения.</span><span class="sxs-lookup"><span data-stu-id="50525-107">Data archived in Exchange 2013 is searchable and discoverable.</span></span> <span data-ttu-id="50525-108">Для получения дополнительных сведений о поддержке интегрированных коммуникаций для Exchange 2013 и Lync Server 2013, ознакомьтесь со статьей [Поддержка интеграции Exchange Server и SharePoint в Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) в документации по поддержке.</span><span class="sxs-lookup"><span data-stu-id="50525-108">For details about support for integrated communications for Exchange 2013 and Lync Server 2013, see [Exchange Server and SharePoint integration support in Lync Server 2013](lync-server-2013-exchange-and-sharepoint-integration-support.md) in the Supportability documentation.</span></span> <span data-ttu-id="50525-109">Сведения о доступе к данным, архивированным в Exchange, можно найти в документации по Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="50525-109">For details about accessing data that is archived in Exchange, see the Exchange 2013 documentation.</span></span>

<div>

## <a name="exporting-archiving-data-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="50525-110">Экспорт данных архивации с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="50525-110">Exporting Archiving Data by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="50525-111">Архивированные данные можно экспортировать с помощью командлета Export-CSArchivingData.</span><span class="sxs-lookup"><span data-stu-id="50525-111">Archiving data can be exported by using the Export-CSArchivingData cmdlet.</span></span> <span data-ttu-id="50525-112">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="50525-112">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="50525-113">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)статье Lync Server Windows PowerShell в блоге.</span><span class="sxs-lookup"><span data-stu-id="50525-113">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="50525-114">**Экспорт данных архивации**</span><span class="sxs-lookup"><span data-stu-id="50525-114">**To export archiving data**</span></span>

  - <span data-ttu-id="50525-115">Эта команда экспортирует все данные atl-sql-001.litwareinc.com, архивированные с 1 июня 2012 г.</span><span class="sxs-lookup"><span data-stu-id="50525-115">This command exports all the archiving data written to the archiving database atl-sql-001.litwareinc.com since June 1, 2012.</span></span> <span data-ttu-id="50525-116">Полученный выходной файл будет храниться в папке C:\\арчивинжекспортс.</span><span class="sxs-lookup"><span data-stu-id="50525-116">The resulting output file will be stored in the folder C:\\ArchivingExports.</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports"

<span data-ttu-id="50525-117">**Экспорт данных архивации для одного пользователя**</span><span class="sxs-lookup"><span data-stu-id="50525-117">**To export archiving data for a single user**</span></span>

  - <span data-ttu-id="50525-p105">Следующая команда экспортирует архивированные данные для одного пользователя: kenmyer@litwareinc.com. Для этого задается параметр UserUri, за которым указывается SIP-адрес пользователя. Пример:</span><span class="sxs-lookup"><span data-stu-id="50525-p105">The following command exports archiving data for a single user: kenmyer@litwareinc.com. This is done by including the UserUri parameter followed by the user’s SIP address. For example:</span></span>
    
        Export-CsArchivingData -Identity "ArchivingDatabase:atl-sql-001.litwareinc.com" -StartDate 6/1/2012 -OutputFolder "C:\ArchivingExports" -UserUri "sip:kenmyer@litwareinc.com"

<span data-ttu-id="50525-121">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [Export – CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) .</span><span class="sxs-lookup"><span data-stu-id="50525-121">For more information, see the help topic for the [Export-CsArchivingData](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="50525-122">См. также</span><span class="sxs-lookup"><span data-stu-id="50525-122">See Also</span></span>


[<span data-ttu-id="50525-123">Поддержка интеграции Exchange Server и SharePoint в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50525-123">Exchange Server and SharePoint integration support in Lync Server 2013</span></span>](lync-server-2013-exchange-and-sharepoint-integration-support.md)  


[<span data-ttu-id="50525-124">Export — CsArchivingData</span><span class="sxs-lookup"><span data-stu-id="50525-124">Export-CsArchivingData</span></span>](https://docs.microsoft.com/powershell/module/skype/Export-CsArchivingData)  
[<span data-ttu-id="50525-125">Управление архивированием Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50525-125">Managing Lync Server 2013 Archiving</span></span>](lync-server-2013-managing-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

