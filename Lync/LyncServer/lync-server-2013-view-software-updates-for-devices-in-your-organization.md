---
title: 'Lync Server 2013: Просмотр обновлений программного обеспечения для устройств в Организации'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View software updates for devices in your organization
ms:assetid: d2cca12b-ed43-4e1f-90ab-d14bca8b482c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182592(v=OCS.15)
ms:contentKeyID: 48185418
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3141f08e7973b123b8c8ee0fe9b9c3c93c8e752
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48518406"
---
# <a name="view-software-updates-for-devices-in-lync-server-2013"></a><span data-ttu-id="4bdf1-102">Просмотр обновлений программного обеспечения для устройств в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bdf1-102">View software updates for devices in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4bdf1-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4bdf1-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4bdf1-104">С помощью Lync Server 2013 вы можете просматривать обновления программного обеспечения для устройств организации и управлять ими с помощью веб-службы обновления устройств.</span><span class="sxs-lookup"><span data-stu-id="4bdf1-104">With Lync Server 2013, you use Device Update Web service to view and manage software updates for your organization’s devices.</span></span> <span data-ttu-id="4bdf1-105">Эти обновления доступны в САВ-файлах на веб-сайте службы поддержки Майкрософт по адресу [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) .</span><span class="sxs-lookup"><span data-stu-id="4bdf1-105">These updates are available in .cab (cabinet) files from the Microsoft Support website at [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091).</span></span> <span data-ttu-id="4bdf1-106">После загрузки CAB-файла выполните командлет **Import-CSDeviceUpdate** , чтобы импортировать правила обновления устройств из CAB-файла.</span><span class="sxs-lookup"><span data-stu-id="4bdf1-106">After you download the .cab file, run the **Import-CSDeviceUpdate** cmdlet to import the device update rules from the .cab file.</span></span> <span data-ttu-id="4bdf1-107">Подробные сведения о командлете **Import – CSDeviceUpdate** можно найти в статье [Import – CSDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) в документации по консоли управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bdf1-107">For details about the **Import-CSDeviceUpdate** cmdlet, see [Import-CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/Import-CsDeviceUpdate) in the Lync Server Management Shell documentation.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="4bdf1-108">Перед развертыванием нового обновления в организации проверьте, что оно работает правильно на тестовом устройстве.</span><span class="sxs-lookup"><span data-stu-id="4bdf1-108">Before deploying a new update to your organization, verify that it functions correctly on a test device.</span></span>



</div>

<div>

## <a name="to-view-software-updates-for-uc-devices"></a><span data-ttu-id="4bdf1-109">Просмотр обновлений ПО для устройств объединенных коммуникаций</span><span class="sxs-lookup"><span data-stu-id="4bdf1-109">To view software updates for UC devices</span></span>

1.  <span data-ttu-id="4bdf1-110">Войдите на любой компьютер во внутреннем развертывании с использованием учетной записи пользователя, назначенной роли CsUserAdministrator или CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="4bdf1-110">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4bdf1-111">На веб-сайте службы поддержки корпорации Майкрософт по адресу [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091) Скачайте CAB-файл в папку на компьютере с Lync Server 2013 (например, C: \\ updates \\UCUpdates.cab).</span><span class="sxs-lookup"><span data-stu-id="4bdf1-111">From the Microsoft Support website at [https://go.microsoft.com/fwlink/p/?linkId=204091](https://go.microsoft.com/fwlink/p/?linkid=204091), download the .cab file to a location on a Lync Server 2013 computer (for example, C:\\Updates\\UCUpdates.cab).</span></span>

3.  <span data-ttu-id="4bdf1-112">Импортируйте правила обновления устройств из файла C: \\ updates \\UCUpdates.cab, выполнив один из следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="4bdf1-112">Import the device update rules from the C:\\Updates\\UCUpdates.cab file by running one of the following cmdlets:</span></span>
    
      - <span data-ttu-id="4bdf1-113">Если CAB-файл расположен на том же компьютере, на котором работает обновляемая служба (service:Redmond-websvc-2), запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="4bdf1-113">If the .cab file is located on the same computer as the one running the service to be updated (service:Redmond-websvc-2), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-2 -FileName C:\Updates\UCUpdates.cab
    
      - <span data-ttu-id="4bdf1-114">Если CAB-файл расположен на другом компьютере, на котором не работает обновляемая служба (service:Redmond-websvc-3), запустите следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="4bdf1-114">If the .cab file is located on a different computer than the one running the service to be updated (service:Redmond-websvc-3), run the following cmdlet:</span></span>
        
            Import-CsDeviceUpdate -Identity service:Redmond-websvc-3 -ByteInput C:\Updates\UCUpdates.cab

4.  <span data-ttu-id="4bdf1-115">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4bdf1-115">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4bdf1-116">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4bdf1-116">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

5.  <span data-ttu-id="4bdf1-117">В левой панели навигации щелкните элемент **Клиенты**, а затем элемент **Обновление устройств**.</span><span class="sxs-lookup"><span data-stu-id="4bdf1-117">In the left navigation bar, click **Clients**, and then click **Device Update**.</span></span>

6.  <span data-ttu-id="4bdf1-118">На странице **Обновление устройств** щелкните обновление в списке, а затем выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="4bdf1-118">On the **Device Update** page, click an update in the list, and then do one of the following:</span></span>
    
      - <span data-ttu-id="4bdf1-p103">**Отмена отложенного обновления.** Чтобы запретить развертывание выбранного обновления на устройства организации, откройте меню **Действие** и выберите команду **Отменить отложенные обновления**.</span><span class="sxs-lookup"><span data-stu-id="4bdf1-p103">**Cancel a pending update.** To prevent the selected update from being deployed to your organization’s devices, click the **Action** menu, and then click **Cancel pending updates**.</span></span>
    
      - <span data-ttu-id="4bdf1-p104">**Утверждение обновления.** Чтобы разрешить развертывание выбранного обновления на устройства организации, откройте меню **Действие** и выберите команду **Утвердить**.</span><span class="sxs-lookup"><span data-stu-id="4bdf1-p104">**Approve an update.** To allow the selected update to be deployed to your organization’s devices, click the **Action** menu, and then click **Approve**.</span></span>
    
      - <span data-ttu-id="4bdf1-p105">**Восстановление обновления.** Чтобы разрешить развертывание на устройства организации ранее утвержденного обновления, откройте меню **Действие** и выберите команду **Восстановить**.</span><span class="sxs-lookup"><span data-stu-id="4bdf1-p105">**Restore an update.** To allow a previously approved update to be deployed to your organization’s devices, click the **Action** menu, and then click **Restore**.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4bdf1-125">См. также</span><span class="sxs-lookup"><span data-stu-id="4bdf1-125">See Also</span></span>


[<span data-ttu-id="4bdf1-126">Управление устройствами, телефонами и клиентскими приложениями в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4bdf1-126">Managing devices, phones, and client applications in Lync Server 2013</span></span>](lync-server-2013-managing-devices-phones-and-client-applications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

