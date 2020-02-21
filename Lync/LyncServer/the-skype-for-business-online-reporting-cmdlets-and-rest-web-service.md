---
title: Командлеты отчетов в Skype для бизнеса Online и веб-служба REST
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: The Skype for Business Online reporting cmdlets and REST web service
ms:assetid: cadd73a7-c08a-4102-b73a-ccb3ad4987bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362845(v=OCS.15)
ms:contentKeyID: 56563409
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 63cbce4dda006bb45606a09eef29d8c47946ad2a
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-skype-for-business-online-reporting-cmdlets-and-rest-web-service"></a><span data-ttu-id="4b63c-102">Командлеты отчетов в Skype для бизнеса Online и веб-служба REST</span><span class="sxs-lookup"><span data-stu-id="4b63c-102">The Skype for Business Online reporting cmdlets and REST web service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b63c-103">_**Последнее изменение темы:** 2014-09-05_</span><span class="sxs-lookup"><span data-stu-id="4b63c-103">_**Topic Last Modified:** 2014-09-05_</span></span>

<span data-ttu-id="4b63c-104">В сочетании с функциями отчетов в Skype для бизнеса Online предоставляется доступ к пяти командлетам Windows PowerShell, которые помогают создавать эти отчеты, и могут использоваться администраторами для возврата настраиваемых отчетов.</span><span class="sxs-lookup"><span data-stu-id="4b63c-104">In conjunction with the reporting features, Skype for Business Online provides access to five Windows PowerShell cmdlets that help generate those reports and are also can be used by administrators to return customized reporting data.</span></span> <span data-ttu-id="4b63c-105">Skype для бизнеса Online также включает REST (передача состояния представления), который может использоваться разработчиками для получения настраиваемых сведений об отчетах.</span><span class="sxs-lookup"><span data-stu-id="4b63c-105">Skype for Business Online also includes the REST (Representational State Transfer), which can be used by developers to retrieve customized reporting information.</span></span>

<span data-ttu-id="4b63c-106">К командлетам отчетов, доступным для администраторов, относятся следующие:</span><span class="sxs-lookup"><span data-stu-id="4b63c-106">The reporting cmdlets available to administrators include:</span></span>

  - <span data-ttu-id="4b63c-107">Командлет Get-Csactiveuserreport используется, который предоставляет сведения о количестве активных пользователей (то есть пользователей, выполнивших вход в Skype для бизнеса Online и участвующих по крайней мере в одном одноранговом сеансе связи).</span><span class="sxs-lookup"><span data-stu-id="4b63c-107">Get-CsActiveUserReport, which provides information about the number of active users (that is, users who have logged on to Skype for Business Online and participated in at least one conference or peer-to-peer communication session).</span></span>

  - <span data-ttu-id="4b63c-108">Get-Ксавконференцетимерепорт, который предоставляет сведения об истечение времени (в минутах) пользователей, затраченных на аудио-и видеоконференции.</span><span class="sxs-lookup"><span data-stu-id="4b63c-108">Get-CsAVConferenceTimeReport, which provides information about the amount of time (in minutes) users spent in audio/video conferences.</span></span>

  - <span data-ttu-id="4b63c-109">Get – Ксконференцерепорт, который предоставляет сведения о количестве и типе конференций, в которых участвовали пользователи.</span><span class="sxs-lookup"><span data-stu-id="4b63c-109">Get-CsConferenceReport, which provides information about the number and type of conferences that users participated in.</span></span>

  - <span data-ttu-id="4b63c-110">Get-CsP2PAVTimeReport, который предоставляет сведения о времени (в минутах), затраченном на одноранговые сеансы, которые включали звук и/или видео.</span><span class="sxs-lookup"><span data-stu-id="4b63c-110">Get-CsP2PAVTimeReport, which provides information about the amount of time (in minutes) users spent in peer-to-peer sessions that included audio and/or video.</span></span>

  - <span data-ttu-id="4b63c-111">Get – CsP2PSessionReport, который предоставляет сведения о количестве и типе одноранговых сеансов, в которых участвовали пользователи.</span><span class="sxs-lookup"><span data-stu-id="4b63c-111">Get-CsP2PSessionReport, which provides information about the number and type of peer-to-peer sessions that users participated in.</span></span>

<span data-ttu-id="4b63c-112">Большинство администраторов будут использовать отчеты, доступные в центре администрирования Microsoft 365: не только автоматически создаваемые отчеты, но и предоставляют графическое представление данных, которые часто легче интерпретировать, чем необработанные значения, возвращаемые Командлеты создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="4b63c-112">Most administrators will use the reports available in the Microsoft 365 admin center: not only are those reports auto-generated, but they also provide a graphical representation of the data that is often easier to interpret than the raw number values returned by the reporting cmdlets.</span></span> <span data-ttu-id="4b63c-113">Однако администраторы, знакомые с Windows PowerShell, могут использовать командлеты отчетов, чтобы возвращать данные, которые не могут быть доступны в отчетах Lync Online.</span><span class="sxs-lookup"><span data-stu-id="4b63c-113">However, administrators familiar with Windows PowerShell can use the reporting cmdlets to return data that is not readily available from the Lync Online reports.</span></span> <span data-ttu-id="4b63c-114">Например, командлеты отчетов возвращают сведения о длительности сеанса (количество времени в минутах, в течение которого каждый сеанс длительность).</span><span class="sxs-lookup"><span data-stu-id="4b63c-114">For example, the reporting cmdlets return information about session duration (the amount of time, in minutes, that each session lasted).</span></span> <span data-ttu-id="4b63c-115">Отдельные длительности сеансов недоступны в отчетах Lync Online.</span><span class="sxs-lookup"><span data-stu-id="4b63c-115">Individual session durations are not available using the Lync Online reports.</span></span> <span data-ttu-id="4b63c-116">Аналогично, в представлении "ежедневно" в отчетах Lync Online отображаются сведения только за последние 14 дней.</span><span class="sxs-lookup"><span data-stu-id="4b63c-116">Likewise, in daily view the Lync Online reports display information only for the preceding 14 days.</span></span> <span data-ttu-id="4b63c-117">Если вы хотите просмотреть ежедневные итоговые значения за другой день (например, с даты по четыре месяца назад), можно использовать командлеты для создания отчетов.</span><span class="sxs-lookup"><span data-stu-id="4b63c-117">If you would like to review the daily totals for a different day (for example, a date from four months ago) you can do so by using the reporting cmdlets.</span></span>

<span data-ttu-id="4b63c-118">Администраторы также могут заинтересовать статью об [использовании Excel для получения данных отчетов office 365](https://msdn.microsoft.com/library/dn781442.aspx), в которой объясняется, как использовать функцию запросов данных OData в Microsoft Excel для создания настраиваемого отчета Office 365.</span><span class="sxs-lookup"><span data-stu-id="4b63c-118">Administrators might also be interested in the article [Using Excel to Retrieve Office 365 Reporting Data](https://msdn.microsoft.com/library/dn781442.aspx), which explains how to use the OData data querying feature in Microsoft Excel to create custom office 365 report.</span></span> <span data-ttu-id="4b63c-119">Настраиваемые отчеты дают возможность определять, какие данные (и какой объем данных) возвращаются из службы отчетов Office 365.</span><span class="sxs-lookup"><span data-stu-id="4b63c-119">Custom reports give you the ability to dictate which data (and how much data) is returned from the Office 365 reporting service.</span></span> <span data-ttu-id="4b63c-120">Настраиваемые отчеты также позволяют выполнять такие задачи, как указать порядок сортировки и группировки данных, а также предоставить доступ к информации, которая не отображается в центре администрирования.</span><span class="sxs-lookup"><span data-stu-id="4b63c-120">Custom reports also enable you to do such things as specify how the data should be sorted and grouped, and provide access to information that is not displayed in the admin center.</span></span>

<span data-ttu-id="4b63c-121">Администраторы с фоном разработки могут использовать веб-службу REST для получения сведений, не отображаемых в центре администрирования Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="4b63c-121">Administrators with a development background can use the REST web service to obtain information not displayed in the Skype for Business Online admin center.</span></span> <span data-ttu-id="4b63c-122">Служба REST похожа на службу SOAP, в которой каждая технология предоставляет способ переноса данных XML между клиентом и сервером.</span><span class="sxs-lookup"><span data-stu-id="4b63c-122">The REST service is similar to the SOAP service, in that each technology provides a way to transfer XML data between a client and a server.</span></span> <span data-ttu-id="4b63c-123">Однако служба REST имеет по крайней мере два преимущества по сравнению со службой SOAP.</span><span class="sxs-lookup"><span data-stu-id="4b63c-123">However, the REST service has at least two advantages over the SOAP service.</span></span> <span data-ttu-id="4b63c-124">Для одной функции REST выполняет передачу XML-данных с использованием стандартизированного формата, который называется форматом синдикации ATOM.</span><span class="sxs-lookup"><span data-stu-id="4b63c-124">For one, REST performs XML data transfers using a standardized format known as the ATOM syndication format.</span></span> <span data-ttu-id="4b63c-125">В отличие от этого, SOAP использует нестандартный формат при переносе данных.</span><span class="sxs-lookup"><span data-stu-id="4b63c-125">By contrast, SOAP using a non-standard format when transferring data.</span></span> <span data-ttu-id="4b63c-126">Кроме того, REST может передавать данные между сетями, которые блокируют HTTP-команды, отличные от GET и POST.</span><span class="sxs-lookup"><span data-stu-id="4b63c-126">In addition, REST is able to transfer data across networks that block HTTP verbs other than GET and POST.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="4b63c-127">См. также</span><span class="sxs-lookup"><span data-stu-id="4b63c-127">See Also</span></span>


<span data-ttu-id="4b63c-128">[Отчеты Lync Online](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4b63c-128">[Lync Online reporting](https://technet.microsoft.com/library/dn362827\(v=ocs.15\))</span></span>  


[<span data-ttu-id="4b63c-129">Веб-служба отчетов Office 365</span><span class="sxs-lookup"><span data-stu-id="4b63c-129">The Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984325.aspx)  
[<span data-ttu-id="4b63c-130">Изучение веб-службы отчетов Office 365</span><span class="sxs-lookup"><span data-stu-id="4b63c-130">Learning About the Office 365 Reporting Web Service</span></span>](https://msdn.microsoft.com/library/office/jj984321.aspx)  
<span data-ttu-id="4b63c-131">[Командлеты отчетов Exchange Online](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span><span class="sxs-lookup"><span data-stu-id="4b63c-131">[The Exchange Online Reporting Cmdlets](https://technet.microsoft.com/library/jj200780\(v=exchg.150\).aspx)</span></span>  
[<span data-ttu-id="4b63c-132">Использование Excel для получения отчетных данных Office 365</span><span class="sxs-lookup"><span data-stu-id="4b63c-132">Using Excel to Retrieve Office 365 Reporting Data</span></span>](https://msdn.microsoft.com/library/dn781442.aspx)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

