---
title: Управление профилями политики пропускной способности сети
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Используйте процедуры, описанные в этой статье для просмотра, создания, изменения или удаления профилей политики пропускной способности сети.
ms.openlocfilehash: d27e4df1b549afd3c176f8b54453c44bb97819f8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30878902"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="c89a6-103">Управление профилями политики пропускной способности сети в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c89a6-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="c89a6-104">Используйте процедуры, описанные в этой статье для просмотра, создания, изменения или удаления профилей политики пропускной способности сети.</span><span class="sxs-lookup"><span data-stu-id="c89a6-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="c89a6-105">Просмотр сведений о профиле политики пропускной способности сети</span><span class="sxs-lookup"><span data-stu-id="c89a6-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="c89a6-106">Как часть контроля допуска звонков (CAC) политика пропускной способности используется для определения ограничения пропускной способности для определенных модальностей.</span><span class="sxs-lookup"><span data-stu-id="c89a6-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="c89a6-107">В Скайп для Business Server только аудио- и видеоконференций модальностей может быть назначен ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="c89a6-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="c89a6-108">Можно задать общие ограничения пропускной способности и ограничения сеанса.</span><span class="sxs-lookup"><span data-stu-id="c89a6-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="c89a6-109">Создание, изменение или удаление профиля контейнер для этих политик можно использовать Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c89a6-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="c89a6-110">Каждый профиль политики пропускной способности может быть связан с одной или нескольких сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="c89a6-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="c89a6-111">Используйте следующие процедуры для просмотра профиля политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="c89a6-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="c89a6-112">Просмотр профиля политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="c89a6-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="c89a6-113">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c89a6-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c89a6-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c89a6-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c89a6-115">В левой панели навигации щелкните **Конфигурация сети** и нажмите кнопку **Политика пропускной способности**.</span><span class="sxs-lookup"><span data-stu-id="c89a6-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="c89a6-116">На странице **Политика пропускной способности** щелкните профиль политики пропускной способности, который требуется просмотреть.</span><span class="sxs-lookup"><span data-stu-id="c89a6-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="c89a6-117">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="c89a6-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="c89a6-118">Просмотр сведений о профиле политики пропускной способности сети с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c89a6-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="c89a6-119">Профили пропускной способности сети можно просматривать с помощью командлета Get-CsNetworkBandwidthPolicyProfile и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c89a6-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="c89a6-120">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c89a6-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="c89a6-121">Для просмотра сведений о профиле политики пропускной способности сети</span><span class="sxs-lookup"><span data-stu-id="c89a6-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="c89a6-122">Чтобы просмотреть сведения обо всех вашей сети профилей политики пропускной способности, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="c89a6-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="c89a6-123">Команда возвращает примерно следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="c89a6-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="c89a6-124">Для получения дополнительных сведений см раздел справки для командлета [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) .</span><span class="sxs-lookup"><span data-stu-id="c89a6-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="c89a6-125">Создание или изменение профилей политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="c89a6-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="c89a6-126">Как часть контроля допуска звонков (CAC) политика пропускной способности используется для определения ограничения пропускной способности для определенных модальностей.</span><span class="sxs-lookup"><span data-stu-id="c89a6-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="c89a6-127">В Скайп для Business Server только аудио- и видеоконференций модальностей может быть назначен ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="c89a6-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="c89a6-128">Можно задать общие ограничения пропускной способности и ограничения сеанса.</span><span class="sxs-lookup"><span data-stu-id="c89a6-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="c89a6-129">Создание, изменение или удаление профиля контейнер для этих политик можно использовать Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c89a6-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="c89a6-130">Каждый профиль политики пропускной способности может быть связан с одной или нескольких сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="c89a6-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="c89a6-131">Используйте следующие процедуры для создания или изменения профиля политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="c89a6-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="c89a6-132">Чтобы создать новый профиль политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="c89a6-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="c89a6-133">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c89a6-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c89a6-134">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c89a6-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c89a6-135">В левой панели навигации щелкните **Конфигурация сети**и щелкните **Политика полосы пропускания**.</span><span class="sxs-lookup"><span data-stu-id="c89a6-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="c89a6-136">На странице **Политика пропускной способности** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="c89a6-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="c89a6-137">В **Новый профиль политики пропускной способности**введите имя в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="c89a6-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="c89a6-138">Это имя должно быть уникальным во всех профилей политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="c89a6-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="c89a6-139">В поле **ограничение звук** введите числовое значение.</span><span class="sxs-lookup"><span data-stu-id="c89a6-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="c89a6-140">Это значение — максимальный объем пропускной способности для выделения для всех подключений звука, выраженная в Кбит/с.</span><span class="sxs-lookup"><span data-stu-id="c89a6-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="c89a6-141">Введите числовое значение в поле **ограничения сеанса звука** .</span><span class="sxs-lookup"><span data-stu-id="c89a6-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="c89a6-142">Это значение — максимальный объем пропускной способности для выделения для отдельного звукового подключения, выраженная в Кбит/с.</span><span class="sxs-lookup"><span data-stu-id="c89a6-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="c89a6-143">Это значение должно быть 40 или выше.</span><span class="sxs-lookup"><span data-stu-id="c89a6-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="c89a6-144">Введите числовое значение в поле **ограничение видео** .</span><span class="sxs-lookup"><span data-stu-id="c89a6-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="c89a6-145">Это значение — максимальный объем пропускной способности для размещения для всех подключений с видеоконференциями, выраженная в Кбит/с.</span><span class="sxs-lookup"><span data-stu-id="c89a6-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="c89a6-146">Введите числовое значение в поле **ограничения сеанса видеосвязи** .</span><span class="sxs-lookup"><span data-stu-id="c89a6-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="c89a6-147">Это значение — максимальный объем пропускной способности для выделения для отдельного видео подключения, выраженная в Кбит/с.</span><span class="sxs-lookup"><span data-stu-id="c89a6-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="c89a6-148">Это значение должно быть 100 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="c89a6-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="c89a6-149">(Необязательно) Введите значение в поле **Описание** введите дополнительные сведения об этом профиле политики пропускной способности, которые не могут быть выражены одним именем.</span><span class="sxs-lookup"><span data-stu-id="c89a6-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="c89a6-150">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="c89a6-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="c89a6-151">Создание нового профиля политики пропускной способности не требует автоматически принудительного ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="c89a6-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="c89a6-152">Профиль политики сначала необходимо связать с сайтом.</span><span class="sxs-lookup"><span data-stu-id="c89a6-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="c89a6-153">Изменение профиля политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="c89a6-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="c89a6-154">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c89a6-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c89a6-155">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c89a6-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c89a6-156">В левой панели навигации щелкните **Конфигурация сети**и щелкните **Политика полосы пропускания**.</span><span class="sxs-lookup"><span data-stu-id="c89a6-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="c89a6-157">На странице **Политика пропускной способности** щелкните профиль политики пропускной способности, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="c89a6-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="c89a6-158">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="c89a6-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="c89a6-159">На странице " **Изменение профиля политики пропускной способности** " Изменение полей при необходимости (для получения дополнительных сведений, содержатся в разделе [Создание нового профиля политики пропускной способности](#to-create-a-new-bandwidth-policy-profile)).</span><span class="sxs-lookup"><span data-stu-id="c89a6-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="c89a6-160">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="c89a6-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="c89a6-161">При изменении профиля политики пропускной способности он немедленно обновляет ограничения пропускной способности все сетевые узлы, связанные с этой профиль политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="c89a6-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="c89a6-162">Удаление профилей политик пропускной способности сети</span><span class="sxs-lookup"><span data-stu-id="c89a6-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="c89a6-163">Как часть контроля допуска звонков (CAC) политика пропускной способности используется для определения ограничения пропускной способности для определенных модальностей.</span><span class="sxs-lookup"><span data-stu-id="c89a6-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="c89a6-164">В Скайп для Business Server только аудио- и видеоконференций модальностей может быть назначен ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="c89a6-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="c89a6-165">Можно задать общие ограничения пропускной способности и ограничения сеанса.</span><span class="sxs-lookup"><span data-stu-id="c89a6-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="c89a6-166">Создание, изменение или удаление профиля контейнер для этих политик можно использовать Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c89a6-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="c89a6-167">Используйте следующие процедуры для удаления профилей политики пропускной способности сети.</span><span class="sxs-lookup"><span data-stu-id="c89a6-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="c89a6-168">Чтобы удалить профиль политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="c89a6-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="c89a6-169">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="c89a6-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="c89a6-170">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c89a6-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="c89a6-171">В левой панели навигации щелкните **Конфигурация сети**и щелкните **Политика полосы пропускания**.</span><span class="sxs-lookup"><span data-stu-id="c89a6-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="c89a6-172">На странице **Политика пропускной способности** щелкните профиль политики пропускной способности, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="c89a6-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="c89a6-173">Одновременно можно удалить несколько профилей.</span><span class="sxs-lookup"><span data-stu-id="c89a6-173">You can delete more than one profile at a time.</span></span> <span data-ttu-id="c89a6-174">Для этого нажмите клавишу CTRL и выберите несколько профилей, удерживая нажатой клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="c89a6-174">To do this, press CTRL and select multiple profiles while holding down the CTRL key.</span></span> <span data-ttu-id="c89a6-175">Или, чтобы выбрать все профили, нажмите кнопку **Выбрать все** в меню **Правка** .</span><span class="sxs-lookup"><span data-stu-id="c89a6-175">Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="c89a6-176">В меню **Правка** выберите пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="c89a6-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="c89a6-177">Не удается удалить профиль политики пропускной способности, которая связана с сетевым узлом.</span><span class="sxs-lookup"><span data-stu-id="c89a6-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="c89a6-178">Можно удалить профиль, удалите связь с сетевым узлом.</span><span class="sxs-lookup"><span data-stu-id="c89a6-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="c89a6-179">См. также</span><span class="sxs-lookup"><span data-stu-id="c89a6-179">See Also</span></span>

[<span data-ttu-id="c89a6-180">Управление контролем допуска звонков для сайтов</span><span class="sxs-lookup"><span data-stu-id="c89a6-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="c89a6-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="c89a6-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="c89a6-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="c89a6-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="c89a6-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="c89a6-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="c89a6-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="c89a6-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

