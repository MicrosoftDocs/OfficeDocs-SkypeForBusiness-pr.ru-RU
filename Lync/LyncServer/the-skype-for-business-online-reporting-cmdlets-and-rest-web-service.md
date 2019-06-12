---
title: Командлеты отчетности в Skype для бизнеса Online и веб-служба RESTFUL
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a140ed48ac662daea14d602f0830b2fbc4bf1c05
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34848893"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="68ee6-102">Командлеты отчетности в Skype для бизнеса Online и веб-служба RESTFUL</span><span class="sxs-lookup"><span data-stu-id="68ee6-102">The Skype for Business Online reporting cmdlets and REST web service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68ee6-103">_**Тема последнего изменения:** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="68ee6-103">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="68ee6-104">В сочетании с функциями отчетов Skype для бизнеса Online предоставляет доступ к пяти командлетам Windows PowerShell, которые помогают создавать эти отчеты, и они также могут использоваться администраторами, чтобы возвращать настраиваемые данные отчетов.</span><span class="sxs-lookup"><span data-stu-id="68ee6-104">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="68ee6-105">Skype для бизнеса Online также включает в себя (функцию пересылки состояния представления), которая может быть использована разработчиками для получения персональных данных отчетов.</span><span class="sxs-lookup"><span data-stu-id="68ee6-105">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="68ee6-106">Ниже перечислены командлеты отчетов, доступные для администраторов.</span><span class="sxs-lookup"><span data-stu-id="68ee6-106">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="68ee6-107">Get-Ксактивеусеррепорт, который предоставляет сведения о количестве активных пользователей (пользователей, которые вошли в Skype для бизнеса Online и участвовали хотя бы в одной конференции или одноранговом сеансе связи).</span><span class="sxs-lookup"><span data-stu-id="68ee6-107">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="68ee6-108">Get-Ксавконференцетимерепорт, который предоставляет сведения о течение времени (в минутах) пользователей, затраченных на аудио-и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="68ee6-108">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="68ee6-109">Get-Ксконференцерепорт, который предоставляет сведения о количестве и типах конференций, в которых участвовали пользователи.</span><span class="sxs-lookup"><span data-stu-id="68ee6-109">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="68ee6-110">Get-CsP2PAVTimeReport, который предоставляет сведения о течение времени (в минутах) пользователей, затраченных на одноранговые сеансы, которые включают звук и/или видео.</span><span class="sxs-lookup"><span data-stu-id="68ee6-110">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="68ee6-111">Get-CsP2PSessionReport, который предоставляет сведения о количестве и типе одноранговых сеансов, в которых участвовали пользователи.</span><span class="sxs-lookup"><span data-stu-id="68ee6-111">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="68ee6-112">Большинство администраторов будут использовать отчеты, доступные в центре администрирования Office 365: не только те, которые были автоматически сгенерированы, но и предоставляют графическое представление данных, которые часто проще интерпретировать, чем необработанные числовые значения, возвращаемые Командлеты для создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="68ee6-112">Most administrators will use the reports available in the Office 365 Admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="68ee6-113">Однако администраторы, знакомые с Windows PowerShell, могут использовать командлеты отчетов, чтобы возвращать данные, которые не будут доступны в отчетах Lync Online.</span><span class="sxs-lookup"><span data-stu-id="68ee6-113">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="68ee6-114">Например, командлеты для работы с отчетами возвращают сведения о длительности сеанса (в минутах), в течение которых ластед сеанса.</span><span class="sxs-lookup"><span data-stu-id="68ee6-114">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="68ee6-115">Некоторые длительности сеанса недоступны в отчетах Lync Online.</span><span class="sxs-lookup"><span data-stu-id="68ee6-115">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="68ee6-116">Аналогичным образом, в представлении ежедневно в отчете Lync Online отображаются данные только за предшествующие 14 дней.</span><span class="sxs-lookup"><span data-stu-id="68ee6-116">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="68ee6-117">Если вы хотите просмотреть ежедневные итоги за другой день (например, дату за четыре месяца назад), вы можете использовать командлеты для создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="68ee6-117">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="68ee6-118">Администраторы могут также заинтересовать статью, [используя Excel для получения данных отчетов office 365](http://msdn.microsoft.com/en-us/library/dn781442.aspx), в котором объясняется, как использовать функцию запроса данных OData в Microsoft Excel для создания настраиваемого отчета Office 365.</span><span class="sxs-lookup"><span data-stu-id="68ee6-118">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](http://msdn.microsoft.com/en-us/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="68ee6-119">Пользовательские отчеты позволяют определять, какие данные (и сколько данных) будут возвращаться из службы отчетов Office 365.</span><span class="sxs-lookup"><span data-stu-id="68ee6-119">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="68ee6-120">Кроме того, пользовательские отчеты позволяют задать способ сортировки и группировки данных и предоставить доступ к сведениям, которые не отображаются в центре администрирования Office 365.</span><span class="sxs-lookup"><span data-stu-id="68ee6-120">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the Office 365 Admin center.</span></span>

<span data-ttu-id="68ee6-121">Администраторы с фоном разработки могут использовать веб-службу RESTFUL для получения сведений, которые не отображаются в центре администрирования Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="68ee6-121">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="68ee6-122">Служба RESTFUL аналогична службе SOAP, так как каждая технология предоставляет способ передачи данных XML между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="68ee6-122">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="68ee6-123">Однако у службы RESTFUL есть по крайней мере два преимущества, чем служба SOAP.</span><span class="sxs-lookup"><span data-stu-id="68ee6-123">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="68ee6-124">Для одного из них функции RESTFUL выполняют передачу данных XML, используя стандартизированный формат, известный как формат объединения ATOM.</span><span class="sxs-lookup"><span data-stu-id="68ee6-124">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="68ee6-125">По сравнению с передачей данных протокол SOAP использует нестандартный формат.</span><span class="sxs-lookup"><span data-stu-id="68ee6-125">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="68ee6-126">Кроме того, остальное может передавать данные через сети, которые блокируют HTTP-глаголы, отличные от GET и POST.</span><span class="sxs-lookup"><span data-stu-id="68ee6-126">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="68ee6-127">См. также</span><span class="sxs-lookup"><span data-stu-id="68ee6-127">See Also</span></span>


<span data-ttu-id="68ee6-128">[Отчеты Lync Online](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="68ee6-128">[Lync Online reporting](https://technet.microsoft.com/en-us/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="68ee6-129">Веб-служба отчетов Office 365</span><span class="sxs-lookup"><span data-stu-id="68ee6-129">The Office 365 Reporting Web Service</span></span>](http://msdn.microsoft.com/en-us/library/office/jj984325.aspx)  
[<span data-ttu-id="68ee6-130">Знакомство с веб-службой отчетов Office 365</span><span class="sxs-lookup"><span data-stu-id="68ee6-130">Learning About the Office 365 Reporting Web Service</span></span>](http://msdn.microsoft.com/en-us/library/office/jj984321.aspx)  
<span data-ttu-id="68ee6-131">[Командлеты отчетов Exchange Online](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="68ee6-131">[The Exchange Online Reporting Cmdlets](http://technet.microsoft.com/en-us/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="68ee6-132">Получение данных отчетов Office 365 с помощью Excel</span><span class="sxs-lookup"><span data-stu-id="68ee6-132">Using Excel to Retrieve Office 365 Reporting Data</span></span>](http://msdn.microsoft.com/en-us/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

