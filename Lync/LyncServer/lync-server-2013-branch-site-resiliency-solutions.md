---
title: 'Lync Server 2013: решения устойчивости для сайтов филиалов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Branch-site resiliency solutions
ms:assetid: 1700f99b-709c-4e47-88eb-c0a5490e26e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398234(v=OCS.15)
ms:contentKeyID: 48183517
ms.date: 12/11/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce14328aed7ae4769d2f2aff18edb9c6135fe025
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841745"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="branch-site-resiliency-solutions-in-lync-server-2013"></a><span data-ttu-id="bc61b-102">Решения устойчивости для сайтов филиалов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc61b-102">Branch-site resiliency solutions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc61b-103">_**Тема последнего изменения:** 2014-12-10_</span><span class="sxs-lookup"><span data-stu-id="bc61b-103">_**Topic Last Modified:** 2014-12-10_</span></span>

<span data-ttu-id="bc61b-104">There are obvious advantages to providing branch-site resiliency to your organization.</span><span class="sxs-lookup"><span data-stu-id="bc61b-104">There are obvious advantages to providing branch-site resiliency to your organization.</span></span> <span data-ttu-id="bc61b-105">В частности, если вы потеряли подключение к центральному сайту, пользователи сайтов филиалов будут иметь услуги голосовой связи и голосовую почту (если вы настроили параметры перенаправления голосовой почты; Дополнительные сведения см. в разделе [требования к устойчивости сайтов филиалов для Lync Server) 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span><span class="sxs-lookup"><span data-stu-id="bc61b-105">Specifically, if you lose the connection to the central site, branch site users will continue to have Enterprise Voice service and voice mail (if you configure voice mail rerouting settings; for details, see [Branch-site resiliency requirements for Lync Server 2013](lync-server-2013-branch-site-resiliency-requirements.md)).</span></span> <span data-ttu-id="bc61b-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span><span class="sxs-lookup"><span data-stu-id="bc61b-106">However, for sites with fewer than 25 users, a resiliency solution may not provide a sufficient return on investment.</span></span>

<span data-ttu-id="bc61b-p102">Доступно три варианта обеспечения устойчивости сайта филиала. Воспользуйтесь следующей таблицей, чтобы определить оптимальный для себя вариант.</span><span class="sxs-lookup"><span data-stu-id="bc61b-p102">If you decide to provide branch-site resiliency, you have three options. The following table can help you determine the best option for your organization.</span></span>

<div>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc61b-109">Если вы...</span><span class="sxs-lookup"><span data-stu-id="bc61b-109">If you…</span></span></th>
<th><span data-ttu-id="bc61b-110">Мы рекомендуем использовать…</span><span class="sxs-lookup"><span data-stu-id="bc61b-110">We recommend that you use a…</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc61b-111">На узле размещается от 25 до 1000 пользователей и рентабельность инвестиций не позволяет провести полную развертку или не доступна локальная административная поддержка</span><span class="sxs-lookup"><span data-stu-id="bc61b-111">Host between 25 and 1000 users at your branch site, and if the return on investment does not support a full deployment or where local administrative support is unavailable</span></span></p></td>
<td><p><span data-ttu-id="bc61b-112">для обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="bc61b-112">Survivable Branch Appliance</span></span></p>
<p><span data-ttu-id="bc61b-113">Бесперебойно работающее устройство ветвления — это стандартный блейд-сервер с сервером регистратора Lync Server и сервер-посредника под управлением Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="bc61b-113">The Survivable Branch Appliance is an industry-standard blade server with a Lync Server Registrar and Mediation Server running on Windows Server 2008 R2.</span></span> <span data-ttu-id="bc61b-114">Бесперебойно работающее устройство филиала также включает коммутируемый коммутируемой телефонной сети (PSTN).</span><span class="sxs-lookup"><span data-stu-id="bc61b-114">The Survivable Branch Appliance also contains a public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="bc61b-115">Сторонние устройства (разработанные партнерами Microsoft по программе сертификации SBA) обеспечивают непрерывное ТСОП-подключение в случае сбоя глобальной сети, но не обеспечивают устойчивость сети и функции конференц-связи, так как эти функции зависят от серверов переднего плана на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="bc61b-115">Qualified third-party devices (developed by Microsoft partners in the Survivable Branch Appliance (SBA) qualification/certification program) provide a continuous PSTN connection in the event of WAN failure, but this approach does not provide resilient presence and conferencing because these features depend on Front End Servers at the central site.</span></span></p>
<p><span data-ttu-id="bc61b-116">Подробные сведения о бесперебойных устройствах филиалов можно &quot;найти в разделе сведения о бесперебойной управляющем устройстве филиалов,&quot; которые описаны далее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="bc61b-116">For details about Survivable Branch Appliances, see &quot;Survivable Branch Appliance Details,&quot; later in this topic.</span></span></p>
<p><span data-ttu-id="bc61b-117"><strong>Примечание.</strong> Если вы решили также использовать магистральную сеть SIP с бесперебойно используемым устройством филиала, обратитесь к своему поставщику управляющего устройства филиала, чтобы узнать, какой поставщик услуг лучше подходит для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bc61b-117"><strong>Note:</strong> If you decide to also use a SIP trunk with your Survivable Branch Appliance, contact your Survivable Branch Appliance vendor to learn about which service provider is best for your organization.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc61b-118">Размещение между пользователями 1000 и 2000 на сайте филиала, отсутствие отказоустойчивого подключения к глобальной сети и обучение администраторов сервера Lync Server</span><span class="sxs-lookup"><span data-stu-id="bc61b-118">Host between 1000 and 2000 users at your branch site, lack a resilient WAN connection, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="bc61b-119">Бесперебойный сервер филиалов или два бесперебойно работающего устройства филиалов.</span><span class="sxs-lookup"><span data-stu-id="bc61b-119">Survivable Branch Server or two Survivable Branch Appliances.</span></span></p>
<p><span data-ttu-id="bc61b-120">Бесперебойный сервер филиалов — это компьютер, на котором указаны требования к оборудованию на сервере Windows Server, на котором установлено программное обеспечение сервера регистратора Lync Server и сервер-посредника.</span><span class="sxs-lookup"><span data-stu-id="bc61b-120">The Survivable Branch Server is a Windows Server meeting specified hardware requirements that has Lync Server Registrar and Mediation Server software installed on it.</span></span> <span data-ttu-id="bc61b-121">Он должен подключаться через ТСОП-шлюз или SIP-магистраль к телефонному оператору.</span><span class="sxs-lookup"><span data-stu-id="bc61b-121">It must connect to either a PSTN gateway or a SIP trunk to a telephone service provider.</span></span></p>
<p><span data-ttu-id="bc61b-122">Сведения о бесперебойных серверах филиалов можно найти &quot;в разделе сведения о бесперебойной&quot; подсети, приведенные ниже.</span><span class="sxs-lookup"><span data-stu-id="bc61b-122">For details about Survivable Branch Servers, see &quot;Survivable Branch Server Details,&quot; later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc61b-123">Если вам нужны возможности присутствия и конференции в дополнение к функциям голосовой связи для пользователей 5000 и прошли обучение администраторов сервера Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bc61b-123">If you require presence and conferencing features in addition to voice features for up to 5000 users, and have trained Lync Server administrators available</span></span></p></td>
<td><p><span data-ttu-id="bc61b-124">Выполняете развертывание в качестве центрального сайта с сервером Standard Edition, а не как сайта филиала.</span><span class="sxs-lookup"><span data-stu-id="bc61b-124">Deploy as a central site with a Standard Edition server rather than as a branch site.</span></span></p>
<p><span data-ttu-id="bc61b-125">Развертывание в масштабе Lync Server обеспечивает непрерывное соединение и устойчивое присутствие и конференции в случае сбоя глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="bc61b-125">A full-scale Lync Server deployment provides a continuous PSTN connection and resilient presence and conferencing in the event of WAN failure.</span></span></p>
<p><span data-ttu-id="bc61b-126">Подробнее о том, как подготавливать это решение, можно найти в разделе <a href="lync-server-2013-planning-for-your-organization.md">планирование организации для Lync server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Определение требований к системе для Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Определение требований инфраструктуры для Lync Server 2013</a>и другие важные разделы документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="bc61b-126">For details about preparing for this solution, see <a href="lync-server-2013-planning-for-your-organization.md">Organization planning for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-system-requirements.md">Determining your system requirements for Lync Server 2013</a>, <a href="lync-server-2013-determining-your-infrastructure-requirements.md">Determining your infrastructure requirements for Lync Server 2013</a>, and other relevant sections of the Planning documentation.</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="resiliency-topologies"></a><span data-ttu-id="bc61b-127">Топология для обеспечения устойчивости</span><span class="sxs-lookup"><span data-stu-id="bc61b-127">Resiliency Topologies</span></span>

<span data-ttu-id="bc61b-128">На следующем изображении показаны рекомендуемые топологии для обеспечения устойчивости сайтов филиалов.</span><span class="sxs-lookup"><span data-stu-id="bc61b-128">The following figure shows the recommended topologies for branch-site resiliency.</span></span>

<span data-ttu-id="bc61b-129">**Варианты обеспечения устойчивости сайта филиала**</span><span class="sxs-lookup"><span data-stu-id="bc61b-129">**Branch site resiliency options**</span></span>

<span data-ttu-id="bc61b-130">![Параметры устойчивости для голосовой ветви] (images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Параметры устойчивости для голосовой ветви")</span><span class="sxs-lookup"><span data-stu-id="bc61b-130">![Voice Branch Resiliency Options](images/Gg398234.47eecd19-08ae-4d82-acbe-61f0de760306(OCS.15).jpg "Voice Branch Resiliency Options")</span></span>

</div>

<div>

## <a name="survivable-branch-appliance-details"></a><span data-ttu-id="bc61b-131">Описание механизма обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="bc61b-131">Survivable Branch Appliance Details</span></span>

<span data-ttu-id="bc61b-132">Бесперебойно работающее устройство филиалов Lync Server включает следующие компоненты:</span><span class="sxs-lookup"><span data-stu-id="bc61b-132">The Lync Server Survivable Branch Appliance includes the following components:</span></span>

  - <span data-ttu-id="bc61b-133">Регистратор для проверки подлинности пользователей, регистрации и маршрутизации вызовов</span><span class="sxs-lookup"><span data-stu-id="bc61b-133">A Registrar for user authentication, registration and call routing</span></span>

  - <span data-ttu-id="bc61b-134">Сервер-посредник для обработки сигналов между регистратором и ТСОП-шлюзом</span><span class="sxs-lookup"><span data-stu-id="bc61b-134">A Mediation Server for handling signaling between the Registrar and a PSTN gateway</span></span>

  - <span data-ttu-id="bc61b-135">ТСОП-шлюз для маршрутизации вызовов в ТСОП в случае отказа глобальной сети</span><span class="sxs-lookup"><span data-stu-id="bc61b-135">A PSTN gateway for routing calls to the PSTN as a fallback transport in the event of a WAN outage</span></span>

  - <span data-ttu-id="bc61b-136">SQL Server Express для локального хранения пользовательских данных</span><span class="sxs-lookup"><span data-stu-id="bc61b-136">SQL Server Express for local user data storage</span></span>

<span data-ttu-id="bc61b-137">Бесперебойно работающее устройство филиала также включает в себя КОММУТИРУЕМые магистрали, аналоговые порты и адаптер Ethernet.</span><span class="sxs-lookup"><span data-stu-id="bc61b-137">The Survivable Branch Appliance also includes PSTN trunks, analog ports, and an Ethernet adapter.</span></span>

<span data-ttu-id="bc61b-138">Если соединение WAN сайтов филиалов с центральным сайтом становится недоступным, пользователи внутренней ветви по-прежнему будут регистрироваться с помощью работающего регистратора и получать услуги голосовой связи, используя бесперебойное соединение с управляющим устройством филиала. в КТСОП.</span><span class="sxs-lookup"><span data-stu-id="bc61b-138">If the branch site’s WAN connection to a central site becomes unavailable, internal branch users continue to be registered with the Survivable Branch Appliance Registrar and obtain uninterrupted voice service by using the Survivable Branch Appliance connection to the PSTN.</span></span> <span data-ttu-id="bc61b-139">Пользователи сайта филиала, подключающиеся из дома и из других удаленных расположений, смогут зарегистрироваться в регистраторе центрального сайта в случае отсутствия подключения к сайту филиала посредством глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="bc61b-139">Branch site users who connect from home or other remote locations will be able to register with a Registrar server at a central site if the WAN link to the branch site is unavailable.</span></span> <span data-ttu-id="bc61b-140">Эти пользователи имеют доступ ко всем возможностям единой системы обмена данными за одним исключением — входящие вызовы на сайт филиала будут переадресовываться на голосовую почту.</span><span class="sxs-lookup"><span data-stu-id="bc61b-140">These users will have full unified communications functionality, with the one exception that inbound calls to the branch site will go to voice mail.</span></span> <span data-ttu-id="bc61b-141">После восстановления подключения по глобальной сети пользователям сайта будут снова предоставлены все функциональные возможности.</span><span class="sxs-lookup"><span data-stu-id="bc61b-141">When the WAN connection becomes available, full functionality should be restored to branch site users.</span></span> <span data-ttu-id="bc61b-142">Отработка отказа для бесперебойно работающего устройства филиала или восстановление службы требует наличия ИТ администратора.</span><span class="sxs-lookup"><span data-stu-id="bc61b-142">Neither the failover to the Survivable Branch Appliance nor the restoration of service requires the presence of an IT administrator.</span></span>

<span data-ttu-id="bc61b-143">Lync Server поддерживает до двух устройств с бесперебойной подразделением на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="bc61b-143">Lync Server supports up to two Survivable Branch Appliance at a branch site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bc61b-144">Пользователи, расположенные на устройстве с бесперебойной подразделением Lync Server, не могут создавать новые комнаты чата и просматривать открытку для существующих комнат.</span><span class="sxs-lookup"><span data-stu-id="bc61b-144">Users who are homed on a Lync Server Survivable Branch Appliance are unable to create new Chat Rooms or view the Room Card for existing rooms.</span></span>



</div>

<div>

## <a name="survivable-branch-appliance-deployment-overview"></a><span data-ttu-id="bc61b-145">Обзор развертывания механизма обеспечения связи филиала</span><span class="sxs-lookup"><span data-stu-id="bc61b-145">Survivable Branch Appliance Deployment Overview</span></span>

<span data-ttu-id="bc61b-146">Бесперебойно работающее устройство филиала изготовлено производителем оборудования в связи с корпорацией Майкрософт и развернутым от их имени в розничных магазинах.</span><span class="sxs-lookup"><span data-stu-id="bc61b-146">The Survivable Branch Appliance is manufactured by original equipment manufacturers in partnership with Microsoft and deployed on their behalf by value-added retailers.</span></span> <span data-ttu-id="bc61b-147">Это развертывание должно происходить только после развертывания Lync Server на центральном сайте, подключения к глобальной сети для сайта филиала, а также для пользователей сайтов филиалов, для которых разрешена Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="bc61b-147">This deployment should occur only after Lync Server has been deployed at the central site, a WAN connection to the branch site is in place, and branch site users are enabled for Enterprise Voice.</span></span>

<span data-ttu-id="bc61b-148">Подробнее об этих этапах можно узнать в разделе Развертывание работающего [устройства филиала или сервера с помощью Lync server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="bc61b-148">For details about these phases, see [Deploying a Survivable Branch Appliance or Server with Lync Server 2013](lync-server-2013-deploying-a-survivable-branch-appliance-or-server.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc61b-149">Этап</span><span class="sxs-lookup"><span data-stu-id="bc61b-149">Phase</span></span></th>
<th><span data-ttu-id="bc61b-150">Шаги</span><span class="sxs-lookup"><span data-stu-id="bc61b-150">Steps</span></span></th>
<th><span data-ttu-id="bc61b-151">Права пользователей</span><span class="sxs-lookup"><span data-stu-id="bc61b-151">User Rights</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc61b-152">Настройка доменных служб Active Directory для бесперебойно работающего устройства филиалов</span><span class="sxs-lookup"><span data-stu-id="bc61b-152">Set up Active Directory Domain Services for the Survivable Branch Appliance</span></span></p></td>
<td><p><span data-ttu-id="bc61b-153"><strong>На центральном сайте:</strong></span><span class="sxs-lookup"><span data-stu-id="bc61b-153"><strong>At the central site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="bc61b-154">Создайте учетную запись пользователя домена (или корпоративную идентификацию) для специалиста, который будет устанавливать и активировать бесперебойно работающее устройство филиала на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="bc61b-154">Create a domain user account (or enterprise identity) for the technician who will install and activate the Survivable Branch Appliance at the branch site.</span></span></p></li>
<li><p><span data-ttu-id="bc61b-155">Создайте учетную запись компьютера (с соответствующим полным доменным именем (FQDN)) для работающего устройства филиалов в доменных службах Active Directory.</span><span class="sxs-lookup"><span data-stu-id="bc61b-155">Create a computer account (with the applicable fully qualified domain name (FQDN)) for Survivable Branch Appliance in Active Directory Domain Services.</span></span></p></li>
<li><p><span data-ttu-id="bc61b-156">В построителе топологии Создавайте и публикуйте бесперебойно работающее устройство филиалов.</span><span class="sxs-lookup"><span data-stu-id="bc61b-156">In Topology Builder, create and publish the Survivable Branch Appliance.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="bc61b-157">Учетная запись технического специалиста должна принадлежать к группе RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="bc61b-157">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span> <span data-ttu-id="bc61b-158">Бесперебойно работающее устройство филиала должно входить в группу Ртксбауниверсалсервицес, что происходит автоматически при использовании Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="bc61b-158">The Survivable Branch Appliance must belong to the RTCSBAUniversalServices group, which happens automatically when you use Topology Builder.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc61b-159">Установка и активация бесперебойно работающего устройства филиалов.</span><span class="sxs-lookup"><span data-stu-id="bc61b-159">Install, and activate the Survivable Branch Appliance.</span></span></p></td>
<td><p><span data-ttu-id="bc61b-160"><strong>На сайте филиала:</strong></span><span class="sxs-lookup"><span data-stu-id="bc61b-160"><strong>At the branch site:</strong></span></span></p>
<ol>
<li><p><span data-ttu-id="bc61b-161">Подключите устройство с бесперебойной подразделением к порту Ethernet и PSTN-порту.</span><span class="sxs-lookup"><span data-stu-id="bc61b-161">Connect the Survivable Branch Appliance to an Ethernet port and PSTN port.</span></span></p></li>
<li><p><span data-ttu-id="bc61b-162">Запуск бесперебойно работающего устройства филиалов.</span><span class="sxs-lookup"><span data-stu-id="bc61b-162">Start the Survivable Branch Appliance.</span></span></p></li>
<li><p><span data-ttu-id="bc61b-163">Присоедините к домену работающее устройство филиала с помощью учетной записи пользователя домена, созданной для работающего устройства филиала на центральном сайте.</span><span class="sxs-lookup"><span data-stu-id="bc61b-163">Join the Survivable Branch Appliance to the domain, using the domain user account created for the Survivable Branch Appliance at the central site.</span></span> <span data-ttu-id="bc61b-164">Укажите полное доменное имя и IP-адрес, совпадающие с полным доменным именем, которое создано в учетной записи компьютера.</span><span class="sxs-lookup"><span data-stu-id="bc61b-164">Set the FQDN and IP address to match the FQDN created in the computer account.</span></span></p></li>
<li><p><span data-ttu-id="bc61b-165">Настройте бесперебойную ветвь устройства с помощью пользовательского интерфейса.</span><span class="sxs-lookup"><span data-stu-id="bc61b-165">Configure the Survivable Branch Appliance using the OEM user interface.</span></span></p></li>
<li><p><span data-ttu-id="bc61b-166">Проверьте подключение к ТСОП.</span><span class="sxs-lookup"><span data-stu-id="bc61b-166">Test PSTN connectivity.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="bc61b-167">Учетная запись технического специалиста должна принадлежать к группе RTCUniversalSBATechnicians.</span><span class="sxs-lookup"><span data-stu-id="bc61b-167">The technician user account must be a member of RTCUniversalSBATechnicians.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="survivable-branch-server-details"></a><span data-ttu-id="bc61b-168">Описание сервера обеспечения связи в филиалах</span><span class="sxs-lookup"><span data-stu-id="bc61b-168">Survivable Branch Server Details</span></span>

<span data-ttu-id="bc61b-169">В построителе топологии создайте сайт ветви, добавьте к нему бесперебойный сервер филиалов, а затем запустите мастер развертывания Lync Server на компьютере, на котором вы хотите установить роль.</span><span class="sxs-lookup"><span data-stu-id="bc61b-169">In Topology Builder create the branch site, add the Survivable Branch Server to that site, and then run the Lync Server Deployment Wizard on the computer where you want to install the role.</span></span>

</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bc61b-170">См. также</span><span class="sxs-lookup"><span data-stu-id="bc61b-170">See Also</span></span>


[<span data-ttu-id="bc61b-171">Развертывание Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc61b-171">Deploying Lync Server 2013</span></span>](lync-server-2013-deploying-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

