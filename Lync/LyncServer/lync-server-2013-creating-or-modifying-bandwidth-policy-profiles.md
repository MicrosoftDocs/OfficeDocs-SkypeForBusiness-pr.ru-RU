---
title: 'Lync Server 2013: создание или изменение профилей политики пропускной способности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying bandwidth policy profiles
ms:assetid: 08a2e18f-9b0d-4a2f-aa14-13bbf79ec745
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520945(v=OCS.15)
ms:contentKeyID: 48183336
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e884a564859396dab19ad8b18c6cf33a54a626e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048620"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="809fb-102">Создание или изменение профилей политики пропускной способности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="809fb-102">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="809fb-103">_**Последнее изменение темы:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="809fb-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="809fb-104">В рамках контроля допуска звонков политика пропускной способности используется, чтобы определять ограничения пропускной способности для конкретных модальностей.</span><span class="sxs-lookup"><span data-stu-id="809fb-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="809fb-105">В Microsoft Lync Server 2013 ограничения пропускной способности могут быть назначены только для модальности аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="809fb-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="809fb-106">Вы можете задать общие ограничения и ограничения сеанса.</span><span class="sxs-lookup"><span data-stu-id="809fb-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="809fb-107">Вы можете использовать панель управления Lync Server для создания, изменения или удаления профиля контейнера для этих политик.</span><span class="sxs-lookup"><span data-stu-id="809fb-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="809fb-108">Каждый профиль политики полосы пропускания можно связать с одним или несколькими сетевыми узлами.</span><span class="sxs-lookup"><span data-stu-id="809fb-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="809fb-109">Используйте следующие процедуры для создания или изменения профиля политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="809fb-109">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="809fb-110">Чтобы удалить профиль политики пропускной способности, ознакомьтесь со статьей [Удаление профилей политики пропускной способности сети в Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="809fb-110">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="809fb-111">Создание профиля политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="809fb-111">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="809fb-112">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="809fb-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="809fb-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="809fb-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="809fb-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="809fb-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="809fb-115">На панели навигации слева выберите пункт **Конфигурация сети** и щелкните \*\*Политика полосы пропускания \*\*.</span><span class="sxs-lookup"><span data-stu-id="809fb-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="809fb-116">На странице **политика пропускной способности** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="809fb-116">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="809fb-117">В разделе **Создание профиля политики пропускной способности**введите имя в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="809fb-117">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="809fb-118">Это имя должно быть уникальным среди всех профилей политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="809fb-118">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="809fb-119">В поле **предельное число звуков** введите числовое значение.</span><span class="sxs-lookup"><span data-stu-id="809fb-119">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="809fb-120">Это значение — максимальный объем пропускной способности, выделяемой для всех звуковых подключений, выраженный в кбит/с.</span><span class="sxs-lookup"><span data-stu-id="809fb-120">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="809fb-121">Введите числовое значение в поле **предельное число сеансов голосовой связи** .</span><span class="sxs-lookup"><span data-stu-id="809fb-121">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="809fb-122">Это значение является максимальным объемом полосы пропускания, выделенной для отдельного подключения к аудио, выраженной в кбит/с.</span><span class="sxs-lookup"><span data-stu-id="809fb-122">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="809fb-123">Это значение должно быть 40 или выше.</span><span class="sxs-lookup"><span data-stu-id="809fb-123">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="809fb-124">Введите числовое значение в поле **Максимальное количество видеоролика** .</span><span class="sxs-lookup"><span data-stu-id="809fb-124">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="809fb-125">Это значение — максимальный объем пропускной способности, выделяемой для всех видеоподключений, выраженный в кбит/с.</span><span class="sxs-lookup"><span data-stu-id="809fb-125">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="809fb-126">Введите числовое значение в поле **предельное число сеансов видео** .</span><span class="sxs-lookup"><span data-stu-id="809fb-126">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="809fb-127">Это значение — максимальный объем пропускной способности, выделяемой для отдельного видеоподключения, выраженный в кбит/с.</span><span class="sxs-lookup"><span data-stu-id="809fb-127">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="809fb-128">Это значение должно быть 100 или выше.</span><span class="sxs-lookup"><span data-stu-id="809fb-128">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="809fb-129">Необязательно Введите значение в поле **Описание** , чтобы получить дополнительные сведения о профиле политики пропускной способности, которые не могут быть выражены только по имени.</span><span class="sxs-lookup"><span data-stu-id="809fb-129">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="809fb-130">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="809fb-130">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="809fb-131">Создание профиля политики пропускной способности не приводит к автоматическому наложению ограничений пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="809fb-131">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="809fb-132">Сначала необходимо связать профиль политики с сайтом.</span><span class="sxs-lookup"><span data-stu-id="809fb-132">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="809fb-133">Сведения о том, как связать профиль политики с сайтом, можно найти <A href="lync-server-2013-creating-or-modifying-network-sites.md">в статье Создание или изменение сетевых сайтов в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="809fb-133">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="809fb-134">Изменение профиля политики полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="809fb-134">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="809fb-135">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="809fb-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="809fb-136">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="809fb-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="809fb-137">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="809fb-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="809fb-138">На панели навигации слева выберите пункт **Конфигурация сети** и щелкните \*\*Политика полосы пропускания \*\*.</span><span class="sxs-lookup"><span data-stu-id="809fb-138">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="809fb-139">На странице **Политика полосы пропускания** щелкните профиль политики полосы пропускания, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="809fb-139">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="809fb-140">В меню **Правка** щелкните пункт  **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="809fb-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="809fb-141">На странице " **изменение профиля политики пропускной способности** " при необходимости измените поля (Дополнительные сведения см. в разделе "Создание профиля политики пропускной способности" в этой статье).</span><span class="sxs-lookup"><span data-stu-id="809fb-141">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="809fb-142">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="809fb-142">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="809fb-143">При изменении профиля политики пропускной способности он незамедлительно обновляет ограничения пропускной способности всех сетевых сайтов, связанных с этим профилем политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="809fb-143">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="809fb-144">См. также</span><span class="sxs-lookup"><span data-stu-id="809fb-144">See Also</span></span>


[<span data-ttu-id="809fb-145">Удаление профилей политики пропускной способности сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="809fb-145">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="809fb-146">Настройка контроля допуска звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="809fb-146">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="809fb-147">New — CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="809fb-147">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="809fb-148">Set — CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="809fb-148">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="809fb-149">Get — CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="809fb-149">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

