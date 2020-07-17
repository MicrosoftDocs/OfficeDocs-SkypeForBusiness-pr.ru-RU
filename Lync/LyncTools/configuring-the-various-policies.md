---
title: Настройка различных политик
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8270452893e6e2e531eed86d730a1ea4f9f604fc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755493"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a><span data-ttu-id="c995f-102">Настройка различных политик</span><span class="sxs-lookup"><span data-stu-id="c995f-102">Configuring the Various Policies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c995f-103">_**Последнее изменение темы:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="c995f-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="configuring-the-various-policies"></a><span data-ttu-id="c995f-104">Настройка различных политик</span><span class="sxs-lookup"><span data-stu-id="c995f-104">Configuring the Various Policies</span></span>

<span data-ttu-id="c995f-105">Ниже приведены различные политики, которые можно настроить в топологии Lync Server 2013 до запуска средства нагрузки и производительности Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c995f-105">Here are the various policies that you can configure in your Lync Server 2013 topology, prior to running the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="configuring-the-archiving-policy"></a><span data-ttu-id="c995f-106">Настройка политики архивации</span><span class="sxs-lookup"><span data-stu-id="c995f-106">Configuring the Archiving Policy</span></span>

<span data-ttu-id="c995f-107">Просмотрите пример скрипта ArchivingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="c995f-107">See the example script ArchivingPolicy.ps1.</span></span> <span data-ttu-id="c995f-108">Этот сценарий необходимо использовать, только если в вашей топологии развернут сервер архивации.</span><span class="sxs-lookup"><span data-stu-id="c995f-108">You need to use this script only if an Archiving Server is deployed in your topology.</span></span> <span data-ttu-id="c995f-109">Дополнительные сведения см. в справке по Lync Server 2013 и командлетам для [архивации и мониторинга командлетов в Lync Server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c995f-109">For details, see the Lync Server 2013 documentation and cmdlet Help for [Archiving and Monitoring cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415629\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a><span data-ttu-id="c995f-110">Настройка политики конференц-связи</span><span class="sxs-lookup"><span data-stu-id="c995f-110">Configuring the Conferencing Policy</span></span>

<span data-ttu-id="c995f-111">Просмотрите пример скрипта MeetingPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="c995f-111">See the example script MeetingPolicy.ps1.</span></span> <span data-ttu-id="c995f-112">Для получения дополнительных сведений ознакомьтесь с документацией по Lync Server 2013 и справка командлета для [командлетов веб-конференций в Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c995f-112">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-contacts-policy"></a><span data-ttu-id="c995f-113">Настройка политики контактов</span><span class="sxs-lookup"><span data-stu-id="c995f-113">Configuring the Contacts Policy</span></span>

<span data-ttu-id="c995f-114">Просмотрите пример ContactsPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="c995f-114">See the example ContactsPolicy.ps1.</span></span> <span data-ttu-id="c995f-115">Для получения дополнительных сведений ознакомьтесь с документацией по Lync Server 2013 и справка командлета для [мгновенных сообщений и командлетов присутствия в Lync Server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c995f-115">For details, see the Lync Server 2013 documentation and the cmdlet Help for [IM and presence cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg398611\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-federation-policy"></a><span data-ttu-id="c995f-116">Настройка политики Федерации</span><span class="sxs-lookup"><span data-stu-id="c995f-116">Configuring the Federation Policy</span></span>

<span data-ttu-id="c995f-117">Просмотрите пример FederationPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="c995f-117">See the example FederationPolicy.ps1.</span></span> <span data-ttu-id="c995f-118">Для получения дополнительных сведений ознакомьтесь с документацией по Lync Server 2013 и справке командлетов [пограничного сервера в командлетах Lync server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) , [Федерации и внешнего доступа в Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c995f-118">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Edge Server cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415635\(v=ocs.15\)) and [Federation and external access cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415651\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a><span data-ttu-id="c995f-119">Настройка политики контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="c995f-119">Configuring the Call Admission Control Policy</span></span>

<span data-ttu-id="c995f-120">Просмотрите пример BandwidthPolicy.ps1.</span><span class="sxs-lookup"><span data-stu-id="c995f-120">See the example BandwidthPolicy.ps1.</span></span> <span data-ttu-id="c995f-121">Для получения дополнительных сведений ознакомьтесь со статьей Lync Server 2013 в документации по [контролю допуска звонков в Lync server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) и справке командлета для [командлетов контроля допуска звонков в Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c995f-121">For details, see the Lync Server 2013 documentation [Overview of call admission control in Lync Server 2013](https://technet.microsoft.com/library/gg398529\(v=ocs.15\)) and the cmdlet Help for [Call admission control cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415676\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a><span data-ttu-id="c995f-122">Настройка правил маршрутизации голосовой связи</span><span class="sxs-lookup"><span data-stu-id="c995f-122">Configuring the Voice Routing Rules</span></span>

<span data-ttu-id="c995f-123">Просмотрите пример RoutingRules.ps1.</span><span class="sxs-lookup"><span data-stu-id="c995f-123">See the example RoutingRules.ps1.</span></span> <span data-ttu-id="c995f-124">При настройке правил маршрутизации голосовой связи запишите контекст телефона (то есть,/Локатион Profile или/Симпленаме), а также внутренние/внешние коды областей, чтобы их можно было указать при создании пользователей и во время настройки Линкперфтул (в частности, для PSTN-UC и UC-PSTN).</span><span class="sxs-lookup"><span data-stu-id="c995f-124">When you configure the voice routing rules, take note of the Phone Context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes so that you can specify them when creating users and during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span> <span data-ttu-id="c995f-125">Например, параметр Симпленаме в вызове командлета **New – CsDialPlan** в RoutingRules.ps1 примере должен использоваться для значения LocationProfile на следующем рисунке UserProfileGenerator.exe.</span><span class="sxs-lookup"><span data-stu-id="c995f-125">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe.</span></span>

<span data-ttu-id="c995f-126">![Пример правила маршрутизации голосовых вызовов.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Пример правила маршрутизации голосовых вызовов.")</span><span class="sxs-lookup"><span data-stu-id="c995f-126">![Sample voice routing rule.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Sample voice routing rule.")</span></span>

<span data-ttu-id="c995f-127">Для получения дополнительных сведений ознакомьтесь с документацией по Lync Server 2013 и обратитесь к разделу Справка по командлетам [корпоративной голосовой связи в Lync server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c995f-127">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Enterprise Voice cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415658\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a><span data-ttu-id="c995f-128">Настройка приложения помощника по конференц-связи</span><span class="sxs-lookup"><span data-stu-id="c995f-128">Configuring Conferencing Attendant application</span></span>

<span data-ttu-id="c995f-129">Просмотрите пример ConferenceAutoAttendantConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="c995f-129">See the example ConferenceAutoAttendantConfiguration.ps1.</span></span> <span data-ttu-id="c995f-130">Запишите номер телефона КонференЦингаутоаттендант (1121111111 по умолчанию), чтобы можно было ввести его в средство настройки средства Линкперф для создания конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c995f-130">Take note of the ConferencingAutoAttendant phone number (1121111111, by default), so that you can type it into the LyncPerf Tool Configuration tool for configuration generation.</span></span>

<span data-ttu-id="c995f-131">![Настройка приложения "помощник по конференц-связи"](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Настройка приложения "помощник по конференц-связи"")</span><span class="sxs-lookup"><span data-stu-id="c995f-131">![Configuring the Conferencing Attendant application](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuring the Conferencing Attendant application")</span></span>

<span data-ttu-id="c995f-132">Для получения дополнительных сведений ознакомьтесь с документацией по Lync Server 2013 и справке командлета для [командлетов веб-конференций в Lync server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) и [командлетах конференц-связи с телефонным подключением в Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c995f-132">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415675\(v=ocs.15\)) and [Dial-in conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415630\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a><span data-ttu-id="c995f-133">Настройка службы парковки вызовов Lync Server</span><span class="sxs-lookup"><span data-stu-id="c995f-133">Configuring Lync Server Call Park Service</span></span>

<span data-ttu-id="c995f-134">По умолчанию парковки вызовов отключен.</span><span class="sxs-lookup"><span data-stu-id="c995f-134">Call Park is disabled by default.</span></span> <span data-ttu-id="c995f-135">Просмотрите пример CallParkConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="c995f-135">See the example CallParkConfiguration.ps1.</span></span> <span data-ttu-id="c995f-136">Для получения дополнительных сведений ознакомьтесь с документацией по Lync Server 2013 и справка командлета для [командлетов приложений парковки вызовов в Lync server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="c995f-136">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Call Park application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415639\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-emergency-calls"></a><span data-ttu-id="c995f-137">Настройка экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="c995f-137">Configuring Emergency Calls</span></span>

<span data-ttu-id="c995f-138">Выполните указанные ниже действия, чтобы настроить нагрузочное тестирование и тестирование производительности для экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="c995f-138">Perform the following steps to configure stress and performance testing for emergency calls.</span></span>

1.  <span data-ttu-id="c995f-139">Настройте маршрут голосовой связи для экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="c995f-139">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="c995f-140">Пример настройки этого маршрута голосовой связи представлен в RoutingRules.ps1 сценарии под комментарием "Route E911 to PSTN".</span><span class="sxs-lookup"><span data-stu-id="c995f-140">See the RoutingRules.ps1 script under the comment "Route E911 to PSTN" for an example of setting up this voice route.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="c995f-141">Пример команды в RoutingRules.ps1 имеет числовой шаблон, включающий число 119, а не 911.</span><span class="sxs-lookup"><span data-stu-id="c995f-141">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="c995f-142">Не следует использовать 911 (или фактический локальный номер экстренного реагирования) для предотвращения случайных вызовов локальных аварийных операторов во время нагрузочного тестирования.</span><span class="sxs-lookup"><span data-stu-id="c995f-142">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during load testing.</span></span> <span data-ttu-id="c995f-143">Эта конфигурация предназначена только для целей моделирования.</span><span class="sxs-lookup"><span data-stu-id="c995f-143">This configuration is for simulation purposes only.</span></span>

    
    </div>

2.  <span data-ttu-id="c995f-144">Настройте адреса, заполнив значения на вкладке **LIS (LIS** ) в усерпровисионингтул, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="c995f-144">Configure addresses by filling in the values on the **LIS** tab in the UserProvisioningTool, as shown in the following figure.</span></span>
    
    <span data-ttu-id="c995f-145">![Настройка службы сведений о местоположении.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Настройка службы сведений о местоположении.")</span><span class="sxs-lookup"><span data-stu-id="c995f-145">![Configuring the Location Information Service.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configuring the Location Information Service.")</span></span>  

3.  <span data-ttu-id="c995f-146">Щелкните **создать файлы конфигурации LIS**.</span><span class="sxs-lookup"><span data-stu-id="c995f-146">Click **Generate LIS Config Files**.</span></span>

4.  <span data-ttu-id="c995f-147">Создаются CSV-файлы для портов, подсетей, коммутаторов и точек беспроводного доступа (WAPs), а также XML-файла для средства нагрузки и производительности Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c995f-147">CSV files for ports, subnets, switches, and wireless access points (WAPs), and an XML file for the Lync Server 2013 Stress and Performance Tool, are generated.</span></span> <span data-ttu-id="c995f-148">CSV-файлы используются в качестве входных данных (в той же папке) при настройке службы сведений о местоположении (LIS) с помощью скрипта LisConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="c995f-148">The CSV files are to be used as inputs (in the same folder) when configuring Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="c995f-149">Переместите созданный файл Locations0.xml в ту же папку, где находится исполняемый файл Lync Server 2013 (LyncPerfTool.exe), в котором будут выполняться сценарии профилей расположения (абонентской группы).</span><span class="sxs-lookup"><span data-stu-id="c995f-149">Move the generated Locations0.xml file to the same folder as the Lync Server 2013 Stress and Performance Tool executable (LyncPerfTool.exe), which will run location profile (dial plan) scenarios.</span></span>

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a><span data-ttu-id="c995f-150">Создание, включение, Настройка и отключение пользователей</span><span class="sxs-lookup"><span data-stu-id="c995f-150">Creating, Enabling, Configuring and Disabling Users</span></span>

<span data-ttu-id="c995f-151">Перед выполнением следующих сценариев необходимо создать всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="c995f-151">You should create all your users before running the following scripts.</span></span> <span data-ttu-id="c995f-152">Следуйте инструкциям в статье [CREATE Users and Contacts](create-users-and-contacts.md) to Create Users.</span><span class="sxs-lookup"><span data-stu-id="c995f-152">Follow the instructions in [Create Users and Contacts](create-users-and-contacts.md) to create users.</span></span> <span data-ttu-id="c995f-153">Для получения дополнительных сведений обратитесь к документации по командлетам Lync Server 2013 для командлетов [Get – CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\))и [Disable – CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="c995f-153">For details, see the Lync Server 2013 cmdlet documentation for the [Get-CsUser](https://technet.microsoft.com/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/library/gg398510\(v=ocs.15\)), and [Disable-CsUser](https://technet.microsoft.com/library/gg398747\(v=ocs.15\)) cmdlets.</span></span>

</div>

<div>

## <a name="configuring-response-group-application"></a><span data-ttu-id="c995f-154">Настройка приложения группы ответа</span><span class="sxs-lookup"><span data-stu-id="c995f-154">Configuring Response Group application</span></span>

<span data-ttu-id="c995f-155">Просмотрите пример ResponseGroupConfiguration.ps1.</span><span class="sxs-lookup"><span data-stu-id="c995f-155">See the example ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="c995f-156">Для получения дополнительных сведений ознакомьтесь с документацией по Lync Server 2013 и справка командлета для [командлетов приложений группы ответа в Lync Server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)). Чтобы просмотреть конфигурацию приложения группы ответа, посмотрите `https://<poolfqdn>/RgsConfig/` , как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="c995f-156">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Response Group application cmdlets in Lync Server 2013](https://technet.microsoft.com/library/gg415654\(v=ocs.15\)).To review the Response Group application configuration, see `https://<poolfqdn>/RgsConfig/`, as shown in the following figure.</span></span>

<span data-ttu-id="c995f-157">![Средство настройки группы ответа.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "Средство настройки группы ответа.")</span><span class="sxs-lookup"><span data-stu-id="c995f-157">![The Response Group Configuration Tool.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "The Response Group Configuration Tool.")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

