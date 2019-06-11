---
title: 'Lync Server 2013: создание и изменение сетевых сайтов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bb09dfcd490d47de1bbfbbde48f538e95fc64cf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834760"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="96ee1-102">Создание и изменение сетевых сайтов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96ee1-102">Creating or modifying network sites in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96ee1-103">_**Тема последнего изменения:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="96ee1-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="96ee1-104">Сетевые сайты — это офисы или места, настроенные в каждом регионе управления допуском звонков (CAC) или Улучшенное развертывание 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="96ee1-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="96ee1-105">Вы можете настроить сайты и связать их с областями с помощью панели управления Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96ee1-105">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="96ee1-106">Например, сетевой регион для Северной Америки может быть связан с сайтами сети, например в Чикаго, Redmond и Vancouver.</span><span class="sxs-lookup"><span data-stu-id="96ee1-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="96ee1-107">Сайт сети CAC должен создаваться для каждого сайта в Организации, даже если на нем нет ограничений по пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="96ee1-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="96ee1-108">На панели управления Lync Server вы можете создавать, изменять и удалять сетевые сайты.</span><span class="sxs-lookup"><span data-stu-id="96ee1-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="96ee1-109">Для создания и изменения сайта сети выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="96ee1-109">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="96ee1-110">Подробнее об удалении существующего сетевого сайта можно узнать в разделе [Удаление существующего сетевого сайта в Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="96ee1-110">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="96ee1-111">Создание сайта сети</span><span class="sxs-lookup"><span data-stu-id="96ee1-111">To create a network site</span></span>

1.  <span data-ttu-id="96ee1-112">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="96ee1-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="96ee1-113">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96ee1-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="96ee1-114">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="96ee1-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="96ee1-115">На панели навигации слева выберите пункт **Настройка сети** , а затем — **сайт**.</span><span class="sxs-lookup"><span data-stu-id="96ee1-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="96ee1-116">На странице **сайта** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="96ee1-116">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="96ee1-117">В поле **имя** **нового сайта**введите имя для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="96ee1-117">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="96ee1-118">Имена сайтов должны быть уникальными в рамках развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="96ee1-118">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="96ee1-119">В раскрывающемся списке **Region (регион** ) выберите сетевую область, которую нужно связать с этим сайтом.</span><span class="sxs-lookup"><span data-stu-id="96ee1-119">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="96ee1-120">Необязательно Если вы хотите помещать ограничения на пропускную способность для звуковых и видеозвонков на этот сайт, выберите профиль политики пропускной способности с нужными параметрами из раскрывающегося списка **политики пропускной способности** .</span><span class="sxs-lookup"><span data-stu-id="96ee1-120">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="96ee1-121">Вы можете просмотреть сведения о доступных профилях политики пропускной способности или создать новый профиль политики пропускной способности на странице <STRONG>профиля политики</STRONG> в группе <STRONG>Конфигурация сети</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="96ee1-121">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="96ee1-122">Подробные сведения можно найти <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">в разделе Создание и изменение профилей политики пропускной способности в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="96ee1-122">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="96ee1-123">Необязательно Если вы хотите предоставить параметры расположения для этого сайта, выберите политику расположения из раскрывающегося списка " **Политика расположения** ".</span><span class="sxs-lookup"><span data-stu-id="96ee1-123">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="96ee1-124">Политика расположения назначает узлу дополнительные 9-1-1 (E9-1-1) и параметры расположения клиента.</span><span class="sxs-lookup"><span data-stu-id="96ee1-124">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="96ee1-125">Вы можете просмотреть сведения о доступных политиках расположения или создать новую политику местоположения на странице " <STRONG>Политика расположения</STRONG> " в группе " <STRONG>Конфигурация сети</STRONG> ".</span><span class="sxs-lookup"><span data-stu-id="96ee1-125">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="96ee1-126">Подробные сведения можно найти <A href="lync-server-2013-viewing-location-policy-information.md">в разделе Просмотр сведений о правилах расположения в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="96ee1-126">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="96ee1-127">Необязательно Введите значение в поле **Описание** , чтобы получить дополнительные сведения об этом сайте, которые нельзя выразить единственным именем.</span><span class="sxs-lookup"><span data-stu-id="96ee1-127">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="96ee1-128">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="96ee1-128">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="96ee1-129">При создании нового сайта сети <STRONG></STRONG> не следует использовать таблицу с сопоставленными подсетями.</span><span class="sxs-lookup"><span data-stu-id="96ee1-129">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="96ee1-130">При создании или изменении подсети вы связываете подсеть с сайтом.</span><span class="sxs-lookup"><span data-stu-id="96ee1-130">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="96ee1-131">Дополнительные сведения можно найти <A href="lync-server-2013-create-or-modify-network-subnets.md">в разделе Создание или изменение подсетей сети в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="96ee1-131">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="96ee1-132">Изменение сетевого сайта</span><span class="sxs-lookup"><span data-stu-id="96ee1-132">To modify a network site</span></span>

1.  <span data-ttu-id="96ee1-133">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="96ee1-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="96ee1-134">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96ee1-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="96ee1-135">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="96ee1-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="96ee1-136">На панели навигации слева выберите пункт **Настройка сети** , а затем — **сайт**.</span><span class="sxs-lookup"><span data-stu-id="96ee1-136">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="96ee1-137">На странице **сайта** выберите сайт, который вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="96ee1-137">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="96ee1-138">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="96ee1-138">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="96ee1-139">На странице **изменение сайта** можно изменить описание, область, профиль политики пропускной способности и политику расположения, связанные с сайтом.</span><span class="sxs-lookup"><span data-stu-id="96ee1-139">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site.</span></span> <span data-ttu-id="96ee1-140">Дополнительные сведения можно найти в разделе "Создание сетевого сайта" ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="96ee1-140">For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="96ee1-141">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="96ee1-141">Click **Commit**.</span></span>

<span data-ttu-id="96ee1-142">На этой странице невозможно \*\*\*\* изменить связанную таблицу подсетей.</span><span class="sxs-lookup"><span data-stu-id="96ee1-142">You cannot modify the **Associated Subnets** table on this page.</span></span> <span data-ttu-id="96ee1-143">Список связанных подсетей предоставляется для справки, чтобы узнать о том, какие подсети будут затронуты при изменении параметров сайта.</span><span class="sxs-lookup"><span data-stu-id="96ee1-143">The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="96ee1-144">Удаление сайта сети</span><span class="sxs-lookup"><span data-stu-id="96ee1-144">To delete a network site</span></span>

1.  <span data-ttu-id="96ee1-145">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="96ee1-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="96ee1-146">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="96ee1-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="96ee1-147">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="96ee1-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="96ee1-148">На панели навигации слева выберите пункт **Настройка сети** , а затем — **сайт**.</span><span class="sxs-lookup"><span data-stu-id="96ee1-148">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="96ee1-149">На странице **сайта** выберите сайт, который вы хотите удалить.</span><span class="sxs-lookup"><span data-stu-id="96ee1-149">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="96ee1-150">За один раз можно удалить сразу несколько сайтов.</span><span class="sxs-lookup"><span data-stu-id="96ee1-150">You can delete more than one site at a time.</span></span> <span data-ttu-id="96ee1-151">Для этого нажмите клавишу CTRL и, удерживая нажатой клавишу CTRL, щелкните несколько сайтов.</span><span class="sxs-lookup"><span data-stu-id="96ee1-151">To do this, press CTRL and select multiple sites while holding down the CTRL key.</span></span> <span data-ttu-id="96ee1-152">Кроме того, чтобы выбрать все сайты, в меню <STRONG>Правка</STRONG> выберите команду <STRONG>выделить все</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="96ee1-152">Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="96ee1-153">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="96ee1-153">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="96ee1-154">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="96ee1-154">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="96ee1-155">Вы не можете удалить сайт сети, если он связан с сетевой подсетью.</span><span class="sxs-lookup"><span data-stu-id="96ee1-155">You cannot remove a network site if it is associated with a network subnet.</span></span> <span data-ttu-id="96ee1-156">При попытке удалить сайт, связанный с подсетью, появится сообщение об ошибке.</span><span class="sxs-lookup"><span data-stu-id="96ee1-156">If you attempt to remove a site associated with a subnet you will receive an error message.</span></span> <span data-ttu-id="96ee1-157">Чтобы проверить, связан ли сайт с подсетями, щелкните его, а затем в меню <STRONG>Правка</STRONG> выберите команду <STRONG>Показать подробности</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="96ee1-157">To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="96ee1-158">См. также</span><span class="sxs-lookup"><span data-stu-id="96ee1-158">See Also</span></span>


[<span data-ttu-id="96ee1-159">Удаление существующего сетевого сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="96ee1-159">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="96ee1-160">New-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="96ee1-160">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="96ee1-161">Set-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="96ee1-161">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="96ee1-162">Remove-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="96ee1-162">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="96ee1-163">Get-CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="96ee1-163">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

