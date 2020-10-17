---
title: 'Lync Server 2013: удаление профилей политики пропускной способности сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting network bandwidth policy profiles
ms:assetid: 4d6beda8-6aa5-4d5e-8a07-363598f0e0c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688050(v=OCS.15)
ms:contentKeyID: 49733643
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f6f43f8c6aae2dec5ea55463c1896f327f008980
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48525356"
---
# <a name="deleting-network-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="4f073-102">Удаление профилей политики пропускной способности сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f073-102">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4f073-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="4f073-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="4f073-104">В рамках контроля допуска звонков политика пропускной способности используется, чтобы определять ограничения пропускной способности для конкретных модальностей.</span><span class="sxs-lookup"><span data-stu-id="4f073-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="4f073-105">В Microsoft Lync Server 2013 ограничения пропускной способности могут быть назначены только для модальности аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="4f073-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="4f073-106">Вы можете задать общие ограничения и ограничения сеанса.</span><span class="sxs-lookup"><span data-stu-id="4f073-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="4f073-107">Вы можете использовать панель управления Lync Server для создания, изменения или удаления профиля контейнера для этих политик.</span><span class="sxs-lookup"><span data-stu-id="4f073-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="4f073-108">Используйте следующие процедуры для удаления профилей политик пропускной способности сети.</span><span class="sxs-lookup"><span data-stu-id="4f073-108">Use the following procedures to delete a network bandwidth policy profiles.</span></span> <span data-ttu-id="4f073-109">Подробнее о создании или изменении профиля политики пропускной способности сети можно узнать [в статье Создание или изменение профилей политики пропускной способности в Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="4f073-109">For details on creating or modifying a network bandwidth policy profile, see [Creating or modifying bandwidth policy profiles in Lync Server 2013](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md).</span></span>

<div>

## <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="4f073-110">Чтобы удалить профиль политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="4f073-110">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="4f073-111">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="4f073-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4f073-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4f073-112">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4f073-113">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4f073-113">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="4f073-114">На левой панели навигации щелкните **Конфигурация сети**, затем щелкните **Политика пропускной способности**.</span><span class="sxs-lookup"><span data-stu-id="4f073-114">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="4f073-115">На странице **Политика пропускной способности** щелкните профиль политики пропускной способности, который следует удалить.</span><span class="sxs-lookup"><span data-stu-id="4f073-115">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4f073-p103">Одновременно можно удалить сразу несколько профилей. Для этого нажмите и удерживайте клавишу CTRL, одновременно выбирая несколько профилей. Или щелкните пункт <STRONG>Выделить все</STRONG> в меню <STRONG>Изменить</STRONG> для выбора сразу нескольких профилей.</span><span class="sxs-lookup"><span data-stu-id="4f073-p103">You can delete more than one profile at a time. To do this, press CTRL and select multiple profiles while holding down the CTRL key. Or, to select all profiles, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="4f073-119">В меню **Изменить** щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="4f073-119">On the **Edit** menu, click **Delete**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="4f073-120">Невозможно удалить профили политики пропускной способности, связанные с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="4f073-120">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="4f073-121">Сначала следует удалить связь с сетевым сайтом, а затем удалить профиль.</span><span class="sxs-lookup"><span data-stu-id="4f073-121">You must first remove the association with the network site before you can delete the profile.</span></span> <span data-ttu-id="4f073-122">Сведения о том, как изменить сетевой сайт, можно найти <A href="lync-server-2013-creating-or-modifying-network-sites.md">в статье Создание или изменение сетевых сайтов в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4f073-122">For details about how to modify the network site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4f073-123">См. также</span><span class="sxs-lookup"><span data-stu-id="4f073-123">See Also</span></span>


[<span data-ttu-id="4f073-124">Создание или изменение профилей политики пропускной способности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f073-124">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md)  
[<span data-ttu-id="4f073-125">Просмотр сведений о профиле политики пропускной способности сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f073-125">Viewing network bandwidth policy profile information in Lync Server 2013</span></span>](lync-server-2013-viewing-network-bandwidth-policy-profile-information.md)  


[<span data-ttu-id="4f073-126">Настройка контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4f073-126">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="4f073-127">Remove — CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="4f073-127">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

