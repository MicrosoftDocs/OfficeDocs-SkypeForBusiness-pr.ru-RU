---
title: Настройка различных политик
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Configuring the Various Policies
ms:assetid: e3b3cbda-7c17-470b-acb0-82fdcc473184
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945610(v=OCS.15)
ms:contentKeyID: 51541436
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a105ea62b82d904007a2faa0493fd17092b84462
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34842051"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-various-policies"></a><span data-ttu-id="eeb18-102">Настройка различных политик</span><span class="sxs-lookup"><span data-stu-id="eeb18-102">Configuring the Various Policies</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eeb18-103">_**Тема последнего изменения:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="eeb18-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<div>

## <a name="configuring-the-various-policies"></a><span data-ttu-id="eeb18-104">Настройка различных политик</span><span class="sxs-lookup"><span data-stu-id="eeb18-104">Configuring the Various Policies</span></span>

<span data-ttu-id="eeb18-105">Ниже приведены различные политики, которые можно настроить в топологии Lync Server 2013 перед запуском средства нагрузки и производительности Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eeb18-105">Here are the various policies that you can configure in your Lync Server 2013 topology, prior to running the Lync Server 2013 Stress and Performance Tool.</span></span>

<div>

## <a name="configuring-the-archiving-policy"></a><span data-ttu-id="eeb18-106">Настройка политики архивации</span><span class="sxs-lookup"><span data-stu-id="eeb18-106">Configuring the Archiving Policy</span></span>

<span data-ttu-id="eeb18-107">Посмотрите пример сценария Арчивингполици. ps1.</span><span class="sxs-lookup"><span data-stu-id="eeb18-107">See the example script ArchivingPolicy.ps1.</span></span> <span data-ttu-id="eeb18-108">Этот сценарий следует использовать только в том случае, если в вашей топологии развернут сервер архивирования.</span><span class="sxs-lookup"><span data-stu-id="eeb18-108">You need to use this script only if an Archiving Server is deployed in your topology.</span></span> <span data-ttu-id="eeb18-109">Дополнительные сведения можно найти в документации по Lync Server 2013 и командлетов для [архивации и мониторинга командлетов в Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="eeb18-109">For details, see the Lync Server 2013 documentation and cmdlet Help for [Archiving and Monitoring cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415629\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-conferencing-policy"></a><span data-ttu-id="eeb18-110">Настройка политики конференц-связи</span><span class="sxs-lookup"><span data-stu-id="eeb18-110">Configuring the Conferencing Policy</span></span>

<span data-ttu-id="eeb18-111">Посмотрите пример сценария Митингполици. ps1.</span><span class="sxs-lookup"><span data-stu-id="eeb18-111">See the example script MeetingPolicy.ps1.</span></span> <span data-ttu-id="eeb18-112">Дополнительные сведения можно найти в документации Lync Server 2013 и в справке по командлетам [веб-конференций в Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="eeb18-112">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-contacts-policy"></a><span data-ttu-id="eeb18-113">Настройка политики контактов</span><span class="sxs-lookup"><span data-stu-id="eeb18-113">Configuring the Contacts Policy</span></span>

<span data-ttu-id="eeb18-114">Смотрите пример Контактсполици. ps1.</span><span class="sxs-lookup"><span data-stu-id="eeb18-114">See the example ContactsPolicy.ps1.</span></span> <span data-ttu-id="eeb18-115">Подробные сведения можно найти в документации Lync Server 2013 и в справке по командлетам для [обмена мгновенными сообщениями и проверки присутствия в Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="eeb18-115">For details, see the Lync Server 2013 documentation and the cmdlet Help for [IM and presence cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398611\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-federation-policy"></a><span data-ttu-id="eeb18-116">Настройка политики Федерации</span><span class="sxs-lookup"><span data-stu-id="eeb18-116">Configuring the Federation Policy</span></span>

<span data-ttu-id="eeb18-117">Смотрите пример Федератионполици. ps1.</span><span class="sxs-lookup"><span data-stu-id="eeb18-117">See the example FederationPolicy.ps1.</span></span> <span data-ttu-id="eeb18-118">Дополнительные сведения можно найти в документации по Lync Server 2013 и о командлетах [пограничного сервера в командлетах Lync server 2013](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\)) и [Федерации и внешнего доступа в Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="eeb18-118">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Edge Server cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415635\(v=ocs.15\)) and [Federation and external access cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415651\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-call-admission-control-policy"></a><span data-ttu-id="eeb18-119">Настройка политики управления допуском звонков</span><span class="sxs-lookup"><span data-stu-id="eeb18-119">Configuring the Call Admission Control Policy</span></span>

<span data-ttu-id="eeb18-120">Смотрите пример Бандвидсполици. ps1.</span><span class="sxs-lookup"><span data-stu-id="eeb18-120">See the example BandwidthPolicy.ps1.</span></span> <span data-ttu-id="eeb18-121">Дополнительные сведения можно найти в документации Lync Server 2013, посвященной управлению допуском [звонков в Lync server 2013](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\)) , и Справка по командлетам [управления допуском звонков в Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="eeb18-121">For details, see the Lync Server 2013 documentation [Overview of call admission control in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg398529\(v=ocs.15\)) and the cmdlet Help for [Call admission control cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415676\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-the-voice-routing-rules"></a><span data-ttu-id="eeb18-122">Настройка правил для маршрутизации голосовых сообщений</span><span class="sxs-lookup"><span data-stu-id="eeb18-122">Configuring the Voice Routing Rules</span></span>

<span data-ttu-id="eeb18-123">Смотрите пример Раутингрулес. ps1.</span><span class="sxs-lookup"><span data-stu-id="eeb18-123">See the example RoutingRules.ps1.</span></span> <span data-ttu-id="eeb18-124">Настроив правила маршрутизации голосовой связи, запишите контекст телефона (то есть,/Локатион Profile или/Симпленаме), а также внутренние и внешние коды города, чтобы их можно было указывать при создании пользователей и настройке конфигурации Линкперфтул (специально для PSTN-UC и UC-КТСОП.</span><span class="sxs-lookup"><span data-stu-id="eeb18-124">When you configure the voice routing rules, take note of the Phone Context (that is, /Location Profile or /SimpleName) and Internal/External Area Codes so that you can specify them when creating users and during LyncPerfTool configuration (specifically for PSTN-UC and UC-PSTN).</span></span> <span data-ttu-id="eeb18-125">Например, параметр Симпленаме в вызове командлета **New-ксдиалплан** в примере раутингрулес. ps1 следует использовать для значения локатионпрофиле на следующем рисунке файла усерпрофилеженератор. exe.</span><span class="sxs-lookup"><span data-stu-id="eeb18-125">For example, the SimpleName parameter in the call to the **New-CsDialPlan** cmdlet in the RoutingRules.ps1 example should be used for the LocationProfile value in the following figure of UserProfileGenerator.exe.</span></span>

<span data-ttu-id="eeb18-126">![Образец правила маршрутизации голосовых сообщений.] (images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Образец правила маршрутизации голосовых сообщений.")</span><span class="sxs-lookup"><span data-stu-id="eeb18-126">![Sample voice routing rule.](images/JJ945610.9f34d971-4ed0-4a4c-b101-086a91c4578c(OCS.15).jpg "Sample voice routing rule.")</span></span>

<span data-ttu-id="eeb18-127">Дополнительные сведения можно найти в документации по Lync Server 2013 и о командлетах для [корпоративных голосовых команд в Lync server 2013](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="eeb18-127">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Enterprise Voice cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415658\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-conferencing-attendant-application"></a><span data-ttu-id="eeb18-128">Настройка приложения-участника конференц-связи</span><span class="sxs-lookup"><span data-stu-id="eeb18-128">Configuring Conferencing Attendant application</span></span>

<span data-ttu-id="eeb18-129">Смотрите пример Конференцеаутоаттендантконфигуратион. ps1.</span><span class="sxs-lookup"><span data-stu-id="eeb18-129">See the example ConferenceAutoAttendantConfiguration.ps1.</span></span> <span data-ttu-id="eeb18-130">Обратите внимание на КонференЦингаутоаттендант номер телефона (1121111111 по умолчанию), чтобы можно было ввести его в средство настройки средств Линкперф для создания конфигурации.</span><span class="sxs-lookup"><span data-stu-id="eeb18-130">Take note of the ConferencingAutoAttendant phone number (1121111111, by default), so that you can type it into the LyncPerf Tool Configuration tool for configuration generation.</span></span>

<span data-ttu-id="eeb18-131">![Настройка приложения-участника Конференц] -связи (images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Настройка приложения-участника Конференц") -связи</span><span class="sxs-lookup"><span data-stu-id="eeb18-131">![Configuring the Conferencing Attendant application](images/JJ945610.0618a22f-27a9-423a-9085-d2bf71e82db6(OCS.15).jpg "Configuring the Conferencing Attendant application")</span></span>

<span data-ttu-id="eeb18-132">Дополнительные сведения можно найти в документации Lync Server 2013 и в разделе Справка по командлетам для [веб-конференций в](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)) lync Server 2013 и [командлетах конференции с телефонным подключением в Lync сервер 2013](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="eeb18-132">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Web conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415675\(v=ocs.15\)) and [Dial-in conferencing cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415630\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-lync-server-call-park-service"></a><span data-ttu-id="eeb18-133">Настройка службы приостановки звонков в Lync Server</span><span class="sxs-lookup"><span data-stu-id="eeb18-133">Configuring Lync Server Call Park Service</span></span>

<span data-ttu-id="eeb18-134">По умолчанию метод приостановки звонка отключен.</span><span class="sxs-lookup"><span data-stu-id="eeb18-134">Call Park is disabled by default.</span></span> <span data-ttu-id="eeb18-135">Смотрите пример Каллпаркконфигуратион. ps1.</span><span class="sxs-lookup"><span data-stu-id="eeb18-135">See the example CallParkConfiguration.ps1.</span></span> <span data-ttu-id="eeb18-136">Дополнительные сведения можно найти в документации по Lync Server 2013 и о командлетах [приложения для приостановки звонков в Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\)).</span><span class="sxs-lookup"><span data-stu-id="eeb18-136">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Call Park application cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415639\(v=ocs.15\)).</span></span>

</div>

<div>

## <a name="configuring-emergency-calls"></a><span data-ttu-id="eeb18-137">Настройка экстренных вызовов</span><span class="sxs-lookup"><span data-stu-id="eeb18-137">Configuring Emergency Calls</span></span>

<span data-ttu-id="eeb18-138">Выполните указанные ниже действия, чтобы настроить стресс и тестирование производительности для экстренных вызовов.</span><span class="sxs-lookup"><span data-stu-id="eeb18-138">Perform the following steps to configure stress and performance testing for emergency calls.</span></span>

1.  <span data-ttu-id="eeb18-139">Настройте голосовой маршрут для вызова экстренной помощи.</span><span class="sxs-lookup"><span data-stu-id="eeb18-139">Set up a voice route for emergency calls.</span></span> <span data-ttu-id="eeb18-140">Пример настройки этого голосового маршрута можно найти в Раутингрулес. ps1 под комментарием "Route E911 to КТСОП".</span><span class="sxs-lookup"><span data-stu-id="eeb18-140">See the RoutingRules.ps1 script under the comment "Route E911 to PSTN" for an example of setting up this voice route.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="eeb18-141">Пример команды в Раутингрулес. ps1 имеет числовой шаблон, который включает число 119 вместо 911.</span><span class="sxs-lookup"><span data-stu-id="eeb18-141">The example command in RoutingRules.ps1 has a number pattern that includes the number 119 rather than 911.</span></span> <span data-ttu-id="eeb18-142">Следует избегать использования 911 (или фактического местного номера для экстренного реагирования), чтобы предотвратить случайные вызовы локальных аварийных операторов в ходе нагрузочного тестирования.</span><span class="sxs-lookup"><span data-stu-id="eeb18-142">You should avoid using 911 (or your actual local emergency number) to prevent accidental calls to your local emergency operators during load testing.</span></span> <span data-ttu-id="eeb18-143">Эта конфигурация предназначена только для целей моделирования.</span><span class="sxs-lookup"><span data-stu-id="eeb18-143">This configuration is for simulation purposes only.</span></span>

    
    </div>

2.  <span data-ttu-id="eeb18-144">Настройте адреса, заполнив значения на вкладке **LIS** в усерпровисионингтул, как показано на приведенном ниже рисунке.</span><span class="sxs-lookup"><span data-stu-id="eeb18-144">Configure addresses by filling in the values on the **LIS** tab in the UserProvisioningTool, as shown in the following figure.</span></span>
    
    <span data-ttu-id="eeb18-145">![Настройка службы сведений о расположении.] (images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Настройка службы сведений о расположении.")</span><span class="sxs-lookup"><span data-stu-id="eeb18-145">![Configuring the Location Information Service.](images/JJ945610.8ac1faa1-e9f9-40d0-b8b7-b159f4f459f7(OCS.15).jpg "Configuring the Location Information Service.")</span></span>  

3.  <span data-ttu-id="eeb18-146">Щелкните **создать файлы конфигурации LIS**.</span><span class="sxs-lookup"><span data-stu-id="eeb18-146">Click **Generate LIS Config Files**.</span></span>

4.  <span data-ttu-id="eeb18-147">Создаются файлы CSV для портов, подсетей, переключателей и точек доступа к беспроводной сети (Вапс), а также XML-файла для средства нагрузки и производительности Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="eeb18-147">CSV files for ports, subnets, switches, and wireless access points (WAPs), and an XML file for the Lync Server 2013 Stress and Performance Tool, are generated.</span></span> <span data-ttu-id="eeb18-148">CSV-файлы будут использоваться в качестве входных данных (в той же папке) при настройке службы сведений о расположении (LIS) с помощью сценария Лисконфигуратион. ps1.</span><span class="sxs-lookup"><span data-stu-id="eeb18-148">The CSV files are to be used as inputs (in the same folder) when configuring Location Information service (LIS) with the LisConfiguration.ps1 script.</span></span> <span data-ttu-id="eeb18-149">Переместите созданный файл Locations0. XML в ту же папку, в которой находится исполняемая программа Lync Server 2013 (Линкперфтул. exe), которая будет запускать сценарии профилей местоположений (абонентской группы).</span><span class="sxs-lookup"><span data-stu-id="eeb18-149">Move the generated Locations0.xml file to the same folder as the Lync Server 2013 Stress and Performance Tool executable (LyncPerfTool.exe), which will run location profile (dial plan) scenarios.</span></span>

</div>

<div>

## <a name="creating-enabling-configuring-and-disabling-users"></a><span data-ttu-id="eeb18-150">Создание, включение, Настройка и отключение пользователей</span><span class="sxs-lookup"><span data-stu-id="eeb18-150">Creating, Enabling, Configuring and Disabling Users</span></span>

<span data-ttu-id="eeb18-151">Перед выполнением следующих сценариев необходимо создать все пользователи.</span><span class="sxs-lookup"><span data-stu-id="eeb18-151">You should create all your users before running the following scripts.</span></span> <span data-ttu-id="eeb18-152">Следуйте инструкциям в разделе [Создание пользователей и контактов](create-users-and-contacts.md) , чтобы создать пользователей.</span><span class="sxs-lookup"><span data-stu-id="eeb18-152">Follow the instructions in [Create Users and Contacts](create-users-and-contacts.md) to create users.</span></span> <span data-ttu-id="eeb18-153">Дополнительные сведения можно найти в документации по командлетам Lync Server 2013 для командлетов [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\))и [Disable-CsUser](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) .</span><span class="sxs-lookup"><span data-stu-id="eeb18-153">For details, see the Lync Server 2013 cmdlet documentation for the [Get-CsUser](https://technet.microsoft.com/en-us/library/gg398125\(v=ocs.15\)), [Set-CsUser](https://technet.microsoft.com/en-us/library/gg398510\(v=ocs.15\)), and [Disable-CsUser](https://technet.microsoft.com/en-us/library/gg398747\(v=ocs.15\)) cmdlets.</span></span>

</div>

<div>

## <a name="configuring-response-group-application"></a><span data-ttu-id="eeb18-154">Настройка приложения группы ответа</span><span class="sxs-lookup"><span data-stu-id="eeb18-154">Configuring Response Group application</span></span>

<span data-ttu-id="eeb18-155">Смотрите пример Респонсеграупконфигуратион. ps1.</span><span class="sxs-lookup"><span data-stu-id="eeb18-155">See the example ResponseGroupConfiguration.ps1.</span></span> <span data-ttu-id="eeb18-156">Дополнительные сведения можно найти в документации по Lync Server 2013 и о командлетах [приложения группы ответа в Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\)). Чтобы просмотреть конфигурацию приложения группы ответа, посмотрите `https://<poolfqdn>/RgsConfig/`, как показано на рисунке ниже.</span><span class="sxs-lookup"><span data-stu-id="eeb18-156">For details, see the Lync Server 2013 documentation and the cmdlet Help for [Response Group application cmdlets in Lync Server 2013](https://technet.microsoft.com/en-us/library/gg415654\(v=ocs.15\)).To review the Response Group application configuration, see `https://<poolfqdn>/RgsConfig/`, as shown in the following figure.</span></span>

<span data-ttu-id="eeb18-157">![Средство настройки группы ответа.] (images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "Средство настройки группы ответа.")</span><span class="sxs-lookup"><span data-stu-id="eeb18-157">![The Response Group Configuration Tool.](images/JJ945610.480a9440-2283-4533-98f8-86daaab4781c(OCS.15).jpg "The Response Group Configuration Tool.")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

