---
title: Управление профилями политики пропускной способности сети
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Используйте процедуры, рассматриваемые в этой статье, для просмотра, создания, изменения или удаления профилей политики пропускной способности сети.
ms.openlocfilehash: 69efe657b6df775b9e647a77bef2588cafdc5b03
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816449"
---
# <a name="managing-network-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="7ad9d-103">Управление профилями политики пропускной способности сети в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7ad9d-103">Managing network bandwidth policy profiles in Skype for Business Server</span></span>

<span data-ttu-id="7ad9d-104">Используйте процедуры, рассматриваемые в этой статье, для просмотра, создания, изменения или удаления профилей политики пропускной способности сети.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-104">Use the procedures in this article to view, create, modify, or delete network bandwidth policy profiles.</span></span>

## <a name="view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="7ad9d-105">Просмотр сведений профиля политики пропускной способности сети</span><span class="sxs-lookup"><span data-stu-id="7ad9d-105">View network bandwidth policy profile information</span></span>

<span data-ttu-id="7ad9d-106">В рамках контроля допуска звонков политика пропускной способности используется, чтобы определять ограничения пропускной способности для конкретных модальностей.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-106">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="7ad9d-107">В Skype для бизнеса Server ограничения пропускной способности могут быть назначены только модальности аудио- и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-107">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="7ad9d-108">Вы можете задать общие ограничения и ограничения сеанса.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-108">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="7ad9d-109">Панель управления Skype для бизнеса Server можно использовать для создания, изменения или удаления профиля контейнера для этих политик.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-109">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="7ad9d-110">Каждый профиль политики полосы пропускания можно связать с одним или несколькими сетевыми узлами.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-110">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="7ad9d-111">Используйте следующие процедуры для просмотра профиля политики полосы пропускания .</span><span class="sxs-lookup"><span data-stu-id="7ad9d-111">Use the following procedures to view a bandwidth policy profile.</span></span> 

### <a name="to-view-a-bandwidth-policy-profile"></a><span data-ttu-id="7ad9d-112">Просмотр профиля политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="7ad9d-112">To view a bandwidth policy profile</span></span>

1.  <span data-ttu-id="7ad9d-113">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7ad9d-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-114">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7ad9d-115">На панели навигации слева выберите пункт **Конфигурация сети** и щелкните **Политика полосы пропускания**.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-115">In the left navigation bar, click **Network Configuration** and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="7ad9d-116">На странице **"Политика пропускной способности"** щелкните профиль политики пропускной способности, который необходимо просмотреть.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-116">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to view.</span></span>

5.  <span data-ttu-id="7ad9d-117">В меню **Edit** (Правка) щелкните пункт  **Show details** (Показать подробности).</span><span class="sxs-lookup"><span data-stu-id="7ad9d-117">On the **Edit** menu, click **Show details**.</span></span>


### <a name="viewing-network-bandwidth-policy-profile-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="7ad9d-118">Просмотр сведений профиля политики пропускной способности сети с Windows PowerShell с помощью Windows PowerShell сети</span><span class="sxs-lookup"><span data-stu-id="7ad9d-118">Viewing network bandwidth policy profile information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="7ad9d-119">Профили пропускной способности сети можно просматривать с помощью Windows PowerShell и Get-CsNetworkBandwidthPolicyProfile управления.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-119">Network bandwidth profiles can be viewed by using Windows PowerShell and the Get-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="7ad9d-120">Этот cmdlet можно запустить в оболочке управления Skype для бизнеса Server или в удаленном сеансе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-120">This cmdlet can be run either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-bandwidth-policy-profile-information"></a><span data-ttu-id="7ad9d-121">Просмотр сведений профиля политики пропускной способности сети</span><span class="sxs-lookup"><span data-stu-id="7ad9d-121">To view network bandwidth policy profile information</span></span>

  - <span data-ttu-id="7ad9d-122">Чтобы просмотреть сведения обо всех профилях политики пропускной способности сети, введите следующую команду в командной оболочке Skype для бизнеса Server и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="7ad9d-122">To view information about all your network bandwidth policy profiles, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkBandwidthPolicyProfile
    
    <span data-ttu-id="7ad9d-123">Это приведет к возврату приблизительно такой информации:</span><span class="sxs-lookup"><span data-stu-id="7ad9d-123">That will return information similar to this:</span></span>
    
        Identity          : RedmondBandwidthPolicy
        BWPolicy          : {BWLimit=200;BWSessionLimit=200;
                            BWPolicyModality=Audio, 
                            BWLimit=1400;BWSessionLimit=500;
                            BWPolicyModality=Video}
        BWPolicyProfileID : RedmondBandwidthPolicy
        Description       :


<span data-ttu-id="7ad9d-124">Дополнительные сведения см. в разделе справки о командлете [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile).</span><span class="sxs-lookup"><span data-stu-id="7ad9d-124">For more information, see the help topic for the [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) cmdlet.</span></span>


## <a name="create-or-modify-bandwidth-policy-profiles"></a><span data-ttu-id="7ad9d-125">Создание или изменение профилей политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="7ad9d-125">Create or modify bandwidth policy profiles</span></span>

<span data-ttu-id="7ad9d-126">В рамках контроля допуска звонков политика пропускной способности используется, чтобы определять ограничения пропускной способности для конкретных модальностей.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-126">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="7ad9d-127">В Skype для бизнеса Server ограничения пропускной способности могут быть назначены только модальности аудио- и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-127">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="7ad9d-128">Вы можете задать общие ограничения и ограничения сеанса.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-128">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="7ad9d-129">Панель управления Skype для бизнеса Server можно использовать для создания, изменения или удаления профиля контейнера для этих политик.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-129">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="7ad9d-130">Каждый профиль политики полосы пропускания можно связать с одним или несколькими сетевыми узлами.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-130">Each bandwidth policy profile can be associated with one or more network sites.</span></span> <span data-ttu-id="7ad9d-131">Используйте следующие процедуры для создания или изменения профиля политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-131">Use the following procedures to create or modify a bandwidth policy profile.</span></span> 

### <a name="to-create-a-new-bandwidth-policy-profile"></a><span data-ttu-id="7ad9d-132">Создание нового профиля политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="7ad9d-132">To create a new bandwidth policy profile</span></span>

1.  <span data-ttu-id="7ad9d-133">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7ad9d-134">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-134">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7ad9d-135">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Политика пропускной способности".**</span><span class="sxs-lookup"><span data-stu-id="7ad9d-135">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="7ad9d-136">На странице **"Политика пропускной способности"** нажмите кнопку **"Новый".**</span><span class="sxs-lookup"><span data-stu-id="7ad9d-136">On the **Bandwidth Policy** page, click **New**.</span></span>

5.  <span data-ttu-id="7ad9d-137">В **новом профиле политики пропускной способности** введите имя в поле **"Имя".**</span><span class="sxs-lookup"><span data-stu-id="7ad9d-137">In **New Bandwidth Policy Profile**, type a name in the **Name** field.</span></span> <span data-ttu-id="7ad9d-138">Это имя должно быть уникальным для всех профилей политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-138">This name must be unique among all bandwidth policy profiles.</span></span>

6.  <span data-ttu-id="7ad9d-139">В поле **ограничения аудио** введите числовые значения.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-139">In the **Audio limit** field, type a numeric value.</span></span> <span data-ttu-id="7ad9d-140">Это значение является максимальным объемом пропускной способности, выделяемой для всех звуковых подключений, выраженных в кб/с.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-140">This value is the maximum amount of bandwidth to allocate for all audio connections, expressed in kbps.</span></span>

7.  <span data-ttu-id="7ad9d-141">Введите числовые значения в поле ограничения **сеанса** аудиосвязи.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-141">Enter a numeric value in the **Audio session limit** field.</span></span> <span data-ttu-id="7ad9d-142">Это значение является максимальным объемом пропускной способности, выделяемой для отдельного звукового подключения, выраженного в кб/с.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-142">This value is the maximum amount of bandwidth to allocate for an individual audio connection, expressed in kbps.</span></span> <span data-ttu-id="7ad9d-143">Это значение должно быть не менее 40.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-143">This value must be 40 or higher.</span></span>

8.  <span data-ttu-id="7ad9d-144">Введите числовом значении в поле **ограничения видео.**</span><span class="sxs-lookup"><span data-stu-id="7ad9d-144">Enter a numeric value in the **Video limit** field.</span></span> <span data-ttu-id="7ad9d-145">Это значение является максимальным объемом пропускной способности, выделяемой для всех видео подключений, выраженной в кб/с.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-145">This value is the maximum amount of bandwidth to allocate for all video connections, expressed in kbps.</span></span>

9.  <span data-ttu-id="7ad9d-146">Введите числовом значении в поле ограничения **сеанса** видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-146">Enter a numeric value in the **Video session limit** field.</span></span> <span data-ttu-id="7ad9d-147">Это значение является максимальным объемом пропускной способности, выделяемой для отдельного видеосвязи, выраженной в кб/с.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-147">This value is the maximum amount of bandwidth to allocate for an individual video connection, expressed in kbps.</span></span> <span data-ttu-id="7ad9d-148">Это значение должно быть не менее 100.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-148">This value must be 100 or higher.</span></span>

10. <span data-ttu-id="7ad9d-149">(Необязательно) Введите значение  в поле "Описание", чтобы предоставить дополнительные сведения об этом профиле политики пропускной способности, которые не могут быть выражены только именем.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-149">(Optional) Type a value in the **Description** field to provide more information about this bandwidth policy profile that cannot be expressed by the name alone.</span></span>

11. <span data-ttu-id="7ad9d-150">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-150">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="7ad9d-151">Создание нового профиля политики пропускной способности не применяет автоматически ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-151">Creating a new bandwidth policy profile does not automatically enforce bandwidth restrictions.</span></span> <span data-ttu-id="7ad9d-152">Сначала необходимо связать профиль политики с сайтом.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-152">You must first associate the policy profile with a site.</span></span> 


### <a name="to-modify-a-bandwidth-policy-profile"></a><span data-ttu-id="7ad9d-153">Изменение профиля политики полосы пропускания</span><span class="sxs-lookup"><span data-stu-id="7ad9d-153">To modify a bandwidth policy profile</span></span>

1.  <span data-ttu-id="7ad9d-154">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-154">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7ad9d-155">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-155">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7ad9d-156">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Политика пропускной способности".**</span><span class="sxs-lookup"><span data-stu-id="7ad9d-156">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="7ad9d-157">На странице **Политика полосы пропускания** щелкните профиль политики полосы пропускания, который нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-157">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to modify.</span></span>

5.  <span data-ttu-id="7ad9d-158">В меню **Правка** щелкните пункт  **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-158">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="7ad9d-159">На странице **"Изменение профиля политики** пропускной способности" при необходимости измените поля (дополнительные сведения см. в подсети "Создание [нового профиля политики пропускной способности").](#to-create-a-new-bandwidth-policy-profile)</span><span class="sxs-lookup"><span data-stu-id="7ad9d-159">On the **Edit Bandwidth Policy Profile** page, modify the fields as necessary (for details, see [To create a new bandwidth policy profile](#to-create-a-new-bandwidth-policy-profile)).</span></span>

7.  <span data-ttu-id="7ad9d-160">Щелкните **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-160">Click **Commit**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="7ad9d-161">При изменении профиля политики пропускной способности он немедленно обновет ограничения пропускной способности всех сетевых узлов, связанных с этим профилем политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-161">When you modify the bandwidth policy profile, it will immediately update the bandwidth limitations of all network sites associated with this bandwidth policy profile.</span></span>

  
## <a name="delete-network-bandwidth-policy-profiles"></a><span data-ttu-id="7ad9d-162">Удаление профилей политики пропускной способности сети</span><span class="sxs-lookup"><span data-stu-id="7ad9d-162">Delete network bandwidth policy profiles</span></span>

<span data-ttu-id="7ad9d-163">В рамках контроля допуска звонков политика пропускной способности используется, чтобы определять ограничения пропускной способности для конкретных модальностей.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-163">As part of call admission control (CAC), a bandwidth policy is used to define bandwidth limitations for certain modalities.</span></span> <span data-ttu-id="7ad9d-164">В Skype для бизнеса Server ограничения пропускной способности могут быть назначены только модальности аудио- и видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-164">In Skype for Business Server, only audio and video modalities can be assigned bandwidth limitations.</span></span> <span data-ttu-id="7ad9d-165">Вы можете задать общие ограничения и ограничения сеанса.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-165">You can set overall bandwidth limitations and session limitations.</span></span> <span data-ttu-id="7ad9d-166">Панель управления Skype для бизнеса Server можно использовать для создания, изменения или удаления профиля контейнера для этих политик.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-166">You can use the Skype for Business Server Control Panel to create, modify, or delete a container profile for these policies.</span></span> <span data-ttu-id="7ad9d-167">Используйте следующие процедуры для удаления профилей политик пропускной способности сети.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-167">Use the following procedures to delete a network bandwidth policy profiles.</span></span> 

### <a name="to-delete-a-bandwidth-policy-profile"></a><span data-ttu-id="7ad9d-168">Чтобы удалить профиль политики пропускной способности</span><span class="sxs-lookup"><span data-stu-id="7ad9d-168">To delete a bandwidth policy profile</span></span>

1.  <span data-ttu-id="7ad9d-169">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-169">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7ad9d-170">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="7ad9d-171">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Политика пропускной способности".**</span><span class="sxs-lookup"><span data-stu-id="7ad9d-171">In the left navigation bar, click **Network Configuration**, and then click **Bandwidth Policy**.</span></span>

4.  <span data-ttu-id="7ad9d-172">На странице **Политика пропускной способности** щелкните профиль политики пропускной способности, который следует удалить.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-172">On the **Bandwidth Policy** page, click the bandwidth policy profile that you want to delete.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="7ad9d-p111">Одновременно можно удалить сразу несколько профилей. Для этого нажмите и удерживайте клавишу CTRL, одновременно выбирая несколько профилей. Или щелкните пункт **Выделить все** в меню **Изменить** для выбора сразу нескольких профилей.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-p111">You can delete more than one profile at a time. To do this, press CTRL and select multiple profiles while holding down the CTRL key. Or, to select all profiles, click **Select all** on the **Edit** menu.</span></span>

5.  <span data-ttu-id="7ad9d-176">В меню **Изменить** щелкните **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-176">On the **Edit** menu, click **Delete**.</span></span>
   

    > [!WARNING]  
    > <span data-ttu-id="7ad9d-177">Невозможно удалить профили политики пропускной способности, связанные с сетевым сайтом.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-177">You cannot delete a bandwidth policy profile that is associated with a network site.</span></span> <span data-ttu-id="7ad9d-178">Сначала следует удалить связь с сетевым сайтом, а затем удалить профиль.</span><span class="sxs-lookup"><span data-stu-id="7ad9d-178">You must first remove the association with the network site before you can delete the profile.</span></span> 


## <a name="see-also"></a><span data-ttu-id="7ad9d-179">См. также</span><span class="sxs-lookup"><span data-stu-id="7ad9d-179">See Also</span></span>

[<span data-ttu-id="7ad9d-180">Управление контролем допуска вызовов для сайтов</span><span class="sxs-lookup"><span data-stu-id="7ad9d-180">Managing call admission control for sites</span></span>](managing-call-admission-control-for-sites.md)
 
[<span data-ttu-id="7ad9d-181">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="7ad9d-181">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="7ad9d-182">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="7ad9d-182">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="7ad9d-183">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="7ad9d-183">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  

[<span data-ttu-id="7ad9d-184">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="7ad9d-184">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)  
  

