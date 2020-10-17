---
title: 'Lync Server 2013: создание устройства для проверки функциональных возможностей обновления'
description: 'Lync Server 2013: создание устройства для проверки функциональных возможностей обновления.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create a device to test update functionality
ms:assetid: ce509fd1-17b3-4b78-b269-fe5d06fe2e1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182587(v=OCS.15)
ms:contentKeyID: 48185466
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1d45d8970dc72abc8ea6095c879272394e34c54d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542175"
---
# <a name="create-a-device-to-test-update-functionality-in-lync-server-2013"></a><span data-ttu-id="3ea35-103">Создание устройства для проверки функциональных возможностей обновления в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3ea35-103">Create a device to test update functionality in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3ea35-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="3ea35-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="3ea35-105">Вы можете добавить устройство проверки на страницу **Устройство проверки** и затем использовать его для проверки функциональных возможностей новых обновлений перед их развертыванием на производственных устройствах.</span><span class="sxs-lookup"><span data-stu-id="3ea35-105">You can add a test device to the **Test Device** page and then use this device to verify the functionality of new updates before deploying the updates to production devices.</span></span> <span data-ttu-id="3ea35-106">Вы можете протестировать устройство глобально (во всей среде Lync Server) или на одном сайте.</span><span class="sxs-lookup"><span data-stu-id="3ea35-106">You can test a device globally (throughout your entire Lync Server environment) or within a single site.</span></span> <span data-ttu-id="3ea35-107">Устройство проверки указывается по MAC-адресу или серийному номеру.</span><span class="sxs-lookup"><span data-stu-id="3ea35-107">You identify a test device by its Media Access Control (MAC) address or serial number.</span></span> <span data-ttu-id="3ea35-108">При добавлении устройства оно отображается в списке на странице " **устройство тестирования** " в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ea35-108">When you add a device, it appears in the list on the **Test Device** page of the Lync Server Control Panel.</span></span>

<div>

## <a name="to-add-a-test-device"></a><span data-ttu-id="3ea35-109">Добавление тестового устройства</span><span class="sxs-lookup"><span data-stu-id="3ea35-109">To add a test device</span></span>

1.  <span data-ttu-id="3ea35-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="3ea35-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3ea35-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="3ea35-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="3ea35-112">В левой панели навигации щелкните **Клиенты**, а затем щелкните **проверить устройство**.</span><span class="sxs-lookup"><span data-stu-id="3ea35-112">In the left navigation bar, click **Clients**, and then click **Test Device**.</span></span>

3.  <span data-ttu-id="3ea35-113">Нажмите кнопку **создать**, а затем выберите либо **глобальное тестовое** устройство, либо **тестическое устройство сайта**.</span><span class="sxs-lookup"><span data-stu-id="3ea35-113">Click **New**, and then click either **Global test device** or **Site test device**.</span></span>

4.  <span data-ttu-id="3ea35-114">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="3ea35-114">Do one of the following:</span></span>
    
      - <span data-ttu-id="3ea35-115">Если выбрано **глобальное тестовое устройство**, перейдите к следующему шагу.</span><span class="sxs-lookup"><span data-stu-id="3ea35-115">If you clicked **Global test device**, skip to the next step.</span></span>
    
      - <span data-ttu-id="3ea35-116">Если выбрано **тестовое устройство сайта**, выберите сайт в списке доступных сайтов, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3ea35-116">If you clicked **Site test device**, select a site from the list of available sites, and then click **OK**.</span></span>

5.  <span data-ttu-id="3ea35-117">В поле **новое устройство проверки**введите имя устройства в поле **имя устройства**.</span><span class="sxs-lookup"><span data-stu-id="3ea35-117">In **New Test Device**, type a name for the device in **Device name**.</span></span>

6.  <span data-ttu-id="3ea35-118">В разделе **тип идентификатора**выберите **MAC-адрес** или **серийный номер**.</span><span class="sxs-lookup"><span data-stu-id="3ea35-118">Under **Identifier type**, click either **MAC address** or **Serial number**.</span></span>

7.  <span data-ttu-id="3ea35-119">В поле **уникальный идентификатор** введите MAC-адрес или серийный номер устройства.</span><span class="sxs-lookup"><span data-stu-id="3ea35-119">In the **Unique identifier** box, type the MAC address or serial number of the device.</span></span>

8.  <span data-ttu-id="3ea35-120">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="3ea35-120">Click **Commit**.</span></span>

</div>

<div>

## <a name="creating-test-devices-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="3ea35-121">Создание тестовых устройств с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3ea35-121">Creating Test Devices by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="3ea35-122">Тестовые устройства можно создавать с помощью Windows PowerShell и командлета New-CsTestDevice.</span><span class="sxs-lookup"><span data-stu-id="3ea35-122">Test devices can be created by using Windows PowerShell and the New-CsTestDevice cmdlet.</span></span> <span data-ttu-id="3ea35-123">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3ea35-123">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="3ea35-124">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="3ea35-124">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<span data-ttu-id="3ea35-125">При создании тестовых устройств с помощью этого командлета необходимо выполнить два действия:</span><span class="sxs-lookup"><span data-stu-id="3ea35-125">When creating test devices using this cmdlet, you must do two things:</span></span>

  - <span data-ttu-id="3ea35-126">Укажите значение MACAddress или SerialNumber в качестве IdentifierType.</span><span class="sxs-lookup"><span data-stu-id="3ea35-126">Specify either MACAddress or SerialNumber as the IdentifierType.</span></span>

  - <span data-ttu-id="3ea35-127">Включите область при указании удостоверения устройства.</span><span class="sxs-lookup"><span data-stu-id="3ea35-127">Include the scope when specifying the device Identity.</span></span> <span data-ttu-id="3ea35-128">Для создания нового устройства в глобальной области используется синтаксис, аналогичный следующему:</span><span class="sxs-lookup"><span data-stu-id="3ea35-128">To create a new device at the global scope use syntax similar to this:</span></span>
    
        -Identity "global/WindowsPhone"
    
    <span data-ttu-id="3ea35-129">Чтобы создать тестовое устройство на уровне сайта, используйте следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="3ea35-129">To create a test device at the site scope use syntax similar to this:</span></span>
    
        -Identity "site:Redmond/WindowsPhone"

<div>

## <a name="to-create-a-test-device-by-using-the-mac-address"></a><span data-ttu-id="3ea35-130">Создание тестового устройства с использованием MAC-адреса</span><span class="sxs-lookup"><span data-stu-id="3ea35-130">To create a test device by using the MAC address</span></span>

  - <span data-ttu-id="3ea35-131">Эта команда создает тестовое устройство в глобальной области и использует MAC-адрес в качестве IdentifierType:</span><span class="sxs-lookup"><span data-stu-id="3ea35-131">This command creates a test device at the global scope, and using the MAC address as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "global/WindowsPhone" -IdentifierType "MACAddress" -Identifier "01:02:03:04:05:06"

</div>

<div>

## <a name="to-create-a-test-device-by-using-the-serial-number"></a><span data-ttu-id="3ea35-132">Создание тестового устройства с использованием серийного номера</span><span class="sxs-lookup"><span data-stu-id="3ea35-132">To create a test device by using the serial number</span></span>

  - <span data-ttu-id="3ea35-133">Эта команда создает новое тестовое устройство на уровне сайта (для сайта Redmond) и использует серийный номер в качестве IdentifierType:</span><span class="sxs-lookup"><span data-stu-id="3ea35-133">This command creates a new test device at the site scope (for the Redmond site) and uses the serial number as the IdentifierType:</span></span>
    
        New-CsTestDevice -Identity "site:Redmond/WindowsPhone" -IdentifierType "SerialNumber" -Identifier "01ABC5419JKR55T"

</div>

<span data-ttu-id="3ea35-134">Для получения дополнительных сведений обратитесь к разделу "Справка" для командлета [New – CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) .</span><span class="sxs-lookup"><span data-stu-id="3ea35-134">For more information, see the help topic for the [New-CsTestDevice](https://docs.microsoft.com/powershell/module/skype/New-CsTestDevice) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

