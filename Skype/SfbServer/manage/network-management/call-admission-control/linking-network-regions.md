---
title: Связь между сетевыми областями
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Вы можете настроить связи между двумя сетевыми областями в рамках управления допуском звонков (CAC). '
ms.openlocfilehash: 4a643f34b9525b53168b9015b77a7f8292abd417
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817528"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="65087-103">Связывание сетевых областей в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="65087-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="65087-104">Вы можете настроить связи между двумя сетевыми областями в рамках управления допуском звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="65087-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="65087-105">В этой статье описаны разделы, которые можно использовать для просмотра сведений о ссылках в регионе невтворк или для настройки и удаления ссылок на нетврок регионах.</span><span class="sxs-lookup"><span data-stu-id="65087-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="65087-106">Просмотр сведений о ссылке на сетевой регион</span><span class="sxs-lookup"><span data-stu-id="65087-106">View network region link information</span></span> 

<span data-ttu-id="65087-107">Вы можете просматривать ссылки между двумя сетевыми областями в рамках управления допуском звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="65087-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="65087-108">Регионы в сети связаны по ГЛОБАЛЬным сетевым подключениям.</span><span class="sxs-lookup"><span data-stu-id="65087-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="65087-109">Вы можете просмотреть существующую ссылку между двумя областями сети с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="65087-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="65087-110">Чтобы просмотреть ссылку на сетевой регион на панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="65087-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="65087-111">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="65087-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="65087-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="65087-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="65087-113">На панели навигации слева выберите пункт **Настройка сети**, а затем щелкните **ссылку Region (регион**).</span><span class="sxs-lookup"><span data-stu-id="65087-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="65087-114">На странице " **ссылка на регион** " щелкните ссылку "регион", которую вы хотите просмотреть.</span><span class="sxs-lookup"><span data-stu-id="65087-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="65087-115">Вы можете просматривать сведения только о одной ссылке на регион за один раз.</span><span class="sxs-lookup"><span data-stu-id="65087-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="65087-116">В меню **Правка** выберите пункт **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="65087-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="65087-117">Просмотр сведений о связи по сетевому региону с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="65087-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="65087-118">Вы можете просматривать ссылки на сетевую область с помощью Windows PowerShell и командлета **Get-кснетворкрегионлинк** .</span><span class="sxs-lookup"><span data-stu-id="65087-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="65087-119">Вы можете запустить этот командлет из командной консоли Skype для бизнеса Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="65087-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="65087-120">Просмотр сведений о связи по сетевому региону</span><span class="sxs-lookup"><span data-stu-id="65087-120">To view network region link information</span></span>

  - <span data-ttu-id="65087-121">Чтобы просмотреть сведения о ссылках на сетевой регион, введите в командной консоли Skype для Business Server указанную ниже команду и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="65087-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="65087-122">Этой командой возвращается информация, аналогичная следующим сведениям:</span><span class="sxs-lookup"><span data-stu-id="65087-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="65087-123">Подробности можно найти в [статьях Get-кснетворкрегионлинк](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="65087-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="65087-124">Настройка ссылок на сетевой регион</span><span class="sxs-lookup"><span data-stu-id="65087-124">Configure network region links</span></span> 

<span data-ttu-id="65087-125">Вы можете настроить связи между двумя сетевыми областями в рамках управления допуском звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="65087-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="65087-126">Регионы в сети связаны по ГЛОБАЛЬным сетевым подключениям.</span><span class="sxs-lookup"><span data-stu-id="65087-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="65087-127">С помощью панели управления "Skype для бизнеса" можно определить связь между двумя областями сети и задать ограничения пропускной способности для звуковых и видеоподключений между этими регионами.</span><span class="sxs-lookup"><span data-stu-id="65087-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="65087-128">Создание ссылки на сетевой регион</span><span class="sxs-lookup"><span data-stu-id="65087-128">To create a network region link</span></span>

1.  <span data-ttu-id="65087-129">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="65087-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="65087-130">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="65087-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="65087-131">На панели навигации слева выберите пункт **Настройка сети**, а затем щелкните **ссылку Region (регион**).</span><span class="sxs-lookup"><span data-stu-id="65087-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="65087-132">На странице " **ссылка на регион** " нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="65087-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="65087-133">В поле " **ссылка на новый регион**" введите значение из поля **имя** .</span><span class="sxs-lookup"><span data-stu-id="65087-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="65087-134">Это значение должно быть уникальным в рамках развертывания Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="65087-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="65087-135">В раскрывающемся списке **сетевой регион \#1** выберите один из двух областей, которые нужно связать.</span><span class="sxs-lookup"><span data-stu-id="65087-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="65087-136">В раскрывающемся списке **сетевой регион \#2** выберите другой регион, который нужно связать.</span><span class="sxs-lookup"><span data-stu-id="65087-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="65087-137">Этот регион должен отличаться от региона, выбранного для сетевого региона \#1.</span><span class="sxs-lookup"><span data-stu-id="65087-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="65087-138">Необязательно Если вы хотите помещать ограничения на пропускную способность для звуковых и видеозвонков в этих регионах, выберите профиль политики пропускной способности из раскрывающегося списка **политика пропускной способности** .</span><span class="sxs-lookup"><span data-stu-id="65087-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="65087-139">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="65087-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="65087-140">Изменение ссылки на сетевой регион</span><span class="sxs-lookup"><span data-stu-id="65087-140">To modify a network region link</span></span>

1.  <span data-ttu-id="65087-141">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="65087-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="65087-142">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="65087-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="65087-143">На панели навигации слева выберите пункт **Настройка сети**, а затем щелкните **ссылку Region (регион**).</span><span class="sxs-lookup"><span data-stu-id="65087-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="65087-144">На странице " **ссылка на регион** " щелкните ссылку на область, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="65087-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="65087-145">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="65087-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="65087-146">В **ссылке Изменить регион**можно изменить связанные с ней регионы или профиль политики пропускной способности для этой ссылки.</span><span class="sxs-lookup"><span data-stu-id="65087-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="65087-147">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="65087-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="65087-148">Удаление ссылок на сетевой регион</span><span class="sxs-lookup"><span data-stu-id="65087-148">Delete network region links</span></span>

<span data-ttu-id="65087-149">Вы можете настроить связи между двумя сетевыми областями в рамках управления допуском звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="65087-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="65087-150">Регионы в сети связаны по ГЛОБАЛЬным сетевым подключениям.</span><span class="sxs-lookup"><span data-stu-id="65087-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="65087-151">Вы можете удалить существующую связь между двумя сетевыми областями с помощью панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="65087-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="65087-152">Удаление ссылки на сетевой регион</span><span class="sxs-lookup"><span data-stu-id="65087-152">To delete a network region link</span></span>

1.  <span data-ttu-id="65087-153">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="65087-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="65087-154">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="65087-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="65087-155">На панели навигации слева выберите пункт **Настройка сети**, а затем щелкните **ссылку Region (регион**).</span><span class="sxs-lookup"><span data-stu-id="65087-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="65087-156">На странице " **ссылка на регион** " щелкните ссылку "регион", которую вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="65087-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="65087-157">Вы можете удалить несколько ссылок на регион за один раз.</span><span class="sxs-lookup"><span data-stu-id="65087-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="65087-158">Для этого нажмите клавишу CTRL и, удерживая нажатой клавишу CTRL, щелкните ссылки несколько областей.</span><span class="sxs-lookup"><span data-stu-id="65087-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="65087-159">Кроме того, чтобы выделить все ссылки на регион, в меню <STRONG>Правка</STRONG> выберите команду <STRONG>выделить все</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="65087-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="65087-160">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="65087-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="65087-161">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="65087-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="65087-162">См. также</span><span class="sxs-lookup"><span data-stu-id="65087-162">See Also</span></span>

[<span data-ttu-id="65087-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="65087-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="65087-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="65087-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="65087-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="65087-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="65087-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="65087-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
