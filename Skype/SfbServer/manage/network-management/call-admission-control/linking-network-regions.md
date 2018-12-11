---
title: Ссылка на области сети
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 'Можно настроить ссылки между двумя сетевыми регионами в рамках контроля допуска звонков (CAC). '
ms.openlocfilehash: f2f3e170b11677663739f4e06ea7c6768f0a9c11
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "27223019"
---
# <a name="linking-network-regions-in-skype-for-business-server"></a><span data-ttu-id="8777d-103">Ссылка на области сети в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="8777d-103">Linking network regions in Skype for Business Server</span></span>

<span data-ttu-id="8777d-104">Можно настроить ссылки между двумя сетевыми регионами в рамках контроля допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="8777d-104">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="8777d-105">Для просмотра сведений о канале области newtwork или Настройка или удаление связей между областями сетевые используйте разделы в этой статье.</span><span class="sxs-lookup"><span data-stu-id="8777d-105">Use the sections in this article to view newtwork region link information or configure or delete netwrok region links.</span></span> 

## <a name="view-network-region-link-information"></a><span data-ttu-id="8777d-106">Просмотр сведений о канале области сети</span><span class="sxs-lookup"><span data-stu-id="8777d-106">View network region link information</span></span> 

<span data-ttu-id="8777d-107">Вы можете просмотреть ссылки между двумя сетевыми регионами в рамках контроля допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="8777d-107">You can view links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="8777d-108">Области сети, связаны через подключение к физической глобальной сети (WAN).</span><span class="sxs-lookup"><span data-stu-id="8777d-108">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="8777d-109">Скайп для панели управления Business Server можно использовать для просмотра существующей связи между двумя сетевыми регионами.</span><span class="sxs-lookup"><span data-stu-id="8777d-109">You can use the Skype for Business Server Control Panel to view an existing link between two network regions.</span></span> 


### <a name="to-view-a-network-region-link-in-skype-for-business-server-control-panel"></a><span data-ttu-id="8777d-110">Просмотр канала области сети в Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="8777d-110">To view a network region link in Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="8777d-111">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8777d-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8777d-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="8777d-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8777d-113">В левой панели навигации щелкните **Конфигурация сети**и нажмите кнопку **Связь между областями**.</span><span class="sxs-lookup"><span data-stu-id="8777d-113">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="8777d-114">На странице **Связь между областями** щелкните связь, который требуется просмотреть.</span><span class="sxs-lookup"><span data-stu-id="8777d-114">On the **Region Link** page, click the region link that you want to view.</span></span>
    
    > [!NOTE]  
    > <span data-ttu-id="8777d-115">Можно просматривать только сведения об одном канале области за раз.</span><span class="sxs-lookup"><span data-stu-id="8777d-115">You can only view information about one region link at a time.</span></span>

5.  <span data-ttu-id="8777d-116">В меню **Правка** выберите **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="8777d-116">From the **Edit** menu, select **Show details**.</span></span>

### <a name="view-network-region-link-information-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="8777d-117">Просмотр сведений о канале области сети с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8777d-117">View network region link information by using Windows PowerShell cmdlets</span></span>

<span data-ttu-id="8777d-118">Между областями сети можно просмотреть с помощью командлета **Get-CsNetworkRegionLink** и Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8777d-118">You can view network region links by using Windows PowerShell and the **Get-CsNetworkRegionLink** cmdlet.</span></span> <span data-ttu-id="8777d-119">Этот командлет можно запустить из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8777d-119">You can run this cmdlet from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> 


### <a name="to-view-network-region-link-information"></a><span data-ttu-id="8777d-120">Для просмотра сведений о канале области сети</span><span class="sxs-lookup"><span data-stu-id="8777d-120">To view network region link information</span></span>

  - <span data-ttu-id="8777d-121">Чтобы просмотреть сведения о всех каналах между областями сети, введите следующую команду в Скайп для консоли Business Server и нажмите клавишу ВВОД:</span><span class="sxs-lookup"><span data-stu-id="8777d-121">To view information about all your network region links, type the following command in the Skype for Business Server Management Shell, and then press ENTER:</span></span>
    
        Get-CsNetworkRegionLink
    
    <span data-ttu-id="8777d-122">Этой командой возвращается информация, аналогичная следующим сведениям:</span><span class="sxs-lookup"><span data-stu-id="8777d-122">This command returns information similar to the following:</span></span>
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California


<span data-ttu-id="8777d-123">Дополнительные сведения см [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span><span class="sxs-lookup"><span data-stu-id="8777d-123">For details, see [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).</span></span>


## <a name="configure-network-region-links"></a><span data-ttu-id="8777d-124">Настройка связей между сетевыми областями</span><span class="sxs-lookup"><span data-stu-id="8777d-124">Configure network region links</span></span> 

<span data-ttu-id="8777d-125">Можно настроить ссылки между двумя сетевыми регионами в рамках контроля допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="8777d-125">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="8777d-126">Области сети, связаны через подключение к физической глобальной сети (WAN).</span><span class="sxs-lookup"><span data-stu-id="8777d-126">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="8777d-127">Скайп для панели управления Business Server можно использовать для определения связи между двумя сетевыми регионами и устанавливать ограничения пропускной способности подключения к аудио- и видеоконференций между этими областями.</span><span class="sxs-lookup"><span data-stu-id="8777d-127">You can use the Skype for Business Server Control Panel to define a link between two network regions and set the bandwidth limitations on audio and video connections between these regions.</span></span>

### <a name="to-create-a-network-region-link"></a><span data-ttu-id="8777d-128">Создание связи между областями сети</span><span class="sxs-lookup"><span data-stu-id="8777d-128">To create a network region link</span></span>

1.  <span data-ttu-id="8777d-129">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8777d-129">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8777d-130">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="8777d-130">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8777d-131">В левой панели навигации щелкните **Конфигурация сети**и нажмите кнопку **Связь между областями**.</span><span class="sxs-lookup"><span data-stu-id="8777d-131">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="8777d-132">На странице **Связь между областями** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="8777d-132">On the **Region Link** page, click **New**.</span></span>

5.  <span data-ttu-id="8777d-133">В окне **Создание связи между областями**введите значение в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="8777d-133">In **New Region Link**, type a value in the **Name** field.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="8777d-134">Это значение должно быть уникальным в рамках вашей Скайп для развертывания Business Server.</span><span class="sxs-lookup"><span data-stu-id="8777d-134">This value must be unique within your Skype for Business Server deployment.</span></span>

6.  <span data-ttu-id="8777d-135">Из **области сети \#1** раскрывающегося списка, выберите один из двух областей, которые необходимо связать.</span><span class="sxs-lookup"><span data-stu-id="8777d-135">From the **Network region \#1** drop-down list, select one of the two regions to be linked.</span></span>

7.  <span data-ttu-id="8777d-136">Из **области сети \#2** раскрывающегося списка выберите регион, должны быть связаны.</span><span class="sxs-lookup"><span data-stu-id="8777d-136">From the **Network region \#2** drop-down list, select the other region to be linked.</span></span> <span data-ttu-id="8777d-137">Эта область должно отличаться от региона, выбранного для области сети \#1.</span><span class="sxs-lookup"><span data-stu-id="8777d-137">This region must be different from the region selected for Network region \#1.</span></span>

8.  <span data-ttu-id="8777d-138">(Необязательно) Если вы хотите наложить ограничения полосы пропускания на голосовые вызовы и видеовызовы между этими областями, выберите профиль политики пропускной способности из раскрывающегося списка **Политика пропускной способности** .</span><span class="sxs-lookup"><span data-stu-id="8777d-138">(Optional) If you want to place bandwidth limitations on audio or video calls between these regions, select a bandwidth policy profile from the **Bandwidth policy** drop-down list.</span></span>

9.  <span data-ttu-id="8777d-139">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="8777d-139">Click **Commit**.</span></span>

### <a name="to-modify-a-network-region-link"></a><span data-ttu-id="8777d-140">Изменение связи сетевой области</span><span class="sxs-lookup"><span data-stu-id="8777d-140">To modify a network region link</span></span>

1.  <span data-ttu-id="8777d-141">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8777d-141">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8777d-142">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="8777d-142">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8777d-143">В левой панели навигации щелкните **Конфигурация сети**и нажмите кнопку **Связь между областями**.</span><span class="sxs-lookup"><span data-stu-id="8777d-143">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="8777d-144">На странице **Связь между областями** щелкните связь, которую требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="8777d-144">On the **Region Link** page, click the region link that you want to modify.</span></span>

5.  <span data-ttu-id="8777d-145">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="8777d-145">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="8777d-146">В окне **Изменение связи между областями**можно изменить связанные области или профиль политики пропускной способности для этой ссылки.</span><span class="sxs-lookup"><span data-stu-id="8777d-146">In **Edit Region Link**, you can modify the regions that are linked or the bandwidth policy profile for this link.</span></span>

7.  <span data-ttu-id="8777d-147">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="8777d-147">Click **Commit**.</span></span>


## <a name="delete-network-region-links"></a><span data-ttu-id="8777d-148">Удаление связей между сетевыми областями</span><span class="sxs-lookup"><span data-stu-id="8777d-148">Delete network region links</span></span>

<span data-ttu-id="8777d-149">Можно настроить ссылки между двумя сетевыми регионами в рамках контроля допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="8777d-149">You can configure links between two network regions as part of call admission control (CAC).</span></span> <span data-ttu-id="8777d-150">Области сети, связаны через подключение к физической глобальной сети (WAN).</span><span class="sxs-lookup"><span data-stu-id="8777d-150">Regions within a network are linked through physical wide area network (WAN) connectivity.</span></span> <span data-ttu-id="8777d-151">Скайп для панели управления Business Server можно использовать для удаления существующей связи между двумя сетевыми регионами.</span><span class="sxs-lookup"><span data-stu-id="8777d-151">You can use the Skype for Business Server Control Panel to delete an existing link between two network regions.</span></span> 

### <a name="to-delete-a-network-region-link"></a><span data-ttu-id="8777d-152">Чтобы удалить связь между областями сети</span><span class="sxs-lookup"><span data-stu-id="8777d-152">To delete a network region link</span></span>

1.  <span data-ttu-id="8777d-153">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="8777d-153">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8777d-154">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="8777d-154">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 

3.  <span data-ttu-id="8777d-155">В левой панели навигации щелкните **Конфигурация сети**и нажмите кнопку **Связь между областями**.</span><span class="sxs-lookup"><span data-stu-id="8777d-155">In the left navigation bar, click **Network Configuration**, and then click **Region Link**.</span></span>

4.  <span data-ttu-id="8777d-156">На странице **Связь между областями** щелкните связь, которую требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="8777d-156">On the **Region Link** page, click the region link that you want to delete.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="8777d-157">Одновременно можно удалить несколько связь между областями.</span><span class="sxs-lookup"><span data-stu-id="8777d-157">You can delete more than one region link at a time.</span></span> <span data-ttu-id="8777d-158">Для этого нажмите клавишу CTRL и выберите несколько связей между областями, удерживая нажатой клавишу CTRL.</span><span class="sxs-lookup"><span data-stu-id="8777d-158">To do this, press CTRL and select multiple region links while holding down the CTRL key.</span></span> <span data-ttu-id="8777d-159">Или, чтобы выделить все связи между областями, нажмите кнопку <STRONG>Выбрать все</STRONG> в меню <STRONG>Правка</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="8777d-159">Or, to select all region links, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

5.  <span data-ttu-id="8777d-160">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="8777d-160">From the **Edit** menu, select **Delete**.</span></span>

6.  <span data-ttu-id="8777d-161">Нажмите **OK**.</span><span class="sxs-lookup"><span data-stu-id="8777d-161">Click **OK**.</span></span>


## <a name="see-also"></a><span data-ttu-id="8777d-162">См. также</span><span class="sxs-lookup"><span data-stu-id="8777d-162">See Also</span></span>

[<span data-ttu-id="8777d-163">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="8777d-163">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  

[<span data-ttu-id="8777d-164">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="8777d-164">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  

[<span data-ttu-id="8777d-165">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="8777d-165">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  

[<span data-ttu-id="8777d-166">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="8777d-166">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  