---
title: 'Lync Server 2013: создание устройства для проверки функциональных возможностей обновления'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ad2fa5283561e1096cfe7e3053db59c3cd2e40e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a><span data-ttu-id="91dbe-102">Создание устройства для проверки функциональных возможностей обновления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="91dbe-102">Create a device to test update functionality in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="91dbe-103">_**Тема последнего изменения:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="91dbe-103">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="91dbe-104">Вы можете добавить устройство проверки на страницу **Устройство проверки** и затем использовать его для проверки функциональных возможностей новых обновлений перед их развертыванием на производственных устройствах.</span><span class="sxs-lookup"><span data-stu-id="91dbe-104">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="91dbe-105">Вы можете протестировать устройство глобально (во всей среде Lync Server) или на одном сайте.</span><span class="sxs-lookup"><span data-stu-id="91dbe-105">You can test a device globally (throughout your entire Lync Server environment) or within a single site.</span></span> <span data-ttu-id="91dbe-106">Устройство проверки указывается по MAC-адресу или серийному номеру.</span><span class="sxs-lookup"><span data-stu-id="91dbe-106">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="91dbe-107">При добавлении устройства оно отображается в списке на странице " **тестирование устройства** " на панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91dbe-107">When you add a device, it appears in the list on the **Test Device** page of the Lync Server Control Panel.</span></span>

<div>

## <a name="to-add-a-test-device"></a><span data-ttu-id="91dbe-108">Добавление тестового устройства</span><span class="sxs-lookup"><span data-stu-id="91dbe-108">To add a test device</span></span>

1.  <span data-ttu-id="91dbe-109">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="91dbe-109">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="91dbe-110">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="91dbe-110">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="91dbe-111">На панели навигации слева выберите пункт **Клиенты**, а затем — пункт **Проверка устройства**.</span><span class="sxs-lookup"><span data-stu-id="91dbe-111">In the left navigation bar, click **Clients**, and then click **Test Device**.</span></span>

3.  <span data-ttu-id="91dbe-112">Нажмите кнопку **создать**, а затем щелкните либо **глобальное тестовое** устройство, либо тестовое **устройство сайта**.</span><span class="sxs-lookup"><span data-stu-id="91dbe-112">Click **New**, and then click either **Global test device** or **Site test device**.</span></span>

4.  <span data-ttu-id="91dbe-113">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="91dbe-113">Do one of the following:</span></span>
    
      - <span data-ttu-id="91dbe-114">Если вы щелкните **глобальное тестовое устройство**, перейдите к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="91dbe-114">If you clicked **Global test device**, skip to the next step.</span></span>
    
      - <span data-ttu-id="91dbe-115">Если выбрано **тестовое устройство сайта**, выберите сайт из списка доступных сайтов и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="91dbe-115">If you clicked **Site test device**, select a site from the list of available sites, and then click **OK**.</span></span>

5.  <span data-ttu-id="91dbe-116">В окне **нового тестового устройства**введите имя устройства в поле **имя устройства**.</span><span class="sxs-lookup"><span data-stu-id="91dbe-116">In **New Test Device**, type a name for the device in **Device name**.</span></span>

6.  <span data-ttu-id="91dbe-117">В поле **тип идентификатора**выберите один из **компьютеров: Mac-адрес** или **серийный номер**.</span><span class="sxs-lookup"><span data-stu-id="91dbe-117">Under **Identifier type**, click either **MAC address** or **Serial number**.</span></span>

7.  <span data-ttu-id="91dbe-118">В поле **уникальный идентификатор** введите MAC-адрес или серийный номер устройства.</span><span class="sxs-lookup"><span data-stu-id="91dbe-118">In the **Unique identifier** box, type the MAC address or serial number of the device.</span></span>

8.  <span data-ttu-id="91dbe-119">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="91dbe-119">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="91dbe-120">Создание тестовых устройств с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="91dbe-120">Creating Test Devices by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="91dbe-121">Тестовые устройства можно создавать с помощью Windows PowerShell и командлета New-Кстестдевице.</span><span class="sxs-lookup"><span data-stu-id="91dbe-121">Test devices can be created by using Windows PowerShell and the New-CsTestDevice cmdlet.</span></span> <span data-ttu-id="91dbe-122">Этот командлет можно выполнить либо из управляющей оболочки Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91dbe-122">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="91dbe-123">Подробнее об использовании удаленной оболочки Windows PowerShell для подключения к серверу Lync Server можно найти в статье "Краткое руководство по работе с Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" на [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)веб-сервере Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91dbe-123">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="91dbe-124">При создании тестовых устройств с помощью этого командлета необходимо выполнить два действия:</span><span class="sxs-lookup"><span data-stu-id="91dbe-124">When creating test devices using this cmdlet, you must do two things:</span></span>

  - <span data-ttu-id="91dbe-125">Укажите значение MACAddress или SerialNumber в качестве Идентифиертипе.</span><span class="sxs-lookup"><span data-stu-id="91dbe-125">Specify either MACAddress or SerialNumber as the IdentifierType.</span></span>

  - <span data-ttu-id="91dbe-126">Включите область при указании удостоверения устройства.</span><span class="sxs-lookup"><span data-stu-id="91dbe-126">Include the scope when specifying the device Identity.</span></span> <span data-ttu-id="91dbe-127">Для создания нового устройства в глобальной области используйте синтаксис, подобный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="91dbe-127">To create a new device at the global scope use syntax similar to this:</span></span>
    
        -Identity "global/WindowsPhone"
    
    <span data-ttu-id="91dbe-128">Для создания тестового устройства в области сайта используйте синтаксис, подобный приведенному ниже.</span><span class="sxs-lookup"><span data-stu-id="91dbe-128">To create a test device at the site scope use syntax similar to this:</span></span>
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a><span data-ttu-id="91dbe-129">Создание тестового устройства с помощью MAC-адреса</span><span class="sxs-lookup"><span data-stu-id="91dbe-129">To create a test device by using the MAC address</span></span>

  - <span data-ttu-id="91dbe-130">Эта команда создает тестовое устройство в глобальной области и использует MAC-адрес в качестве Идентифиертипе:</span><span class="sxs-lookup"><span data-stu-id="91dbe-130">This command creates a test device at the global scope, and using the MAC address as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a><span data-ttu-id="91dbe-131">Создание тестового устройства с использованием серийного номера</span><span class="sxs-lookup"><span data-stu-id="91dbe-131">To create a test device by using the serial number</span></span>

  - <span data-ttu-id="91dbe-132">Эта команда создает новое тестовое устройство в области сайта (для сайта Redmond) и использует серийный номер в качестве Идентифиертипе:</span><span class="sxs-lookup"><span data-stu-id="91dbe-132">This command creates a new test device at the site scope (for the Redmond site) and uses the serial number as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

<span data-ttu-id="91dbe-133">Дополнительные сведения можно найти в разделе справки по командлету [New-кстестдевице](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .</span><span class="sxs-lookup"><span data-stu-id="91dbe-133">For more information, see the help topic for the [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

