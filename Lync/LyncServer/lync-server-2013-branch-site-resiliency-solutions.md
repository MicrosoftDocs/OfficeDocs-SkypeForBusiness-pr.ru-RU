---
title: 'Lync Server 2013: решения устойчивости для сайтов филиалов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a72d07e1ccdae6c433de92057e6e9414fff20153
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="0c834-102">Решения для обеспечения устойчивости сайтов филиалов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c834-102">Branch-site resiliency solutions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c834-103">_**Последнее изменение темы:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="0c834-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="0c834-104">Существуют очевидные преимущества обеспечения устойчивости сайта филиала в Организации.</span><span class="sxs-lookup"><span data-stu-id="0c834-104">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="0c834-105">В частности, если вы потеряете подключение к центральному сайту, пользователи сайта филиала будут иметь корпоративную голосовую службу и голосовую почту (при настройке параметров перенаправления голосовой почты; Дополнительные сведения см. в статье [требования к устойчивости сайтов филиалов для Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span><span class="sxs-lookup"><span data-stu-id="0c834-105">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="0c834-106">Тем не менее, для сайтов с менее 25 пользователями решение устойчивости может не обеспечивать достаточных рентабельности инвестиций.</span><span class="sxs-lookup"><span data-stu-id="0c834-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="0c834-p102">Доступно три варианта обеспечения устойчивости сайта филиала. Воспользуйтесь следующей таблицей, чтобы определить оптимальный для себя вариант.</span><span class="sxs-lookup"><span data-stu-id="0c834-p102">If you decide to provide branch-site resiliency, you have three options. The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c834-109">Если вы...</span><span class="sxs-lookup"><span data-stu-id="0c834-109">If you…</span></span></th>
<th><span data-ttu-id="0c834-110">Мы рекомендуем использовать…</span><span class="sxs-lookup"><span data-stu-id="0c834-110">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c834-111">На узле размещается от 25 до 1000 пользователей и рентабельность инвестиций не позволяет провести полную развертку или не доступна локальная административная поддержка</span><span class="sxs-lookup"><span data-stu-id="0c834-111">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="0c834-112">Устройство для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="0c834-112">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="0c834-113">Устройство для обеспечения связи в филиалах является отраслевым стандартным сервером с регистратором Lync Server и сервером-посредником под управлением Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="0c834-113">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="0c834-114">Устройство для обеспечения связи в филиалах также содержит шлюз телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="0c834-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="0c834-115">Сторонние устройства (разработанные партнерами Microsoft по программе сертификации SBA) обеспечивают непрерывное ТСОП-подключение в случае сбоя глобальной сети, но не обеспечивают устойчивость сети и функции конференц-связи, так как эти функции зависят от серверов переднего плана на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="0c834-115">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="0c834-116">Подробные сведения о устройствах для обеспечения связи в &quot;филиалах можно найти в статье&quot; сведения об устройстве для обеспечения связи в филиалах, далее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="0c834-116">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="0c834-117"><strong>Примечание:</strong> Если вы решили также использовать магистральную линию SIP с устройством для обеспечения связи в филиалах, обратитесь к поставщику устройства для обеспечения связи в филиалах, чтобы узнать, какой поставщик услуг лучше всего подходит для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0c834-117"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c834-118">Размещение между пользователями 1000 и 2000 на сайте филиала, отсутствие отказоустойчивого подключения к глобальной сети и обучение доступных администраторов Lync Server</span><span class="sxs-lookup"><span data-stu-id="0c834-118">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="0c834-119">Сервер для обеспечения связи в филиалах или два устройства для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="0c834-119">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="0c834-120">Сервер для обеспечения связи в филиалах — это Windows Server, на котором указаны определенные требования к оборудованию, на которых установлено программное обеспечение сервера-посредника и сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="0c834-120">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="0c834-121">Он должен подключаться через ТСОП-шлюз или SIP-магистраль к телефонному оператору.</span><span class="sxs-lookup"><span data-stu-id="0c834-121">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="0c834-122">Подробнее о серверах для обеспечения связи в филиалах &quot;можно узнать в статье сведения о&quot; сервере для обеспечения связи в филиалах, приведенном далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="0c834-122">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c834-123">Если вам требуются функции для присутствия и конференц-связи в дополнение к функциям голосовой связи для пользователей 5000 и прошли обучение администраторам Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0c834-123">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="0c834-124">Выполняете развертывание в качестве центрального сайта с сервером Standard Edition, а не как сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="0c834-124">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="0c834-125">Развертывание Lync Server с полным масштабированием обеспечивает непрерывное подключение и устойчивое присутствие и конференц-связь в случае сбоя глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="0c834-125">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="0c834-126">Сведения о подготовке этого решения приведены в статье <a href="lync-server-2013-planning-for-your-organization.md">планирование организации для Lync server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Определение требований к системе для Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Определение требований к инфраструктуре для Lync Server 2013</a>и другие важные разделы документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="0c834-126">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="0c834-127">Топология для обеспечения устойчивости</span><span class="sxs-lookup"><span data-stu-id="0c834-127">Resiliency Topologies</span></span>

<span data-ttu-id="0c834-128">На следующем изображении показаны рекомендуемые топологии для обеспечения устойчивости сайтов филиалов.</span><span class="sxs-lookup"><span data-stu-id="0c834-128">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="0c834-129">**Варианты обеспечения устойчивости сайта филиала**</span><span class="sxs-lookup"><span data-stu-id="0c834-129">**Branch site resiliency options**</span></span>

<span data-ttu-id="0c834-130">![Параметры устойчивости для голосовой ветви](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Параметры устойчивости для голосовой ветви")</span><span class="sxs-lookup"><span data-stu-id="0c834-130">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="0c834-131">Описание механизма обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="0c834-131">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="0c834-132">Устройство для обеспечения связи в филиалах Lync Server включает в себя следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="0c834-132">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="0c834-133">Регистратор для проверки подлинности пользователей, регистрации и маршрутизации вызовов</span><span class="sxs-lookup"><span data-stu-id="0c834-133">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="0c834-134">Сервер-посредник для обработки сигналов между регистратором и ТСОП-шлюзом</span><span class="sxs-lookup"><span data-stu-id="0c834-134">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="0c834-135">ТСОП-шлюз для маршрутизации вызовов в ТСОП в случае отказа глобальной сети</span><span class="sxs-lookup"><span data-stu-id="0c834-135">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="0c834-136">SQL Server Express для локального хранения пользовательских данных</span><span class="sxs-lookup"><span data-stu-id="0c834-136">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="0c834-137">Устройство для обеспечения связи в филиалах также включает магистральные линии связи PSTN, аналоговые порты и Ethernet.</span><span class="sxs-lookup"><span data-stu-id="0c834-137">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="0c834-138">Если подключение WAN сайта филиала к центральному сайту становится недоступным, пользователи внутренней ветви продолжают регистрироваться с помощью регистратора устройства для обеспечения связи в филиалах и получают непрерванную службу голосовой связи с помощью соединения с устройством для обеспечения связи в филиалах в PSTN.</span><span class="sxs-lookup"><span data-stu-id="0c834-138">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="0c834-139">Пользователи сайта филиала, подключающиеся из дома и из других удаленных расположений смогут зарегистрироваться в регистраторе центрального сайта в случае  отсутствия подключения к сайту филиала посредством глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="0c834-139">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="0c834-140">Эти пользователи имеют доступ ко всем возможностям единой системы обмена данными за одним исключением — входящие вызовы на сайт филиала будут переадресовываться на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="0c834-140">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="0c834-141">После восстановления подключения по глобальной сети пользователям сайта будут снова предоставлены все функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="0c834-141">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="0c834-142">Отработка отказа для устройства для обеспечения связи в филиалах и для восстановления службы требует наличия ИТ ИТ.</span><span class="sxs-lookup"><span data-stu-id="0c834-142">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="0c834-143">Lync Server поддерживает до двух устройств для обеспечения связи в филиалах на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="0c834-143">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="0c834-144">Пользователи, размещенные на устройстве для обеспечения связи в филиалах Lync Server, не могут создавать новые комнаты чата или просматривать карточку комнаты для существующих комнат.</span><span class="sxs-lookup"><span data-stu-id="0c834-144">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="0c834-145">Обзор развертывания механизма обеспечения связи филиала</span><span class="sxs-lookup"><span data-stu-id="0c834-145">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="0c834-146">Устройство для обеспечения связи в филиалах предназначено для производителей вычислительной техники в связи с корпорацией Майкрософт и развернуто от их имени розничными поставщиками услуг.</span><span class="sxs-lookup"><span data-stu-id="0c834-146">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="0c834-147">Это развертывание должно выполняться только после развертывания Lync Server на центральном сайте, подключения глобальной сети к сайту филиала, а для пользователей сайта филиала включена поддержка корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0c834-147">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="0c834-148">Подробнее об этих этапах можно узнать в статье Deployment The Deployment [Appliance or Server with Lync server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="0c834-148">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c834-149">Этап</span><span class="sxs-lookup"><span data-stu-id="0c834-149">Phase</span></span></th>
<th><span data-ttu-id="0c834-150">Шаги</span><span class="sxs-lookup"><span data-stu-id="0c834-150">Steps</span></span></th>
<th><span data-ttu-id="0c834-151">Права пользователей</span><span class="sxs-lookup"><span data-stu-id="0c834-151">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c834-152">Настройка доменных служб Active Directory для устройства для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="0c834-152">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="0c834-153"><strong>На центральном сайте:</strong></span><span class="sxs-lookup"><span data-stu-id="0c834-153"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="0c834-154">Создайте учетную запись пользователя домена (или корпоративный идентификатор) для специалиста, который будет устанавливать и активировать устройство для обеспечения связи в филиалах на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="0c834-154">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="0c834-155">Создайте учетную запись компьютера (с соответствующим полным доменным именем) для устройства для обеспечения связи в филиалах в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0c834-155">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="0c834-156">В построителе топологий создайте и опубликуйте устройство для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="0c834-156">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="0c834-157">Учетная запись технического специалиста должна принадлежать к группе RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="0c834-157">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="0c834-158">Устройство для обеспечения связи в филиалах должно принадлежать к группе Ртксбауниверсалсервицес, что происходит автоматически при использовании построителя топологий.</span><span class="sxs-lookup"><span data-stu-id="0c834-158">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c834-159">Установите и активируйте устройство для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="0c834-159">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="0c834-160"><strong>На сайте филиала:</strong></span><span class="sxs-lookup"><span data-stu-id="0c834-160"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="0c834-161">Подключите устройство для обеспечения связи в филиалах к порту Ethernet и PSTN.</span><span class="sxs-lookup"><span data-stu-id="0c834-161">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="0c834-162">Запустите устройство для обеспечения связи в филиалах.</span><span class="sxs-lookup"><span data-stu-id="0c834-162">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="0c834-163">Присоедините устройство для обеспечения связи в филиалах к домену, используя учетную запись пользователя домена, созданную для устройства для обеспечения связи в филиале на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="0c834-163">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="0c834-164">Укажите полное доменное имя и IP-адрес, совпадающие с полным доменным именем, созданным в учетной записи компьютера.</span><span class="sxs-lookup"><span data-stu-id="0c834-164">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="0c834-165">Настройка устройства для обеспечения связи в филиалах с помощью пользовательского интерфейса ПВТ.</span><span class="sxs-lookup"><span data-stu-id="0c834-165">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="0c834-166">Проверьте подключение к ТСОП.</span><span class="sxs-lookup"><span data-stu-id="0c834-166">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="0c834-167">Учетная запись технического специалиста должна принадлежать к группе RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="0c834-167">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="0c834-168">Описание сервера обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="0c834-168">Survivable Branch Server Details</span></span>

<span data-ttu-id="0c834-169">В построителе топологий создайте сайт филиала, добавьте к нему сервер для обеспечения связи в филиалах, а затем запустите мастер развертывания Lync Server на компьютере, на котором необходимо установить роль.</span><span class="sxs-lookup"><span data-stu-id="0c834-169">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="0c834-170">См. также</span><span class="sxs-lookup"><span data-stu-id="0c834-170">See Also</span></span>


[<span data-ttu-id="0c834-171">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0c834-171">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

