---
title: Управление профилями политики пропускной способности сети
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: В этой статье описаны процедуры, которые можно использовать для просмотра, создания, изменения и удаления профилей политики пропускной способности сети.
ms.openlocfilehash: 3b2b62e5e823a9d86f1884d79b67483bce38a39f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279524"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="2f419-103">Управление профилями политики пропускной способности сети в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2f419-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="2f419-104">В этой статье описаны процедуры, которые можно использовать для просмотра, создания, изменения и удаления профилей политики пропускной способности сети.</span><span class="sxs-lookup"><span data-stu-id="2f419-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="2f419-105">Просмотр данных профиля политики пропускной способности сети</span><span class="sxs-lookup"><span data-stu-id="2f419-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="2f419-106">В рамках управления допуском звонков (CAC) для определения ограничений пропускной способности для некоторых модальностей используется политика пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="2f419-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="2f419-107">В Skype для бизнеса Server можно назначать ограничения пропускной способности только для звуковых и видеомодальностей.</span><span class="sxs-lookup"><span data-stu-id="2f419-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="2f419-108">Вы можете настроить общие ограничения пропускной способности и ограничения сеанса.</span><span class="sxs-lookup"><span data-stu-id="2f419-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="2f419-109">С помощью панели управления "Skype для бизнеса" можно создавать, изменять и удалять профили контейнеров для этих политик.</span><span class="sxs-lookup"><span data-stu-id="2f419-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="2f419-110">Каждый профиль политики пропускной способности может быть связан с одним или несколькими сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="2f419-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="2f419-111">Чтобы просмотреть профиль политики пропускной способности, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2f419-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="2f419-112">Просмотр профиля политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="2f419-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="2f419-113">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2f419-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2f419-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2f419-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2f419-115">На панели навигации слева выберите пункт **Настройка сети** , а затем — **политика пропускной способности**.</span><span class="sxs-lookup"><span data-stu-id="2f419-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="2f419-116">На странице **политики пропускной способности** выберите профиль политики пропускной способности, который вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="2f419-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="2f419-117">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="2f419-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="2f419-118">Просмотр данных профиля политики пропускной способности сети с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2f419-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="2f419-119">Профили пропускной способности сети можно просматривать с помощью Windows PowerShell и командлета Get-Кснетворкбандвидсполиципрофиле.</span><span class="sxs-lookup"><span data-stu-id="2f419-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="2f419-120">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2f419-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="2f419-121">Просмотр данных профиля политики пропускной способности сети</span><span class="sxs-lookup"><span data-stu-id="2f419-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="2f419-122">Чтобы просмотреть сведения о всех профилях политики пропускной способности сети, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="2f419-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="2f419-123">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="2f419-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="2f419-124">Дополнительные сведения можно найти в разделе справки по командлету [Get-кснетворкбандвидсполиципрофиле](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .</span><span class="sxs-lookup"><span data-stu-id="2f419-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="2f419-125">Создание и изменение профилей политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="2f419-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="2f419-126">В рамках управления допуском звонков (CAC) для определения ограничений пропускной способности для некоторых модальностей используется политика пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="2f419-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="2f419-127">В Skype для бизнеса Server можно назначать ограничения пропускной способности только для звуковых и видеомодальностей.</span><span class="sxs-lookup"><span data-stu-id="2f419-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="2f419-128">Вы можете настроить общие ограничения пропускной способности и ограничения сеанса.</span><span class="sxs-lookup"><span data-stu-id="2f419-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="2f419-129">С помощью панели управления "Skype для бизнеса" можно создавать, изменять и удалять профили контейнеров для этих политик.</span><span class="sxs-lookup"><span data-stu-id="2f419-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="2f419-130">Каждый профиль политики пропускной способности может быть связан с одним или несколькими сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="2f419-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="2f419-131">Чтобы создать или изменить профиль политики пропускной способности, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2f419-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="2f419-132">Создание нового профиля политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="2f419-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="2f419-133">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2f419-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2f419-134">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2f419-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2f419-135">На панели навигации слева выберите пункт **Настройка сети**, а затем — **политика пропускной способности**.</span><span class="sxs-lookup"><span data-stu-id="2f419-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="2f419-136">На странице **политики пропускной способности** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="2f419-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="2f419-137">В окне **новый профиль политики пропускной способности**введите имя в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="2f419-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="2f419-138">Это имя должно быть уникальным среди всех профилей политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="2f419-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="2f419-139">В поле **предельное число звуков** введите числовое значение.</span><span class="sxs-lookup"><span data-stu-id="2f419-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="2f419-140">Это значение — это максимальный объем пропускной способности, выделяемый для всех звуковых подключений, выраженный в кбит/с.</span><span class="sxs-lookup"><span data-stu-id="2f419-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="2f419-141">Введите числовое значение в поле " **Ограничение сеанса голосовой связи** ".</span><span class="sxs-lookup"><span data-stu-id="2f419-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="2f419-142">Это значение — это максимальный объем пропускной способности, выделяемый для отдельного звукового подключения, выраженный в кбит/с.</span><span class="sxs-lookup"><span data-stu-id="2f419-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="2f419-143">Это значение должно быть 40 или выше.</span><span class="sxs-lookup"><span data-stu-id="2f419-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="2f419-144">Введите числовое значение в поле "предельный **Размер видео** ".</span><span class="sxs-lookup"><span data-stu-id="2f419-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="2f419-145">Это значение — это максимальный объем пропускной способности, выделяемый для всех видеоподключений, выраженный в кбит/с.</span><span class="sxs-lookup"><span data-stu-id="2f419-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="2f419-146">Введите числовое значение в поле " **Ограничение сеанса видео** ".</span><span class="sxs-lookup"><span data-stu-id="2f419-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="2f419-147">Это значение — это максимальный объем пропускной способности, выделяемый для отдельного видеосоединения, выраженный в КБ/с.</span><span class="sxs-lookup"><span data-stu-id="2f419-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="2f419-148">Это значение должно быть 100 или выше.</span><span class="sxs-lookup"><span data-stu-id="2f419-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="2f419-149">Необязательно Введите значение в поле **Описание** , чтобы получить дополнительные сведения об этом профиле политики пропускной способности, которое не может быть выражено только именем.</span><span class="sxs-lookup"><span data-stu-id="2f419-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="2f419-150">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="2f419-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="2f419-151">Создание профиля политики пропускной способности не приводит к автоматическому применению ограничений для пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="2f419-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="2f419-152">Сначала необходимо связать профиль политики с сайтом.</span><span class="sxs-lookup"><span data-stu-id="2f419-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="2f419-153">Изменение профиля политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="2f419-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="2f419-154">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2f419-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2f419-155">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2f419-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2f419-156">На панели навигации слева выберите пункт **Настройка сети**, а затем — **политика пропускной способности**.</span><span class="sxs-lookup"><span data-stu-id="2f419-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="2f419-157">На странице **политики пропускной способности** выберите профиль политики пропускной способности, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="2f419-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="2f419-158">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="2f419-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="2f419-159">На странице **профиля политики изменения пропускной способности** измените соответствующие поля (Дополнительные сведения [можно найти в разделе Создание нового профиля политики пропускной способности](#to-create-a-new-bandwidth-policy-profile)).</span><span class="sxs-lookup"><span data-stu-id="2f419-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="2f419-160">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="2f419-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="2f419-161">При изменении профиля политики пропускной способности немедленно обновляются ограничения пропускной способности всех сайтов сети, связанных с этим профилем политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="2f419-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="2f419-162">Удаление профилей политики пропускной способности сети</span><span class="sxs-lookup"><span data-stu-id="2f419-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="2f419-163">В рамках управления допуском звонков (CAC) для определения ограничений пропускной способности для некоторых модальностей используется политика пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="2f419-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="2f419-164">В Skype для бизнеса Server можно назначать ограничения пропускной способности только для звуковых и видеомодальностей.</span><span class="sxs-lookup"><span data-stu-id="2f419-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="2f419-165">Вы можете настроить общие ограничения пропускной способности и ограничения сеанса.</span><span class="sxs-lookup"><span data-stu-id="2f419-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="2f419-166">С помощью панели управления "Skype для бизнеса" можно создавать, изменять и удалять профили контейнеров для этих политик.</span><span class="sxs-lookup"><span data-stu-id="2f419-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="2f419-167">Для удаления профилей политики пропускной способности сети выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="2f419-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="2f419-168">Удаление профиля политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="2f419-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="2f419-169">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="2f419-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2f419-170">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2f419-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="2f419-171">На панели навигации слева выберите пункт **Настройка сети**, а затем — **политика пропускной способности**.</span><span class="sxs-lookup"><span data-stu-id="2f419-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="2f419-172">На странице **политики пропускной способности** выберите профиль политики пропускной способности, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="2f419-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="2f419-173">За один раз можно удалить сразу несколько профилей.</span><span class="sxs-lookup"><span data-stu-id="2f419-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="2f419-174">Для этого нажмите клавишу CTRL и, удерживая нажатой клавишу CTRL, выберите несколько профилей.</span><span class="sxs-lookup"><span data-stu-id="2f419-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="2f419-175">Кроме того, чтобы выбрать все профили, в меню **Правка** выберите команду **выделить все** .</span><span class="sxs-lookup"><span data-stu-id="2f419-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="2f419-176">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="2f419-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="2f419-177">Вы не можете удалить профиль политики пропускной способности, связанный с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="2f419-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="2f419-178">Прежде чем удалять профиль, необходимо сначала удалить связь с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="2f419-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="2f419-179">См. также</span><span class="sxs-lookup"><span data-stu-id="2f419-179">See Also</span></span>

[<span data-ttu-id="2f419-180">Управление допуском звонков для сайтов</span><span class="sxs-lookup"><span data-stu-id="2f419-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="2f419-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="2f419-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="2f419-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="2f419-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="2f419-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="2f419-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="2f419-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="2f419-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

