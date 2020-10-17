---
title: 'Lync Server 2013: отчет о регистрации пользователей'
description: 'Lync Server 2013: отчет о регистрации пользователей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Registration Report
ms:assetid: 151d5cc9-cc1b-4cfa-be9c-55ebe321f7a4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558614(v=OCS.15)
ms:contentKeyID: 48183486
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7adb8ef7e94a24f0fd088f12e009fc9d63f3be9d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569755"
---
# <a name="user-registration-report-in-lync-server-2013"></a><span data-ttu-id="53953-103">Отчет о регистрации пользователей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53953-103">User Registration Report in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53953-104">_**Последнее изменение темы:** 2012-10-21_</span><span class="sxs-lookup"><span data-stu-id="53953-104">_**Topic Last Modified:** 2012-10-21_</span></span>

<span data-ttu-id="53953-105">В отчете о регистрации пользователей представлены общие сведения о действиях входа пользователей, в том числе сведения о количестве пользователей, выполнивших вход в Microsoft Lync Server 2013 в течение определенного периода времени (ежечасно, ежедневно, еженедельно, ежемесячно).</span><span class="sxs-lookup"><span data-stu-id="53953-105">The User Registration Report provides an overview of user logon activity, most notably information about the number of users who logged on to Microsoft Lync Server 2013 during a specified time period (hourly, daily, weekly, monthly).</span></span> <span data-ttu-id="53953-106">Следует иметь в виду, что в отчете лишь сообщается, сколько людей входило в систему.</span><span class="sxs-lookup"><span data-stu-id="53953-106">Keep in mind that the report only tells you how many people logged on.</span></span> <span data-ttu-id="53953-107">В нем не указывается, *какие* люди входили в систему.</span><span class="sxs-lookup"><span data-stu-id="53953-107">It does not tell you *which* people logged on.</span></span> <span data-ttu-id="53953-108">Отчеты мониторинга не предоставляют сведения о том, какие конкретные пользователи используют Lync Server 2013 (и какие из них не являются).</span><span class="sxs-lookup"><span data-stu-id="53953-108">Monitoring Reports do not provide information about which specific users are using Lync Server 2013 (and which ones are not).</span></span> <span data-ttu-id="53953-109">Тем не менее с помощью отчета об активности пользователей можно получить грубую оценку пользовательской информации.</span><span class="sxs-lookup"><span data-stu-id="53953-109">However, you can get a rough estimate of user information by using the User Activity Report.</span></span>

<span data-ttu-id="53953-110">При предоставлении сведений о входах пользователей в систему в отчете о регистрации пользователей делается два важных разграничения.</span><span class="sxs-lookup"><span data-stu-id="53953-110">When providing information about user logons, the User Registration Report draws two important distinctions.</span></span> <span data-ttu-id="53953-111">Во-первых, в отчете входы в систему разбиваются на две основные категории: внутренние и внешние входы в систему.</span><span class="sxs-lookup"><span data-stu-id="53953-111">First, it breaks logons down into two primary categories: internal logons and external logons.</span></span> <span data-ttu-id="53953-112">Внутренние входы представляют пользователей, вошедших в систему с внутренней стороны брандмауэра организации (то есть, с компьютера, подключенного к корпоративной сети).</span><span class="sxs-lookup"><span data-stu-id="53953-112">Internal logons represent users who logged on from inside your organization's firewall (that is, while connected to the corporate network).</span></span> <span data-ttu-id="53953-113">Внешние входы представляют пользователей, которые входили в систему за пределами брандмауэра через пограничный сервер (например, пользователь, вошедший в Интернет-кафе, считает как внешний вход).</span><span class="sxs-lookup"><span data-stu-id="53953-113">External logons represent users who logged on from outside the firewall through an Edge Server (for example, a user who logged on from an Internet café counts as an external logon).</span></span> <span data-ttu-id="53953-114">Если необходимо узнать, сколько пользователей входит в систему с внешней стороны брандмауэра, эти сведения можно найти в отчете о регистрации пользователей.</span><span class="sxs-lookup"><span data-stu-id="53953-114">If you need to know how many of your users are logging on from outside the firewall, the User Registration Report can provide you with this information.</span></span>

<span data-ttu-id="53953-115">Кроме того, в отчете о регистрации пользователей отмечается, сколько *активных* пользователей присутствовало в течение заданного периода времени.</span><span class="sxs-lookup"><span data-stu-id="53953-115">In addition, the User Registration Report notes how many *active* users were present during a given time period.</span></span> <span data-ttu-id="53953-116">Активный пользователь — это пользователь, который выполнил участие в сеансе обмена мгновенными сообщениями, который участвовал в собрании Lync, выполнил или получил телефонный звонок, или в других случаях использует Lync Server в течение этого периода времени.</span><span class="sxs-lookup"><span data-stu-id="53953-116">An active user is a user who took part in an instant messaging (IM) session, participated in a Lync Meeting, made or received a phone call, or otherwise used Lync Server during that period of time.</span></span> <span data-ttu-id="53953-117">Такой пользователь отличается от пользователя, вошедшего в систему, но не проявлявшего никакой активности в системе.</span><span class="sxs-lookup"><span data-stu-id="53953-117">This is different from a user who logged on, but never actually used the system.</span></span>

<div>

## <a name="accessing-the-user-registration-report"></a><span data-ttu-id="53953-118">Доступ к отчету о регистрации пользователей</span><span class="sxs-lookup"><span data-stu-id="53953-118">Accessing the User Registration Report</span></span>

<span data-ttu-id="53953-p104">Доступ к отчету о регистрации пользователей предоставляется только на домашней странице отчетов мониторинга. Отчет о регистрации пользователей не связан с какими-либо другими отчетами.</span><span class="sxs-lookup"><span data-stu-id="53953-p104">You access the User Registration Report only from the Monitoring Reports home page. The User Registration Report does not link to any other reports.</span></span>

</div>

<div>

## <a name="making-the-best-use-of-the-user-registration-report"></a><span data-ttu-id="53953-121">Оптимальное использование отчета о регистрации пользователей</span><span class="sxs-lookup"><span data-stu-id="53953-121">Making the Best Use of the User Registration Report</span></span>

<span data-ttu-id="53953-122">Когда вы развернули сервер Lync Server, выполните следующие действия: как узнать, действительно ли пользователи используют эту новую технологию?</span><span class="sxs-lookup"><span data-stu-id="53953-122">After you've deployed Lync Server one commonly-asked question is this: How do I know if my users are actually using this new technology?</span></span> <span data-ttu-id="53953-123">Хотя в этом отношении есть определенные ограничения, отчет о регистрации пользователей позволяет ответить на этот вопрос.</span><span class="sxs-lookup"><span data-stu-id="53953-123">Although it has a few limitations in this regard, the User Registration Report can help you answer this question.</span></span> <span data-ttu-id="53953-124">Чтобы определить, используются ли Lync Server пользователями, необходимо выполнить два действия.</span><span class="sxs-lookup"><span data-stu-id="53953-124">To determine whether or not users are using Lync Server, you need to do two things.</span></span> <span data-ttu-id="53953-125">Во-первых, нужно получить значение показателя уникальных входов пользователей из отчета о регистрации пользователей.</span><span class="sxs-lookup"><span data-stu-id="53953-125">First, get the value of the Unique logon users metric from the User Registration Report.</span></span> <span data-ttu-id="53953-126">Это значение указывает, сколько отдельных участников вошли в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53953-126">This value tells you how many distinct individuals logged on to Lync Server.</span></span>

<span data-ttu-id="53953-127">При сравнении метрика общего числа входов показывает общее количество пользователей, выполнивших вход в Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53953-127">By comparison, the Total logons metric shows how many total times anyone logged on to Lync Server.</span></span> <span data-ttu-id="53953-128">Например, пусть Кен Myer вошел на Lync Server пять раз в один день.</span><span class="sxs-lookup"><span data-stu-id="53953-128">For example, suppose Ken Myer logged on to Lync Server five different times in a single day.</span></span> <span data-ttu-id="53953-129">В этом случае для Кен Майера было бы подсчитано пять отдельных сеансов входа в показателе общего числа входов, но лишь один зарегистрированный пользователь в показателе уникальных зарегистрированных пользователей.</span><span class="sxs-lookup"><span data-stu-id="53953-129">In that case, Ken Myer would count as five separate logon sessions for the Total logons metric, but just one logon user for the Unique logon users metric.</span></span> <span data-ttu-id="53953-130">Аналогично, пользователи нередко входят в систему с нескольких устройств или из нескольких мест.</span><span class="sxs-lookup"><span data-stu-id="53953-130">Likewise, it's not uncommon for a user to log on from multiple devices or multiple locations.</span></span> <span data-ttu-id="53953-131">Например, пользователь может войти в систему с помощью настольного компьютера, его портативного компьютера, а также может иметь IP-телефон, который автоматически выполняет вход на Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53953-131">For example, a user can log on using her desktop computer, her laptop computer, and she can have an IP phone that automatically logs on to Lync Server.</span></span> <span data-ttu-id="53953-132">В этом примере имеется один уникальный пользователь с тремя входами в систему.</span><span class="sxs-lookup"><span data-stu-id="53953-132">In this example, there is one unique user with three logons.</span></span>

<span data-ttu-id="53953-133">Для дальнейшего пояснения разницы между общим количеством входов и уникальными входами рассмотрим входы в систему для заданного периода времени, приведенные в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="53953-133">To further explain the difference between total logons and unique logons, consider the logons for a given time period in the following table.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53953-134">Пользователь</span><span class="sxs-lookup"><span data-stu-id="53953-134">User</span></span></th>
<th><span data-ttu-id="53953-135">Время входа</span><span class="sxs-lookup"><span data-stu-id="53953-135">Logon time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53953-136">Кен Майер</span><span class="sxs-lookup"><span data-stu-id="53953-136">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="53953-137">07.07.2012 08:45:00</span><span class="sxs-lookup"><span data-stu-id="53953-137">7/7/2012 8:45 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53953-138">Кен Майер</span><span class="sxs-lookup"><span data-stu-id="53953-138">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="53953-139">07.07.2012 08:46:00</span><span class="sxs-lookup"><span data-stu-id="53953-139">7/7/2012 8:46 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53953-140">Пилар Аккерман</span><span class="sxs-lookup"><span data-stu-id="53953-140">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="53953-141">07.07.2012 09:17:00</span><span class="sxs-lookup"><span data-stu-id="53953-141">7/7/2012 9:17 AM</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53953-142">Кен Майер</span><span class="sxs-lookup"><span data-stu-id="53953-142">Ken Myer</span></span></p></td>
<td><p><span data-ttu-id="53953-143">07.07.2012 09:22:00</span><span class="sxs-lookup"><span data-stu-id="53953-143">7/7/2012 9:22 AM</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53953-144">Пилар Аккерман</span><span class="sxs-lookup"><span data-stu-id="53953-144">Pilar Ackerman</span></span></p></td>
<td><p><span data-ttu-id="53953-145">07.07.2012 09:31:00</span><span class="sxs-lookup"><span data-stu-id="53953-145">7/7/2012 9:31 AM</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="53953-p107">Обратите внимание, что общее количество входов в систему равно пяти; однако существует только два уникальных регистрировавшихся пользователя: Кен Майер (входивший в систему три раза) и Пилар Аккерман (заходивший в систему дважды). В этом разница между входами в систему и уникальными регистрировавшимися пользователями.</span><span class="sxs-lookup"><span data-stu-id="53953-p107">Notice that there is a total of five logons; however, there are only two unique logon users: Ken Myer (who logged on three times) and Pilar Ackerman (who logged on twice). That's the difference between logons and unique logon users.</span></span>

<span data-ttu-id="53953-148">Кроме того, чтобы узнать количество уникальных входов в систему, необходимо знать общее количество пользователей, для которых была включена поддержка Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53953-148">In addition to knowing the number of unique logons, you need to know the total number of users who have been enabled for Lync Server.</span></span> <span data-ttu-id="53953-149">Это значение можно получить, открыв командную консоль Lync Server 2013 и выполнив следующую команду Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="53953-149">That value can be retrieved by opening the Lync Server 2013 Management Shell and running the following Windows PowerShell command:</span></span>

    (Get-CsUser).Count

<span data-ttu-id="53953-150">Если предыдущая команда возвращает значение 1 236, то метрика для пользователей с уникальным входом Возвращает среднее значение 667, что означает, что немного больше половины пользователей, которым разрешите Lync, будут на самом деле входить в систему каждый день (то есть 667 на 1 236, то есть приблизительно 54%).</span><span class="sxs-lookup"><span data-stu-id="53953-150">If the preceding command returns a value of 1,236 and Unique logon users metric returns an average value of 667, that suggests that a little over half of your users enable for Lync are actually logging on to the system each day (that is, 667 divided by 1,236, which is approximately 54%).</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="53953-151">Следует иметь в виду, что показателями входов учитываются пользователи, которые на самом деле входили в систему в указанный период времени.</span><span class="sxs-lookup"><span data-stu-id="53953-151">Keep in mind that the logon metrics record users who actually logged on during the specified time period.</span></span> <span data-ttu-id="53953-152">Они не учитывают пользователей, которые уже были зарегистрированы в системе.</span><span class="sxs-lookup"><span data-stu-id="53953-152">They don't keep track of users who were already logged on to the system.</span></span> <span data-ttu-id="53953-153">Например, если показатель количества уникальных регистрировавшихся пользователей равен 667 и имеется 1236 пользователей, это свидетельствует о том, что около половины пользователей входят в систему.</span><span class="sxs-lookup"><span data-stu-id="53953-153">For example, if your Unique logon users metric shows 667 logons and you have 1,236 users, that suggests that about half your users are logging on to the system.</span></span> <span data-ttu-id="53953-154">Однако предположим, что 300 пользователей уже находились в системе на момент, когда началась проверка данных о регистрации.</span><span class="sxs-lookup"><span data-stu-id="53953-154">However, suppose 300 users were already logged on to the system at the time you began checking the logon data.</span></span> <span data-ttu-id="53953-155">Это означает, что у вас есть почти 1 000 пользователей, выполнивших вход в Lync Server, что означает, что ближе к 80% пользователей были зарегистрированы.</span><span class="sxs-lookup"><span data-stu-id="53953-155">That would mean that you actually had nearly 1,000 users logged on to Lync Server, which would mean that closer to 80% of your users were logged on.</span></span>



</div>

<span data-ttu-id="53953-156">Следует также сравнить значение показателя количества уникальных регистрировавшихся пользователей со значением показателя количества уникальных активных пользователей.</span><span class="sxs-lookup"><span data-stu-id="53953-156">You should also compare the Unique logon users value with the value of the Unique active users metric.</span></span> <span data-ttu-id="53953-157">Метрика уникального активного пользователя указывает, сколько уникальных пользователей использовало Lync Server: они были присоединены к собранию Lync или участвуют в сеансе обмена мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="53953-157">The Unique active users metric tells you how many unique users actually used Lync Server: they made a phone call, they joined a Lync Meeting, or they participated in an IM session.</span></span> <span data-ttu-id="53953-158">Это полезная информация, так как Microsoft Lync 2013 может быть настроен для автоматического запуска при каждом запуске Windows пользователем.</span><span class="sxs-lookup"><span data-stu-id="53953-158">This is useful information, because Microsoft Lync 2013 can be configured to automatically start each time a user starts Windows.</span></span> <span data-ttu-id="53953-159">Из-за этого у вас может быть большое количество пользователей, которые автоматически подключаются к Lync при каждом входе в Windows каждый день, но в этом случае никогда не используете Lync Server в течение этого периода времени.</span><span class="sxs-lookup"><span data-stu-id="53953-159">Because of that, you might have a large number of users who automatically log on to Lync when they log on to Windows each day, but then never actually use Lync Server during that time period.</span></span>

<span data-ttu-id="53953-160">Метрика Unique Active Users также предоставляет более осмысленные данные в Организации, где пользователи обычно не завершают работу Windows в конце дня.</span><span class="sxs-lookup"><span data-stu-id="53953-160">The Unique active users metric also provides more meaningful data in an organization where users typically do not log off Windows at the end of the day.</span></span> <span data-ttu-id="53953-161">Вместо этого они просто блокируют свои компьютеры и не работают с Windows и Lync.</span><span class="sxs-lookup"><span data-stu-id="53953-161">Instead, they simply lock their computers and leave Windows and Lync running.</span></span> <span data-ttu-id="53953-162">В подобной ситуации каждый день может происходить всего несколько входов в систему, так как пользователи зарегистрировались несколько дней назад и с тех пор не выходили из системы.</span><span class="sxs-lookup"><span data-stu-id="53953-162">In a situation like that, you might end up with very few logons per day because your users logged on several days ago and never logged off.</span></span> <span data-ttu-id="53953-163">Однако уникальные активные пользователи сообщают, активно ли пользователи с помощью Lync или другого клиента Lync Server.</span><span class="sxs-lookup"><span data-stu-id="53953-163">However, Unique active users tells you whether users are actively using Lync or another Lync Server client.</span></span>

</div>

<div>

## <a name="filters"></a><span data-ttu-id="53953-164">Фильтры</span><span class="sxs-lookup"><span data-stu-id="53953-164">Filters</span></span>

<span data-ttu-id="53953-165">Фильтры позволяют получить более конкретные наборы возвращаемых данных.</span><span class="sxs-lookup"><span data-stu-id="53953-165">Filters provide a way for you to return a more finely targeted set of data or to view the returned data in different ways.</span></span> <span data-ttu-id="53953-166">Например, отчет о регистрации пользователей позволяет просматривать данные для всех пулов регистраторов и пограничных серверов, а также просматривать данные для отдельного пула.</span><span class="sxs-lookup"><span data-stu-id="53953-166">For example, the User Registration Report enables you to view data for all your Registrar pool and Edge Servers or to view data for an individual pool.</span></span> <span data-ttu-id="53953-167">Можно также выбрать порядок группирования данных.</span><span class="sxs-lookup"><span data-stu-id="53953-167">You can also choose how data should be grouped.</span></span> <span data-ttu-id="53953-168">В этом случае регистрации группируются по времени, дням, неделям или месяцам.</span><span class="sxs-lookup"><span data-stu-id="53953-168">In this case, registrations grouped by hour, day, week, or month.</span></span>

<span data-ttu-id="53953-169">В следующей таблице приведены фильтры, которые можно использовать с отчетом о регистрации пользователей.</span><span class="sxs-lookup"><span data-stu-id="53953-169">The following table lists the filters that you can use with the User Registration Report.</span></span>

### <a name="user-registration-report-filters"></a><span data-ttu-id="53953-170">Фильтры отчета о регистрации пользователей</span><span class="sxs-lookup"><span data-stu-id="53953-170">User Registration Report Filters</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53953-171">Имя</span><span class="sxs-lookup"><span data-stu-id="53953-171">Name</span></span></th>
<th><span data-ttu-id="53953-172">Описание</span><span class="sxs-lookup"><span data-stu-id="53953-172">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53953-173"><strong>From</strong></span><span class="sxs-lookup"><span data-stu-id="53953-173"><strong>From</strong></span></span></p></td>
<td><p><span data-ttu-id="53953-p113">Начальные дата и время временного диапазона. Чтобы просмотреть данные по часам, введите начальные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="53953-p113">Start date and time for the time range. To view data by hours, enter both the start date and time as follows:</span></span></p>
<p><span data-ttu-id="53953-176">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="53953-176">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="53953-p114">Если не указать время начала, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="53953-p114">If you do not enter a start time, the report automatically begins at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="53953-179">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="53953-179">7/7/2012</span></span></p>
<p><span data-ttu-id="53953-180">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="53953-180">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="53953-181">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="53953-181">7/3/2012</span></span></p>
<p><span data-ttu-id="53953-182">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="53953-182">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53953-183"><strong>To</strong></span><span class="sxs-lookup"><span data-stu-id="53953-183"><strong>To</strong></span></span></p></td>
<td><p><span data-ttu-id="53953-p115">Конечные дата и время временного диапазона. Чтобы просмотреть данные по часам, введите конечные дату и время следующим образом:</span><span class="sxs-lookup"><span data-stu-id="53953-p115">End date and time for the time range. To view data by hours, enter both the end date and time as follows:</span></span></p>
<p><span data-ttu-id="53953-186">7/7/2012 13:00.</span><span class="sxs-lookup"><span data-stu-id="53953-186">7/7/2012 1:00 PM</span></span></p>
<p><span data-ttu-id="53953-p116">Если не указать время окончания, автоматически будет выбрано время 00:00 указанного дня. Чтобы просмотреть данные по дням, просто введите дату:</span><span class="sxs-lookup"><span data-stu-id="53953-p116">If you do not enter an end time, the report automatically ends at 12:00 AM on the specified day. To view data by day, enter just the date:</span></span></p>
<p><span data-ttu-id="53953-189">7/7/2012</span><span class="sxs-lookup"><span data-stu-id="53953-189">7/7/2012</span></span></p>
<p><span data-ttu-id="53953-190">Для просмотра по неделям или по месяцам введите дату, выпадающую на любой день недели или месяца, который вы хотите просмотреть (это необязательно должен быть первый день недели или месяца):</span><span class="sxs-lookup"><span data-stu-id="53953-190">To view by week or by month, enter a date that falls anywhere within the week or month that you want to view (you do not have to enter the first day of the week or month):</span></span></p>
<p><span data-ttu-id="53953-191">7/3/2012</span><span class="sxs-lookup"><span data-stu-id="53953-191">7/3/2012</span></span></p>
<p><span data-ttu-id="53953-192">Неделя всегда начинается с воскресения и заканчивается субботой.</span><span class="sxs-lookup"><span data-stu-id="53953-192">Weeks always run from Sunday through Saturday.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53953-193"><strong>Interval</strong></span><span class="sxs-lookup"><span data-stu-id="53953-193"><strong>Interval</strong></span></span></p></td>
<td><p><span data-ttu-id="53953-p117">Временной интервал. Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="53953-p117">Time interval. Select one of the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="53953-196">Ежечасно (может отображаться до 25 часов)</span><span class="sxs-lookup"><span data-stu-id="53953-196">Hourly (a maximum of 25 hours can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="53953-197">Ежедневно (может отображаться до 31 дня)</span><span class="sxs-lookup"><span data-stu-id="53953-197">Daily (a maximum of 31 days can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="53953-198">Еженедельно (может отображаться до 12 недель)</span><span class="sxs-lookup"><span data-stu-id="53953-198">Weekly (a maximum of 12 weeks can be displayed)</span></span></p></li>
<li><p><span data-ttu-id="53953-199">Ежемесячно (может отображаться до 12 месяцев)</span><span class="sxs-lookup"><span data-stu-id="53953-199">Monthly (a maximum of 12 months can be displayed)</span></span></p></li>
</ul>
<p><span data-ttu-id="53953-p118">Если даты начала и окончания превышают максимальное допустимые значения для выбранного интервала, отображается только максимальное число значений (от даты начала). Например, если выбран интервал "Ежедневно" с датой начала 07.07.2012 и датой окончания 28.02.2012, данные отображаются с 12:00 07.08.2012 до 12:00 07.09.2012 (то есть в общей сложности отображаются данные для 31 дня).</span><span class="sxs-lookup"><span data-stu-id="53953-p118">If the start and end dates exceed the maximum number of values allowed for the selected interval, only the maximum number of values (starting from the start date) are displayed. For example, if you select the Daily interval with a start date of 7/7/2012 and an end date of 2/28/2012, data is displayed for the days 8/7/2012 12:00 AM to 9/7/2012 12:00 AM (that is, a total of 31 days' worth of data).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53953-202"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="53953-202"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="53953-203">Полное доменное имя пула регистратора или пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="53953-203">Fully qualified domain name (FQDN) of the Registrar pool or Edge Server.</span></span> <span data-ttu-id="53953-204">Можно выбрать отдельный пул или выбрать <strong>[Все]</strong>, чтобы просмотреть данные для всех пулов.</span><span class="sxs-lookup"><span data-stu-id="53953-204">You can either select an individual pool or choose <strong>[All]</strong> to view data for all the pools.</span></span> <span data-ttu-id="53953-205">Данный раскрывающийся список заполняется автоматически на основе записей, имеющихся в базе данных.</span><span class="sxs-lookup"><span data-stu-id="53953-205">This drop-down list is automatically populated for you based on the records in the database.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a><span data-ttu-id="53953-206">Метрики</span><span class="sxs-lookup"><span data-stu-id="53953-206">Metrics</span></span>

<span data-ttu-id="53953-207">В следующей таблице представлены сведения, приведенные в отчете о регистрации пользователей.</span><span class="sxs-lookup"><span data-stu-id="53953-207">The following table lists the information provided in the User Registration Report.</span></span>

### <a name="user-registration-report-metrics"></a><span data-ttu-id="53953-208">Показатели отчета о регистрации пользователей</span><span class="sxs-lookup"><span data-stu-id="53953-208">User Registration Report Metrics</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53953-209">Имя</span><span class="sxs-lookup"><span data-stu-id="53953-209">Name</span></span></th>
<th><span data-ttu-id="53953-210">Возможность сортировки по этому показателю</span><span class="sxs-lookup"><span data-stu-id="53953-210">Can you sort on this item?</span></span></th>
<th><span data-ttu-id="53953-211">Описание</span><span class="sxs-lookup"><span data-stu-id="53953-211">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53953-212"><strong>Каждый час</strong></span><span class="sxs-lookup"><span data-stu-id="53953-212"><strong>Hourly</strong></span></span></p>
<p><span data-ttu-id="53953-213"><strong>Ежедневное</strong></span><span class="sxs-lookup"><span data-stu-id="53953-213"><strong>Daily</strong></span></span></p>
<p><span data-ttu-id="53953-214"><strong>Еженедельное</strong></span><span class="sxs-lookup"><span data-stu-id="53953-214"><strong>Weekly</strong></span></span></p>
<p><span data-ttu-id="53953-215"><strong>Monthly</strong></span><span class="sxs-lookup"><span data-stu-id="53953-215"><strong>Monthly</strong></span></span></p></td>
<td><p><span data-ttu-id="53953-216">Нет</span><span class="sxs-lookup"><span data-stu-id="53953-216">No</span></span></p></td>
<td><p><span data-ttu-id="53953-p120">Указывает выбранный на панели инструментов фильтров интервал времени. Если это возможно, вы можете щелкнуть заданный интервала для просмотра подробных сведений для этого интервала. Например, если вы используете интервал "Ежедневно" и выбираете 07.07.2012, вы увидите почасовую детализацию активности регистрации пользователей для этой даты.</span><span class="sxs-lookup"><span data-stu-id="53953-p120">Indicates the time interval that you selected on the filter toolbar. Where applicable, you can click a given time interval to view detailed information for that interval. For example, if you are using the Daily interval and you click 7/7/2012, you see an hourly breakdown of user registration activity for that date.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53953-220"><strong>Общее количество входов</strong></span><span class="sxs-lookup"><span data-stu-id="53953-220"><strong>Total logons</strong></span></span></p></td>
<td><p><span data-ttu-id="53953-221">Нет</span><span class="sxs-lookup"><span data-stu-id="53953-221">No</span></span></p></td>
<td><p><span data-ttu-id="53953-222">Общее количество успешных сеансов входа.</span><span class="sxs-lookup"><span data-stu-id="53953-222">Total number of successful logon sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53953-223"><strong>Количество внутренних входов</strong></span><span class="sxs-lookup"><span data-stu-id="53953-223"><strong>Internal logons</strong></span></span></p></td>
<td><p><span data-ttu-id="53953-224">Нет</span><span class="sxs-lookup"><span data-stu-id="53953-224">No</span></span></p></td>
<td><p><span data-ttu-id="53953-225">Общее количество входов в систему в пределах внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="53953-225">Total number of logons within the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53953-226"><strong>Количество внешних входов</strong></span><span class="sxs-lookup"><span data-stu-id="53953-226"><strong>External logons</strong></span></span></p></td>
<td><p><span data-ttu-id="53953-227">Нет</span><span class="sxs-lookup"><span data-stu-id="53953-227">No</span></span></p></td>
<td><p><span data-ttu-id="53953-228">Общее количество входов в систему из внешних сетей с использованием пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="53953-228">Total number of logons from outside the internal network, using the Edge Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53953-229"><strong>Количество уникальных входов пользователей</strong></span><span class="sxs-lookup"><span data-stu-id="53953-229"><strong>Unique logon users</strong></span></span></p></td>
<td><p><span data-ttu-id="53953-230">Нет</span><span class="sxs-lookup"><span data-stu-id="53953-230">No</span></span></p></td>
<td><p><span data-ttu-id="53953-p121">Общее количество пользователей хотя бы с одним сеансом входа. Пользователь с несколькими сеансами входа считается как один пользователь, так же, как и пользователь с одним сеансом входа.</span><span class="sxs-lookup"><span data-stu-id="53953-p121">Total number of users who had at least one logon session. A user who had multiple logon sessions counts as one user, the same as a person who had just a single logon session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53953-233"><strong>Количество активных пользователей</strong></span><span class="sxs-lookup"><span data-stu-id="53953-233"><strong>Unique active users</strong></span></span></p></td>
<td><p><span data-ttu-id="53953-234">Нет</span><span class="sxs-lookup"><span data-stu-id="53953-234">No</span></span></p></td>
<td><p><span data-ttu-id="53953-p122">Общее количество пользователей, участвующих в одноранговом сеансе или сеансе конференции. Пользователь с несколькими сеансами считается как один пользователь, так же, как и пользователь с одним сеансом входа.</span><span class="sxs-lookup"><span data-stu-id="53953-p122">Total number of users who were involved in a peer-to-peer or conferencing session. A user who had multiple sessions counts as one user, the same as a person who had just a single session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

