---
title: 'Lync Server 2013: отчет по IP-телефонам'
description: 'Lync Server 2013: отчет по IP-телефонам.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bc05017775ad64e0e18f876215aa2c6b3882bd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575025"
---
# <a name="ip-phone-inventory-report-in-lync-server-2013"></a><span data-ttu-id="856d0-103">Отчет по инвентаризации IP-телефонов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="856d0-103">IP Phone Inventory Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="856d0-104">_**Последнее изменение темы:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="856d0-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="856d0-p101">Отчет по IP-телефонам предоставляет сведения о IP-телефонах, используемых в организации. В отчете по IP-телефонам содержится список IP-телефонов, которые использовались в течение периода, заданного при создании отчета. С помощью этого отчета администраторы могут получить сведения об устаревших телефонах, которые требуется заменить, а также сведения о редко используемых дорогостоящих телефонах. Эти данные могут использоваться при планировании покупки новых телефонов или перераспределении имеющихся телефонов. (Например, пользователь, который редко использует дорогостоящий телефон, может поменяться телефоном с пользователем, который использует телефон чаще.)</span><span class="sxs-lookup"><span data-stu-id="856d0-p101">The IP Phone Inventory Report reports information about the IP phones currently in use in your organization. The IP Inventory Report provides a detailed list of the IP phones that were actually used during the specified reporting period. Among other things, this report lets administrators know if there are any old, outdated phones still in use that should be replaced; it can also alert administrators to the fact that there are expensive phones in the organization that are rarely being used. That type of information can be invaluable when it comes time to purchase new phones or to redistribute existing phones. (For example, a user who rarely uses his or her expensive phone might be asked to swap phones with a user who uses his or her phone much more frequently.)</span></span>

<span data-ttu-id="856d0-110">Следует отметить, что этот отчет имеет некоторые ограничения для случая использования данных отчета в реальном складском учете.</span><span class="sxs-lookup"><span data-stu-id="856d0-110">It should be noted that this report does have a few limitations when it comes to being used as a true inventory report.</span></span> <span data-ttu-id="856d0-111">Для одного из них в отчете IP-телефон просто выводятся все телефоны, которые входили на сервер Lync Server в течение указанного периода времени, отсортированные по времени последнего входа в систему.</span><span class="sxs-lookup"><span data-stu-id="856d0-111">For one thing, the IP Phone Report simply lists all the phones that logged on to Lync Server during the specified time period, sorted by their last logon time.</span></span> <span data-ttu-id="856d0-112">Если телефон не выполнял вход в течение указанного периода времени, он будет отсутствовать в этом отчете.</span><span class="sxs-lookup"><span data-stu-id="856d0-112">If a phone did not log on during the specified time period then it will not be listed in the inventory report.</span></span> <span data-ttu-id="856d0-113">Это относится также к телефонам, которые выполнили вход до начального периода создания отчета и остаются в системе в течение указанного периода времени.</span><span class="sxs-lookup"><span data-stu-id="856d0-113">That includes phones that logged on before the time period started and were still logged on during the specified time interval.</span></span> <span data-ttu-id="856d0-114">Например, вы хотите найти все телефоны на июль 2012 г.</span><span class="sxs-lookup"><span data-stu-id="856d0-114">For example, suppose you wanted to look at all the phone inventory for July, 2012.</span></span> <span data-ttu-id="856d0-115">Предположим, что несколько телефонов, вошедших в Lync Server, 30 июня 2012 и вошли в систему с 1 по 1 июля.</span><span class="sxs-lookup"><span data-stu-id="856d0-115">Suppose, as well, that several phones logged on to Lync Server on June 30, 2012 and were still logged on as of July 1st.</span></span> <span data-ttu-id="856d0-116">Эти телефоны не будут добавлены в отчет за 1 июля 2012 г.</span><span class="sxs-lookup"><span data-stu-id="856d0-116">Those phones will not show up on the inventory report for July 1st.</span></span>

<span data-ttu-id="856d0-p103">Кроме того, отчет может содержать телефоны, которые уже не используются в организации. Например, несколько телефонов Fabrikam выполнили вход в систему 1 июля 2012 г., а 5 дней спустя организация заменила все телефоны Fabrikam новой моделью Contoso. Телефоны Fabrikam будут отображаться в отчете, поскольку они выполнили вход в систему в течение июля.</span><span class="sxs-lookup"><span data-stu-id="856d0-p103">It's also important to note that the inventory report could include phones that your organization no longer uses. For example, suppose a number of Fabrikam phones logged on to the system on July 1, 2012; 5 days later your organization got rid of all those Fabrikam phones and replaced them with a newer Contoso model. The Fabrikam phones will still appear on the "inventory" report simply because they logged on to the system during the month of July.</span></span>

<span data-ttu-id="856d0-p104">Кроме того, в отчете отсутствуют сведения о количестве разных моделей телефонов. Например, в организации установлено 105 телефонов модели Polycom CX600. В отчете вместо общего количества телефонов этой модели вы увидите 105 отдельных записей для телефонов Polycom Cx600. Чтобы узнать количество телефонов модели Polycom Cx600, потребуется посчитать количество строк вручную.</span><span class="sxs-lookup"><span data-stu-id="856d0-p104">In addition, the IP Phone Inventory Report does not report summary totals for the different types of phones. For example, suppose you have 105 Polycom CX600 phones. The report will not tell you that you have 105 of these phones; instead, you will simply see 105 separate entries for the Polycom Cx600. The only way to know that there are 105 entries for the Polycom Cx600 would be to count each of those entries manually.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="856d0-124">В качестве альтернативного варианта можно экспортировать данные в Microsoft Excel или Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="856d0-124">Or, export the data and use Microsoft Excel or Windows PowerShell to do that counting for you.</span></span>



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a><span data-ttu-id="856d0-125">Доступ к отчету по IP-телефонам</span><span class="sxs-lookup"><span data-stu-id="856d0-125">Accessing the IP Phone Inventory Report</span></span>

<span data-ttu-id="856d0-p105">Для доступа к отчету по IP-телефонам используется домашняя страница Monitoring Reports (Отчеты мониторинга). При выборе показателя User URI (URI пользователя) откроется отчет User Activity Report (Действия пользователя). При выборе показателя Last activity (Последнее действие) для одноранговых звонков откроется отчет Peer-to-Peer Session Detail Report (Сведения об одноранговом сеансе). При выборе того же показателя для конференции откроется отчет Conference Detail Report (Сведения о конференции).</span><span class="sxs-lookup"><span data-stu-id="856d0-p105">The IP Phone Inventory Report is accessed from the Monitoring Reports home page. If you click the User URI metric you can access the User Activity Report for that user. Clicking the Last activity metric for a peer-to-peer call will take you to the Peer-to-Peer Session Detail Report; clicking that same metric for a conference will take you to the Conference Detail Report.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a><span data-ttu-id="856d0-129">Рекомендации по использованию отчета по IP-телефонам</span><span class="sxs-lookup"><span data-stu-id="856d0-129">Making the Best Use of the IP Phone Inventory Report</span></span>

<span data-ttu-id="856d0-130">Если вы заинтересованы в сведениях об использовании только для одного определенного типа телефона (например, "как часто пользователи используют Polycom CX600 телефона?"), вы можете получить эти сведения непосредственно из отчета по IP-телефонам, выполнив фильтрацию по данному конкретному типу телефона.</span><span class="sxs-lookup"><span data-stu-id="856d0-130">If you're only interested in usage information for one particular kind of phone (for example, "How often are users using a Polycom CX600 phone?") you can get that information directly from the IP Phone Inventory Report by filtering for that particular kind of phone.</span></span> <span data-ttu-id="856d0-131">Тем не менее, если вы хотите получить сводную информацию для всех телефонов (количество людей, использующих Polycom CX600, сколько используется LG-Nortel IP8540 и т. д.), то вам потребуется экспортировать данные и использовать другое приложение (например, Windows PowerShell) для этого типа анализа.</span><span class="sxs-lookup"><span data-stu-id="856d0-131">However, if you want summary information for all your phones (how many people are using a Polycom CX600, how many are using an LG-Nortel IP8540, etc.) then you will need to export the data and use another application (such as Windows PowerShell) to do that type of analysis.</span></span> <span data-ttu-id="856d0-132">Например, предположим, что данные экспортируются в файл значений с разделителями-запятыми (C: \\ \\ \_ Inventory Data \_ \_Report.csv).</span><span class="sxs-lookup"><span data-stu-id="856d0-132">For example, suppose you export the data to a comma-separated values file (C:\\Data\\IP\_Phone\_Inventory\_Report.csv).</span></span> <span data-ttu-id="856d0-133">В этом случае вы можете использовать эти две команды для предоставления сводных данных для всех телефонов:</span><span class="sxs-lookup"><span data-stu-id="856d0-133">In that case, you could use these two commands to provide summary data for all your phones:</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

<span data-ttu-id="856d0-134">Команды возвращают данные, схожие со следующими:</span><span class="sxs-lookup"><span data-stu-id="856d0-134">That will return data similar to this:</span></span>

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

<span data-ttu-id="856d0-135">Следующие команды возвращают сведения о телефонах, которые выполнили вход в систему, но никогда не использовались для звонков (на это указывает отсутствие значения показателя Last activity (Последнее действие)):</span><span class="sxs-lookup"><span data-stu-id="856d0-135">Similarly, these two commands tell you which phones logged on to the system but were never actually used to make a call (the value of the Last activity metric is blank, indicating that there hasn't been any last activity):</span></span>

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

<span data-ttu-id="856d0-136">Команды возвращают данные, схожие со следующими:</span><span class="sxs-lookup"><span data-stu-id="856d0-136">That returns data similar to this for each phone that has not been used:</span></span>

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

<span data-ttu-id="856d0-137">Другой интересный способ использования отчета по IP-телефонам: если у IP-телефона есть MAC-адрес, то для получения сведений о пользователе, который использовал этот телефон последним, введите требуемый MAC-адрес в соответствующее поле.</span><span class="sxs-lookup"><span data-stu-id="856d0-137">Another interesting way to use the IP Phone Inventory Report is this: if you have the MAC address of an IP Phone you can find out the user who last used that phone simply by entering that address in the MAC address text box.</span></span> <span data-ttu-id="856d0-138">Отчет по IP-телефонам вернет SIP-адрес последнего пользователя, выполнившего вход в систему.</span><span class="sxs-lookup"><span data-stu-id="856d0-138">The IP Phone Inventory report will then report back (among other things) the SIP address of the user who last logged on with that phone.</span></span> <span data-ttu-id="856d0-139">В качестве альтернативного варианта для поиска всех телефонов, используемых этим пользователем, введите SIP-адрес пользователя (в поле User URI (URI пользователя)).</span><span class="sxs-lookup"><span data-stu-id="856d0-139">Alternatively, you can enter a user SIP address (in the User URI prefix box) to find out all the phones that have been used by that user.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="856d0-140">Фильтры</span><span class="sxs-lookup"><span data-stu-id="856d0-140">Filters</span></span>

<span data-ttu-id="856d0-p108">Фильтры позволяют получить более детализированный набор данных или изменить способ просмотра возвращаемых данных. Например, с помощью отчета по IP-телефонам можно получить сведения о телефонах определенного производителя или телефонах конкретной модели. Кроме того, вы можете задать параметры группировки данных. В этом случае регистрации группируются по часам, дням, неделям или месяцам.</span><span class="sxs-lookup"><span data-stu-id="856d0-p108">Filters provide a way for you to return a more finely-targeted set of data or to view the returned data in different ways. For example, the IP Phone Inventory enables you to view only the phones manufactured by a specific company, or even a specific version of those phones. You can also choose how data should be grouped. In this case, registrations are grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="856d0-145">В следующей таблице перечислены фильтры, доступные в отчете по IP-телефонам.</span><span class="sxs-lookup"><span data-stu-id="856d0-145">The following table lists the filters that you can use with the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-filters"></a><span data-ttu-id="856d0-146">Фильтры отчета по IP-телефонам</span><span class="sxs-lookup"><span data-stu-id="856d0-146">IP Phone Inventory Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="856d0-147">Имя</span><span class="sxs-lookup"><span data-stu-id="856d0-147">Name</span></span></th>
<th><span data-ttu-id="856d0-148">Описание</span><span class="sxs-lookup"><span data-stu-id="856d0-148">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="856d0-149"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="856d0-149"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-p109">Дата и время начала диапазона. Чтобы просмотреть данные по часам, введите дату и время начала в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="856d0-p109">Start date/time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="856d0-152">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="856d0-152">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="856d0-p110">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="856d0-p110">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="856d0-155">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="856d0-155">7/7/2012</span></span></p>
<p><span data-ttu-id="856d0-156">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="856d0-156">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="856d0-157">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="856d0-157">7/3/2012</span></span></p>
<p><span data-ttu-id="856d0-158">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="856d0-158">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856d0-159"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="856d0-159"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-p111">Дата и время окончания диапазона. Чтобы просмотреть данные по часам, введите дату и время окончания в следующем формате:</span><span class="sxs-lookup"><span data-stu-id="856d0-p111">End date/time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="856d0-162">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="856d0-162">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="856d0-p112">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="856d0-p112">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="856d0-165">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="856d0-165">7/7/2012</span></span></p>
<p><span data-ttu-id="856d0-166">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="856d0-166">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="856d0-167">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="856d0-167">7/3/2012</span></span></p>
<p><span data-ttu-id="856d0-168">Первым днем недели считается воскресенье, а последним — суббота.</span><span class="sxs-lookup"><span data-stu-id="856d0-168">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="856d0-169"><strong>Вычислитель</strong></span><span class="sxs-lookup"><span data-stu-id="856d0-169"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-p113">Название компании, создавшей IP-телефон. Значения для данного фильтра заполняются автоматически на основе данных об IP-телефонах, хранящихся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="856d0-p113">Name of the company that manufactured the IP phone. The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856d0-172"><strong>Hardware version</strong> (Версия оборудования)</span><span class="sxs-lookup"><span data-stu-id="856d0-172"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-173">Номер версии IP-телефона; используя производители и фильтры аппаратных версий, вы можете уникальным образом идентифицировать конкретный тип телефона.</span><span class="sxs-lookup"><span data-stu-id="856d0-173">Version number of the IP phone; by using the Manufacturer and the Hardware version filters you can uniquely identity a particular type of phone.</span></span> <span data-ttu-id="856d0-174">Значения для данного фильтра заполняются автоматически на основе данных об IP-телефонах, хранящихся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="856d0-174">The values for this filter are automatically populated for you based on the IP phones that are currently in the database.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="856d0-175"><strong>User agent</strong> (Агент пользователя)</span><span class="sxs-lookup"><span data-stu-id="856d0-175"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-p115">Идентификатор программного обеспечения, используемого IP-телефоном. Значения для данного фильтра заполняются автоматически на основе данных об IP-телефонах, хранящихся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="856d0-p115">Identifier for the software used by the IP phone. The values for this filter are automatically populated for you based on the IP phones currently in the database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856d0-178"><strong>MAC address</strong> (MAC-адрес)</span><span class="sxs-lookup"><span data-stu-id="856d0-178"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-p116">Уникальный идентификатор сетевого интерфейса IP-телефона. Обычно MAC-адрес задается производителем и не поддерживает изменение.</span><span class="sxs-lookup"><span data-stu-id="856d0-p116">Unique identifier for the network interface on the IP phone. The Media Access Control (MAC) address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p>
<p><span data-ttu-id="856d0-p117">Чтобы найти записи, относящиеся к определенному MAC-адресу, введите требуемый MAC-адрес. Пример:</span><span class="sxs-lookup"><span data-stu-id="856d0-p117">To search for records pertaining to a specific MAC address simply enter that address. For example:</span></span></p>
<p><span data-ttu-id="856d0-183">00 – 8 – 5D – 16-16-48</span><span class="sxs-lookup"><span data-stu-id="856d0-183">00-08-5D-16-16-48</span></span></p>
<p><span data-ttu-id="856d0-p118">Требуется вводить полные адреса. При вводе части адреса (например, 00-08-5D) данные не будут возвращены.</span><span class="sxs-lookup"><span data-stu-id="856d0-p118">You must enter the complete address. A partial address (for example 00-08-5D) does not return any data.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="856d0-186"><strong>Last activity before days</strong> (Последние действия за период)</span><span class="sxs-lookup"><span data-stu-id="856d0-186"><strong>Last activity before days</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-187">Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="856d0-187">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="856d0-188">Ко</span><span class="sxs-lookup"><span data-stu-id="856d0-188">[All]</span></span></p></li>
<li><p><span data-ttu-id="856d0-189">10 </span><span class="sxs-lookup"><span data-stu-id="856d0-189">10</span></span></p></li>
<li><p><span data-ttu-id="856d0-190">двадцать</span><span class="sxs-lookup"><span data-stu-id="856d0-190">20</span></span></p></li>
<li><p><span data-ttu-id="856d0-191">более</span><span class="sxs-lookup"><span data-stu-id="856d0-191">30</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856d0-192"><strong>Last logoff time before days</strong> (Последние выходы за период)</span><span class="sxs-lookup"><span data-stu-id="856d0-192"><strong>Last logoff time before days</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-193">Выберите одно из следующих значений:</span><span class="sxs-lookup"><span data-stu-id="856d0-193">Select one of the following values:</span></span></p>
<ul>
<li><p><span data-ttu-id="856d0-194">Ко</span><span class="sxs-lookup"><span data-stu-id="856d0-194">[All]</span></span></p></li>
<li><p><span data-ttu-id="856d0-195">10 </span><span class="sxs-lookup"><span data-stu-id="856d0-195">10</span></span></p></li>
<li><p><span data-ttu-id="856d0-196">двадцать</span><span class="sxs-lookup"><span data-stu-id="856d0-196">20</span></span></p></li>
<li><p><span data-ttu-id="856d0-197">более</span><span class="sxs-lookup"><span data-stu-id="856d0-197">30</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="856d0-198"><strong>User URI prefix</strong> (Префикс URI пользователя)</span><span class="sxs-lookup"><span data-stu-id="856d0-198"><strong>User URI prefix</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-199">SIP-адрес пользователя, который использует IP-телефон.</span><span class="sxs-lookup"><span data-stu-id="856d0-199">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="856d0-200">Метрики</span><span class="sxs-lookup"><span data-stu-id="856d0-200">Metrics</span></span>

<span data-ttu-id="856d0-201">В следующей таблице перечислены сведения, доступные в отчете по IP-телефонам.</span><span class="sxs-lookup"><span data-stu-id="856d0-201">The following table lists the information provided in the IP Phone Inventory Report.</span></span>

### <a name="ip-phone-inventory-report-metrics"></a><span data-ttu-id="856d0-202">Показатели отчета по IP-телефонам</span><span class="sxs-lookup"><span data-stu-id="856d0-202">IP Phone Inventory Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="856d0-203">Имя</span><span class="sxs-lookup"><span data-stu-id="856d0-203">Name</span></span></th>
<th><span data-ttu-id="856d0-204">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="856d0-204">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="856d0-205">Описание</span><span class="sxs-lookup"><span data-stu-id="856d0-205">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="856d0-206"><strong>Вычислитель</strong></span><span class="sxs-lookup"><span data-stu-id="856d0-206"><strong>Manufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-207">Да</span><span class="sxs-lookup"><span data-stu-id="856d0-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="856d0-208">Название компании, создавшей IP-телефон.</span><span class="sxs-lookup"><span data-stu-id="856d0-208">Name of the company that manufactured the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856d0-209"><strong>Hardware version</strong> (Версия оборудования)</span><span class="sxs-lookup"><span data-stu-id="856d0-209"><strong>Hardware version</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-210">Да</span><span class="sxs-lookup"><span data-stu-id="856d0-210">Yes</span></span></p></td>
<td><p><span data-ttu-id="856d0-211">Номер версии IP-телефона.</span><span class="sxs-lookup"><span data-stu-id="856d0-211">Version number of the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="856d0-212"><strong>MAC address</strong> (MAC-адрес)</span><span class="sxs-lookup"><span data-stu-id="856d0-212"><strong>MAC address</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-213">Да</span><span class="sxs-lookup"><span data-stu-id="856d0-213">Yes</span></span></p></td>
<td><p><span data-ttu-id="856d0-p119">Уникальный идентификатор сетевого интерфейса IP-телефона. Обычно MAC-адрес задается производителем и не поддерживает изменение.</span><span class="sxs-lookup"><span data-stu-id="856d0-p119">Unique identifier for the network interface on the IP phone. The MAC address is typically assigned at the time the phone is manufactured and is hard-wired into the device hardware.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856d0-216"><strong>User URI</strong> (URI пользователя)</span><span class="sxs-lookup"><span data-stu-id="856d0-216"><strong>User URI</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-217">Да</span><span class="sxs-lookup"><span data-stu-id="856d0-217">Yes</span></span></p></td>
<td><p><span data-ttu-id="856d0-218">SIP-адрес пользователя, который использует IP-телефон.</span><span class="sxs-lookup"><span data-stu-id="856d0-218">SIP address of the user who used the IP phone.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="856d0-219"><strong>User agent</strong> (Агент пользователя)</span><span class="sxs-lookup"><span data-stu-id="856d0-219"><strong>User agent</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-220">Да</span><span class="sxs-lookup"><span data-stu-id="856d0-220">Yes</span></span></p></td>
<td><p><span data-ttu-id="856d0-221">Идентификатор программного обеспечения, используемого IP-телефоном.</span><span class="sxs-lookup"><span data-stu-id="856d0-221">Identifier for the software used by the IP phone.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856d0-222"><strong>Last logon time</strong> (Время последнего входа)</span><span class="sxs-lookup"><span data-stu-id="856d0-222"><strong>Last logon time</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-223">Да</span><span class="sxs-lookup"><span data-stu-id="856d0-223">Yes</span></span></p></td>
<td><p><span data-ttu-id="856d0-224">Дата и время последнего входа в Lync Server с помощью IP-телефона.</span><span class="sxs-lookup"><span data-stu-id="856d0-224">Date and time that the IP phone last logged on to Lync Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="856d0-225"><strong>Last logoff time</strong> (Время последнего выхода)</span><span class="sxs-lookup"><span data-stu-id="856d0-225"><strong>Last logoff time</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-226">Да</span><span class="sxs-lookup"><span data-stu-id="856d0-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="856d0-227">Дата и время последнего выхода из Lync Server для IP-телефона.</span><span class="sxs-lookup"><span data-stu-id="856d0-227">Date and time that the IP phone last logged off from Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="856d0-228"><strong>Last activity</strong> (Последние действия)</span><span class="sxs-lookup"><span data-stu-id="856d0-228"><strong>Last activity</strong></span></span></p></td>
<td><p><span data-ttu-id="856d0-229">Да</span><span class="sxs-lookup"><span data-stu-id="856d0-229">Yes</span></span></p></td>
<td><p><span data-ttu-id="856d0-230">Дата и время последнего использования IP-телефона.</span><span class="sxs-lookup"><span data-stu-id="856d0-230">Date and time that the IP phone was last used.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

