---
title: Связывание областей сети
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
description: 'Вы можете настроить канал между двумя областями сети как часть контроля допуска звонков (CAC). '
ms.openlocfilehash: 0a4f5c63b4470fbfe6d2677f0e9e6f52841f7ebb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816469"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="4d61a-103">Связывание областей сети в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4d61a-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="4d61a-104">Вы можете настроить канал между двумя областями сети как часть контроля допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="4d61a-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4d61a-105">В разделах этой статьи можно просмотреть сведения о ссылках на новые области, а также настроить или удалить ссылки на области netwrok.</span><span class="sxs-lookup"><span data-stu-id="4d61a-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="4d61a-106">Просмотр сведений о связи между областями сети</span><span class="sxs-lookup"><span data-stu-id="4d61a-106">View network region link information</span></span> 

<span data-ttu-id="4d61a-107">Вы можете просмотреть каналы между двумя областями сети как часть контроля допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="4d61a-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4d61a-108">Регионы в сети связываются с помощью физического подключения глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="4d61a-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="4d61a-109">Панель управления Skype для бизнеса Server можно использовать для просмотра существующей связи между двумя областями сети.</span><span class="sxs-lookup"><span data-stu-id="4d61a-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="4d61a-110">Просмотр связи между областями сети на панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4d61a-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="4d61a-111">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="4d61a-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d61a-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4d61a-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4d61a-113">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Связь между областями".**</span><span class="sxs-lookup"><span data-stu-id="4d61a-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4d61a-114">На странице **Канал области** щелкните канал области, который нужно просмотреть.</span><span class="sxs-lookup"><span data-stu-id="4d61a-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="4d61a-115">За один раз вы можете просмотреть сведения только об одном канале области.</span><span class="sxs-lookup"><span data-stu-id="4d61a-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="4d61a-116">В меню **Правка** щелкните пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="4d61a-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="4d61a-117">Просмотр сведений о связи между областями сети с помощью Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4d61a-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="4d61a-118">Для просмотра связей между областями сети можно использовать Windows PowerShell **командлет Get-CsNetworkRegionLink.**</span><span class="sxs-lookup"><span data-stu-id="4d61a-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="4d61a-119">Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4d61a-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="4d61a-120">Просмотр сведений о канале области сети</span><span class="sxs-lookup"><span data-stu-id="4d61a-120">To view network region link information</span></span>

  - <span data-ttu-id="4d61a-121">Чтобы просмотреть сведения обо всех связях между областями сети, введите следующую команду в командной оболочке Skype для бизнеса Server и нажмите ввод:</span><span class="sxs-lookup"><span data-stu-id="4d61a-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="4d61a-122">Эта команда возвращает следующую информацию:</span><span class="sxs-lookup"><span data-stu-id="4d61a-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="4d61a-123">Дополнительные сведения см. в разделе [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="4d61a-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="4d61a-124">Настройка связей между областями сети</span><span class="sxs-lookup"><span data-stu-id="4d61a-124">Configure network region links</span></span> 

<span data-ttu-id="4d61a-125">Вы можете настроить канал между двумя областями сети как часть контроля допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="4d61a-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4d61a-126">Регионы в сети связываются с помощью физического подключения глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="4d61a-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="4d61a-127">Панель управления Skype для бизнеса Server можно использовать для определения связи между двумя областями сети и ограничения пропускной способности аудио- и видеосвязи между этими областями.</span><span class="sxs-lookup"><span data-stu-id="4d61a-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="4d61a-128">Создание связи сетевой области</span><span class="sxs-lookup"><span data-stu-id="4d61a-128">To create a network region link</span></span>

1.  <span data-ttu-id="4d61a-129">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="4d61a-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d61a-130">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4d61a-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4d61a-131">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Связь между областями".**</span><span class="sxs-lookup"><span data-stu-id="4d61a-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4d61a-132">На странице **Связь между областями** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="4d61a-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="4d61a-133">В окне **Создание связи между областями** введите значение в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="4d61a-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="4d61a-134">Это значение должно быть уникальным в развертывании Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4d61a-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="4d61a-135">В **выпадаемом \# списке** "Область сети 1" выберите одну из двух областей, которые необходимо соединить.</span><span class="sxs-lookup"><span data-stu-id="4d61a-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="4d61a-136">В **выпадаемом \# списке** "Регион сети 2" выберите другую область, которая должна быть связана.</span><span class="sxs-lookup"><span data-stu-id="4d61a-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="4d61a-137">Этот регион должен быть отличается от региона, выбранного для области сети \# 1.</span><span class="sxs-lookup"><span data-stu-id="4d61a-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="4d61a-138">(Необязательно) Если нужно наложить ограничения полосы пропускания на аудио- или видеовызовы между этими областями, выберите профиль политики в раскрывающемся списке **Политика полосы пропускания**.</span><span class="sxs-lookup"><span data-stu-id="4d61a-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="4d61a-139">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4d61a-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="4d61a-140">Изменение связи сетевой области</span><span class="sxs-lookup"><span data-stu-id="4d61a-140">To modify a network region link</span></span>

1.  <span data-ttu-id="4d61a-141">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="4d61a-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d61a-142">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4d61a-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4d61a-143">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Связь между областями".**</span><span class="sxs-lookup"><span data-stu-id="4d61a-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4d61a-144">На странице **Связь между областями** щелкните связь, которую нужно изменить.</span><span class="sxs-lookup"><span data-stu-id="4d61a-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="4d61a-145">В меню **Правка** выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="4d61a-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="4d61a-146">В окне **Изменение связи между областями** вы можете изменить связанные области или профиль политики пропускной способности для этой связи.</span><span class="sxs-lookup"><span data-stu-id="4d61a-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="4d61a-147">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="4d61a-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="4d61a-148">Удаление связей между областями сети</span><span class="sxs-lookup"><span data-stu-id="4d61a-148">Delete network region links</span></span>

<span data-ttu-id="4d61a-149">Вы можете настроить канал между двумя областями сети как часть контроля допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="4d61a-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="4d61a-150">Регионы в сети связываются с помощью физического подключения глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="4d61a-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="4d61a-151">Панель управления Skype для бизнеса Server можно использовать для удаления существующей связи между двумя областями сети.</span><span class="sxs-lookup"><span data-stu-id="4d61a-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="4d61a-152">Удаление канала области сети</span><span class="sxs-lookup"><span data-stu-id="4d61a-152">To delete a network region link</span></span>

1.  <span data-ttu-id="4d61a-153">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="4d61a-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="4d61a-154">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="4d61a-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="4d61a-155">В левой панели навигации щелкните **"Конфигурация** сети" и выберите **"Связь между областями".**</span><span class="sxs-lookup"><span data-stu-id="4d61a-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="4d61a-156">На странице **Канал области** щелкните канал области, который нужно удалить.</span><span class="sxs-lookup"><span data-stu-id="4d61a-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="4d61a-p107">За один раз вы можете удалить несколько каналов. Для этого нажмите клавишу CTRL и, удерживая ее, выберите несколько каналов. Чтобы выбрать все каналы, щелкните пункт <STRONG>Выбрать все</STRONG> в меню <STRONG>Правка</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="4d61a-p107">You can delete more than one region link at a time. To do this, press CTRL and select multiple region links while holding down the CTRL key. Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="4d61a-160">В меню **Правка** щелкните пункт **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="4d61a-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="4d61a-161">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="4d61a-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="4d61a-162">См. также</span><span class="sxs-lookup"><span data-stu-id="4d61a-162">See Also</span></span>

[<span data-ttu-id="4d61a-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4d61a-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="4d61a-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4d61a-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="4d61a-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4d61a-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="4d61a-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="4d61a-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
