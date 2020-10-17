---
title: 'Lync Server 2013: Просмотр сведений о профиле политики пропускной способности сети'
description: 'Lync Server 2013: Просмотр сведений о профиле политики пропускной способности сети.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network bandwidth policy profile information
ms:assetid: eed453fc-04e9-4971-959c-6fad54bf1c96
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721931(v=OCS.15)
ms:contentKeyID: 49733866
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c72a3533ae6f49f91db91b2c3b515c0b5153ec27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565405"
---
# <a name="viewing-network-bandwidth-policy-profile-information-in-lync-server-2013"></a><span data-ttu-id="d75c0-103">Просмотр сведений о профиле политики пропускной способности сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d75c0-103">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d75c0-104">_**Последнее изменение темы:** 2013-02-23_</span><span class="sxs-lookup"><span data-stu-id="d75c0-104">_**Topic Last Modified:** 2013-02-23_</span></span>

<span data-ttu-id="d75c0-105">В рамках контроля допуска звонков политика пропускной способности используется, чтобы определять ограничения пропускной способности для конкретных модальностей.</span><span class="sxs-lookup"><span data-stu-id="d75c0-105">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="d75c0-106">В Microsoft Lync Server 2013 ограничения пропускной способности могут быть назначены только для модальности аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="d75c0-106">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="d75c0-107">Вы можете задать общие ограничения и ограничения сеанса.</span><span class="sxs-lookup"><span data-stu-id="d75c0-107">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="d75c0-108">Вы можете использовать панель управления Lync Server для создания, изменения или удаления профиля контейнера для этих политик.</span><span class="sxs-lookup"><span data-stu-id="d75c0-108">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="d75c0-109">Каждый профиль политики полосы пропускания можно связать с одним или несколькими сетевыми узлами.</span><span class="sxs-lookup"><span data-stu-id="d75c0-109">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="d75c0-110">Используйте следующие процедуры для просмотра профиля политики полосы пропускания .</span><span class="sxs-lookup"><span data-stu-id="d75c0-110">Use the following procedures to view a bandwidth policy profile.</span></span> <span data-ttu-id="d75c0-111">Чтобы создать или изменить профиль политики пропускной способности, ознакомьтесь со статьей [Создание или изменение профилей политики пропускной способности в Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d75c0-111">To create or modify a bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="d75c0-112">Просмотр профиля политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="d75c0-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="d75c0-113">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="d75c0-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d75c0-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d75c0-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d75c0-115">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d75c0-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d75c0-116">На панели навигации слева выберите пункт **Конфигурация сети** и щелкните \*\*Политика полосы пропускания \*\*.</span><span class="sxs-lookup"><span data-stu-id="d75c0-116">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="d75c0-117">На странице **политика пропускной способности** щелкните профиль политики пропускной способности, который требуется просмотреть.</span><span class="sxs-lookup"><span data-stu-id="d75c0-117">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="d75c0-118">В меню **Edit** (Правка) щелкните пункт  **Show details** (Показать подробности).</span><span class="sxs-lookup"><span data-stu-id="d75c0-118">On the **Edit** menu, click **Show details**.</span></span>

</div>

<div>

## <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="d75c0-119">Просмотр сведений о профиле политики пропускной способности сети с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="d75c0-119">Viewing Network Bandwidth Policy Profile Information by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="d75c0-120">Профили пропускной способности сети можно просматривать с помощью Windows PowerShell и командлета Get-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="d75c0-120">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="d75c0-121">Этот командлет можно запустить либо из командной консоли Lync Server 2013, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d75c0-121">This cmdlet can be run either from the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="d75c0-122">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="d75c0-122">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>

## <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="d75c0-123">Просмотр сведений о профиле политики пропускной способности сети</span><span class="sxs-lookup"><span data-stu-id="d75c0-123">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="d75c0-124">Чтобы просмотреть сведения обо всех профилях политики пропускной способности сети, введите следующую команду в командной консоли Lync Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="d75c0-124">To view information about all your network bandwidth policy profiles, type the following command in the Lync Server Management Shell and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="d75c0-125">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="d75c0-125">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :

</div>

<span data-ttu-id="d75c0-126">Дополнительные сведения см. в разделе справки о командлете [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="d75c0-126">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d75c0-127">См. также</span><span class="sxs-lookup"><span data-stu-id="d75c0-127">See Also</span></span>


[<span data-ttu-id="d75c0-128">Создание или изменение профилей политики пропускной способности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d75c0-128">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="d75c0-129">Удаление профилей политики пропускной способности сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d75c0-129">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="d75c0-130">Настройка контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d75c0-130">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

