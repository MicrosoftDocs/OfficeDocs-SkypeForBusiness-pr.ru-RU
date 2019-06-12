---
title: 'Lync Server 2013: Просмотр обновлений программного обеспечения для устройств в вашей организации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 06700e198dcd1923e875401b4539a0af84417c44
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34849145"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-software-updates-for-devices-in-lync-server-2013"></a><span data-ttu-id="36fd3-102">Просмотр обновлений программного обеспечения для устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36fd3-102">View software updates for devices in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="36fd3-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="36fd3-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="36fd3-104">В Lync Server 2013 вы используете веб-службу обновления устройств для просмотра обновлений программного обеспечения для устройств организации и управления ими.</span><span class="sxs-lookup"><span data-stu-id="36fd3-104">With Lync Server 2013, you use Device Update Web service to view and manage software updates for your organization’s devices.</span></span> <span data-ttu-id="36fd3-105">Эти обновления доступны на веб-сайте службы поддержки Майкрософт по адресу [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)CAB (CAB-файлов).</span><span class="sxs-lookup"><span data-stu-id="36fd3-105">These updates are available in .cab (cabinet) files from the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091).</span></span> <span data-ttu-id="36fd3-106">Загрузив CAB-файл, выполните командлет **Import — ксдевицеупдате** , чтобы импортировать правила обновления устройства из файла CAB.</span><span class="sxs-lookup"><span data-stu-id="36fd3-106">After you download the .cab file, run the **Import-CSDeviceUpdate** cmdlet to import the device update rules from the .cab file.</span></span> <span data-ttu-id="36fd3-107">Дополнительные сведения о командлете **Import-ксдевицеупдате** можно найти в документации [Import-Ксдевицеупдате](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) в командной консоли Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="36fd3-107">For details about the **Import-CSDeviceUpdate** cmdlet, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="36fd3-108">Перед развертыванием нового обновления в вашей организации убедитесь, что оно правильно работает на тестовом устройстве.</span><span class="sxs-lookup"><span data-stu-id="36fd3-108">Before deploying a new update to your organization, verify that it functions correctly on a test device.</span></span>



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a><span data-ttu-id="36fd3-109">Просмотр обновлений программного обеспечения для устройств UC</span><span class="sxs-lookup"><span data-stu-id="36fd3-109">To view software updates for UC devices</span></span>

1.  <span data-ttu-id="36fd3-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="36fd3-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="36fd3-111">Скачайте CAB-файл в папку [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091)на компьютере Lync Server 2013 (например, C:\\Updates\\. cab) на сайте службы поддержки Майкрософт по адресу.</span><span class="sxs-lookup"><span data-stu-id="36fd3-111">From the Microsoft Support website at [http://go.microsoft.com/fwlink/p/?linkId=204091](http://go.microsoft.com/fwlink/p/?linkid=204091), download the .cab file to a location on a Lync Server 2013 computer (for example, C:\\Updates\\UCUpdates.cab).</span></span>

3.  <span data-ttu-id="36fd3-112">Импортируйте правила обновления устройства из файла C:\\Updates\\укупдатес. cab, выполнив один из следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="36fd3-112">Import the device update rules from the C:\\Updates\\UCUpdates.cab file by running one of the following cmdlets:</span></span>
    
      - <span data-ttu-id="36fd3-113">Если CAB-файл находится на том же компьютере, что и служба, для которой выполняется обновление (Service: Redmond-вебсвк-2), выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="36fd3-113">If the .cab file is located on the same computer as the one running the service to be updated (service:Redmond-websvc-2), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - <span data-ttu-id="36fd3-114">Если CAB-файл находится на компьютере, отличном от того, на котором запущена служба (Service: Redmond-вебсвк-3), выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="36fd3-114">If the .cab file is located on a different computer than the one running the service to be updated (service:Redmond-websvc-3), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  <span data-ttu-id="36fd3-115">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="36fd3-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="36fd3-116">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="36fd3-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

5.  <span data-ttu-id="36fd3-117">На панели навигации слева выберите пункт **Клиенты**, а затем — **обновление устройства**.</span><span class="sxs-lookup"><span data-stu-id="36fd3-117">In the left navigation bar, click **Clients**, and then click **Device Update**.</span></span>

6.  <span data-ttu-id="36fd3-118">На странице **обновление устройства** выберите обновление в списке, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="36fd3-118">On the **Device Update** page, click an update in the list, and then do one of the following:</span></span>
    
      - <span data-ttu-id="36fd3-119">**Отмена ожидающего обновления.**</span><span class="sxs-lookup"><span data-stu-id="36fd3-119">**Cancel a pending update.**</span></span> <span data-ttu-id="36fd3-120">Чтобы запретить развертывание выбранного обновления на устройствах вашей организации, откройте меню **действия** и выберите пункт **отменить ожидающие обновления**.</span><span class="sxs-lookup"><span data-stu-id="36fd3-120">To prevent the selected update from being deployed to your organization’s devices, click the **Action** menu, and then click **Cancel pending updates**.</span></span>
    
      - <span data-ttu-id="36fd3-121">**Утверждение обновления.**</span><span class="sxs-lookup"><span data-stu-id="36fd3-121">**Approve an update.**</span></span> <span data-ttu-id="36fd3-122">Чтобы разрешить развертывание выбранного обновления на устройствах своей организации, откройте меню **действия** и выберите пункт **утвердить**.</span><span class="sxs-lookup"><span data-stu-id="36fd3-122">To allow the selected update to be deployed to your organization’s devices, click the **Action** menu, and then click **Approve**.</span></span>
    
      - <span data-ttu-id="36fd3-123">**Восстановите обновление.**</span><span class="sxs-lookup"><span data-stu-id="36fd3-123">**Restore an update.**</span></span> <span data-ttu-id="36fd3-124">Чтобы разрешить развертывание ранее одобренных обновлений на устройствах своей организации, откройте меню **действия** и выберите команду **восстановить**.</span><span class="sxs-lookup"><span data-stu-id="36fd3-124">To allow a previously approved update to be deployed to your organization’s devices, click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="36fd3-125">См. также</span><span class="sxs-lookup"><span data-stu-id="36fd3-125">See Also</span></span>


[<span data-ttu-id="36fd3-126">Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="36fd3-126">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

