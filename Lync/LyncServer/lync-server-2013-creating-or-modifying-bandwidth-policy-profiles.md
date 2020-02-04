---
title: 'Lync Server 2013: создание и изменение профилей политики пропускной способности'
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
ms.openlocfilehash: 06019464d6d37c601c9077d36c81976d43b6e37c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41733689"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="f5590-102">Создание и изменение профилей политики пропускной способности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5590-102">Creating or modifying bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f5590-103">_**Тема последнего изменения:** 2012-10-15_</span><span class="sxs-lookup"><span data-stu-id="f5590-103">_**Topic Last Modified:** 2012-10-15_</span></span>

<span data-ttu-id="f5590-104">В рамках управления допуском звонков (CAC) для определения ограничений пропускной способности для некоторых модальностей используется политика пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="f5590-104">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="f5590-105">В Microsoft Lync Server 2013 можно назначать ограничения пропускной способности только для модальностей аудио и видео.</span><span class="sxs-lookup"><span data-stu-id="f5590-105">In Microsoft Lync Server 2013, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="f5590-106">Вы можете настроить общие ограничения пропускной способности и ограничения сеанса.</span><span class="sxs-lookup"><span data-stu-id="f5590-106">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="f5590-107">С помощью панели управления Lync Server вы можете создавать, изменять и удалять профили контейнеров для этих политик.</span><span class="sxs-lookup"><span data-stu-id="f5590-107">You can use the Lync Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="f5590-108">Каждый профиль политики пропускной способности может быть связан с одним или несколькими сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="f5590-108">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="f5590-109">Чтобы создать или изменить профиль политики пропускной способности, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f5590-109">Use the following procedures to create or modify a bandwidth policy profile.</span></span> <span data-ttu-id="f5590-110">Чтобы удалить профиль политики пропускной способности, ознакомьтесь со сведениями [Удаление профилей политики пропускной способности сети в Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span><span class="sxs-lookup"><span data-stu-id="f5590-110">To delete a bandwidth policy profile, see [Deleting network bandwidth policy profiles in Lync Server 2013](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)</span></span>

<div>

## <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="f5590-111">Создание нового профиля политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="f5590-111">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="f5590-112">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f5590-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f5590-113">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5590-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f5590-114">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f5590-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f5590-115">На панели навигации слева выберите пункт **Настройка сети** , а затем — **политика пропускной способности**.</span><span class="sxs-lookup"><span data-stu-id="f5590-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="f5590-116">На странице **политики пропускной способности** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="f5590-116">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="f5590-117">В окне **новый профиль политики пропускной способности**введите имя в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="f5590-117">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="f5590-118">Это имя должно быть уникальным среди всех профилей политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="f5590-118">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="f5590-119">В поле **предельное число звуков** введите числовое значение.</span><span class="sxs-lookup"><span data-stu-id="f5590-119">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="f5590-120">Это значение — это максимальный объем пропускной способности, выделяемый для всех звуковых подключений, выраженный в кбит/с.</span><span class="sxs-lookup"><span data-stu-id="f5590-120">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="f5590-121">Введите числовое значение в поле " **Ограничение сеанса голосовой связи** ".</span><span class="sxs-lookup"><span data-stu-id="f5590-121">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="f5590-122">Это значение — это максимальный объем пропускной способности, выделяемый для отдельного звукового подключения, выраженный в кбит/с.</span><span class="sxs-lookup"><span data-stu-id="f5590-122">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="f5590-123">Это значение должно быть 40 или выше.</span><span class="sxs-lookup"><span data-stu-id="f5590-123">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="f5590-124">Введите числовое значение в поле " **предельный размер видео** ".</span><span class="sxs-lookup"><span data-stu-id="f5590-124">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="f5590-125">Это значение — это максимальный объем пропускной способности, выделяемый для всех видеоподключений, выраженный в кбит/с.</span><span class="sxs-lookup"><span data-stu-id="f5590-125">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="f5590-126">Введите числовое значение в поле " **Ограничение сеанса видео** ".</span><span class="sxs-lookup"><span data-stu-id="f5590-126">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="f5590-127">Это значение — это максимальный объем пропускной способности, выделяемый для отдельного видеосоединения, выраженный в КБ/с.</span><span class="sxs-lookup"><span data-stu-id="f5590-127">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="f5590-128">Это значение должно быть 100 или выше.</span><span class="sxs-lookup"><span data-stu-id="f5590-128">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="f5590-129">Необязательно Введите значение в поле **Описание** , чтобы получить дополнительные сведения об этом профиле политики пропускной способности, которое не может быть выражено только именем.</span><span class="sxs-lookup"><span data-stu-id="f5590-129">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="f5590-130">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="f5590-130">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5590-131">Создание профиля политики пропускной способности не приводит к автоматическому применению ограничений для пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="f5590-131">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="f5590-132">Сначала необходимо связать профиль политики с сайтом.</span><span class="sxs-lookup"><span data-stu-id="f5590-132">You must first associate the policy profile with a site.</span></span> <span data-ttu-id="f5590-133">Сведения о том, как связать профиль политики с сайтом, можно найти <A href="lync-server-2013-creating-or-modifying-network-sites.md">в разделе Создание или изменение сетевых сайтов в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="f5590-133">For details about how to associate a policy profile with a site, see <A href="lync-server-2013-creating-or-modifying-network-sites.md">Creating or modifying network sites in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="f5590-134">Изменение профиля политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="f5590-134">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="f5590-135">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="f5590-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="f5590-136">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f5590-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f5590-137">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f5590-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="f5590-138">На панели навигации слева выберите пункт **Настройка сети** , а затем — **политика пропускной способности**.</span><span class="sxs-lookup"><span data-stu-id="f5590-138">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="f5590-139">На странице **политики пропускной способности** выберите профиль политики пропускной способности, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="f5590-139">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="f5590-140">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="f5590-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="f5590-141">На странице **профиля политики изменения пропускной способности** измените соответствующие поля (Дополнительные сведения можно найти в разделе "Создание профиля политики пропускной способности" в этой статье выше).</span><span class="sxs-lookup"><span data-stu-id="f5590-141">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see the "To create a bandwidth policy profile" section earlier in this topic).</span></span>

7.  <span data-ttu-id="f5590-142">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="f5590-142">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f5590-143">При изменении профиля политики пропускной способности немедленно обновляются ограничения пропускной способности всех сайтов сети, связанных с этим профилем политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="f5590-143">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f5590-144">См. также</span><span class="sxs-lookup"><span data-stu-id="f5590-144">See Also</span></span>


[<span data-ttu-id="f5590-145">Удаление профилей политики пропускной способности сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5590-145">Deleting network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-deleting-network-bandwidth-policy-profiles.md)  


[<span data-ttu-id="f5590-146">Настройка управления допуском звонков в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f5590-146">Configure call admission control in Lync Server 2013</span></span>](lync-server-2013-configure-call-admission-control.md)  
[<span data-ttu-id="f5590-147">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f5590-147">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="f5590-148">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f5590-148">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  
[<span data-ttu-id="f5590-149">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f5590-149">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

