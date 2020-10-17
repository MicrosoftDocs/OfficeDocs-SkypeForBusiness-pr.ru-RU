---
title: 'Lync Server 2013: создание или изменение сетевых сайтов'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network sites
ms:assetid: 358aa08a-c5bc-45fc-8017-19e6202f88c5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520975(v=OCS.15)
ms:contentKeyID: 48183801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c88ca28478cbd9d38e9e85c5a852fb93b49c0df
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516726"
---
# <a name="creating-or-modifying-network-sites-in-lync-server-2013"></a><span data-ttu-id="7d725-102">Создание или изменение сетевых сайтов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d725-102">Creating or modifying network sites in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7d725-103">_**Последнее изменение темы:** 2012-10-08_</span><span class="sxs-lookup"><span data-stu-id="7d725-103">_**Topic Last Modified:** 2012-10-08_</span></span>

<span data-ttu-id="7d725-104">Сетевые узлы — это офисы или места, настроенные в каждой области развертывания контроля допуска звонков (CAC) или Enhanced 9-1-1.</span><span class="sxs-lookup"><span data-stu-id="7d725-104">Network sites are the offices or locations configured within each region of a call admission control (CAC) or Enhanced 9-1-1 deployment.</span></span> <span data-ttu-id="7d725-105">С помощью панели управления Microsoft Lync Server 2013 можно настраивать сайты и связывать их с областями.</span><span class="sxs-lookup"><span data-stu-id="7d725-105">You can use the Microsoft Lync Server 2013 Control Panel to configure sites and associate them with regions.</span></span> <span data-ttu-id="7d725-106">Например, сетевую область для Северной Америки можно связать с такими сетевыми узлами, как Чикаго, Редмонд и Ванкувер.</span><span class="sxs-lookup"><span data-stu-id="7d725-106">For example, a network region for North America might be associated with networks sites such as Chicago, Redmond, and Vancouver.</span></span> <span data-ttu-id="7d725-107">Сетевой узел CAC необходимо создать для каждого узла в организации, даже если у этого узла нет ограничений по пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="7d725-107">A CAC network site must be created for every site within an organization, even if that site has no bandwidth limitations.</span></span> <span data-ttu-id="7d725-108">С помощью панели управления Lync Server вы можете создавать, изменять и удалять сетевые сайты.</span><span class="sxs-lookup"><span data-stu-id="7d725-108">From the Lync Server Control Panel you can create, modify, and delete network sites.</span></span> <span data-ttu-id="7d725-109">Ниже описаны процедуры для создания или изменения сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="7d725-109">Use the following procedures to create or modify a network site.</span></span> <span data-ttu-id="7d725-110">Более подробную информацию об удалении существующего сетевого сайта можно узнать [в статье Удаление существующего сетевого сайта в Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="7d725-110">For details on deleting an existing network site, see [Deleting an existing network site in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md).</span></span>

<div>

## <a name="to-create-a-network-site"></a><span data-ttu-id="7d725-111">Создание сетевого узла</span><span class="sxs-lookup"><span data-stu-id="7d725-111">To create a network site</span></span>

1.  <span data-ttu-id="7d725-112">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="7d725-112">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7d725-113">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d725-113">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7d725-114">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7d725-114">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7d725-115">В левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Узел**.</span><span class="sxs-lookup"><span data-stu-id="7d725-115">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="7d725-116">На странице **Узел** нажмите кнопку **Создать**.</span><span class="sxs-lookup"><span data-stu-id="7d725-116">On the **Site** page, click **New**.</span></span>

5.  <span data-ttu-id="7d725-117">В диалоговом окне **Создание узла** введите имя узла в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="7d725-117">In **New Site**, type a name for this site in the **Name** field.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7d725-118">Имена сайтов должны быть уникальными в рамках развертывания Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7d725-118">Site names must be unique within the Lync Server 2013 deployment.</span></span>

    
    </div>

6.  <span data-ttu-id="7d725-119">В раскрывающемся списке **Область** выберите сетевую область, которую необходимо сопоставить с этим узлом.</span><span class="sxs-lookup"><span data-stu-id="7d725-119">In the **Region** drop-down list, select a network region to associate with this site.</span></span>

7.  <span data-ttu-id="7d725-120">(Необязательно) Если нужно наложить ограничения полосы пропускания на аудио- или видеовызовы с данного узла, выберите профиль политики с соответствующими параметрами в раскрывающемся списке **Политика полосы пропускания**.</span><span class="sxs-lookup"><span data-stu-id="7d725-120">(Optional) If you want to place bandwidth limitations on audio or video calls to this site, select the bandwidth policy profile with the appropriate settings from the **Bandwidth policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7d725-121">Вы можете просмотреть информацию о доступных профилях политики пропускной полосы или создать новый профиль на странице <STRONG>Профиль политики</STRONG> группы <STRONG>Конфигурация сети</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7d725-121">You can view the details of the available bandwidth policy profiles, or create a new bandwidth policy profile, on the <STRONG>Policy Profile</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="7d725-122">Дополнительные сведения см. <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">в статье Создание или изменение профилей политики пропускной способности в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7d725-122">For details, see <A href="lync-server-2013-creating-or-modifying-bandwidth-policy-profiles.md">Creating or modifying bandwidth policy profiles in Lync Server 2013</A>.</span></span>

    
    </div>

8.  <span data-ttu-id="7d725-123">(Необязательно) Если требуется предоставить параметры местоположения для данного узла, выберите политику расположения в раскрывающемся списке **Политика расположения**.</span><span class="sxs-lookup"><span data-stu-id="7d725-123">(Optional) If you want to provide location settings for this site, select a location policy from the **Location policy** drop-down list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7d725-124">Политика расположения устанавливает определенные параметры системы Enhanced 9-1-1 (E9-1-1) и клиентского расположения для узла.</span><span class="sxs-lookup"><span data-stu-id="7d725-124">The location policy assigns specific Enhanced 9-1-1 (E9-1-1) and client location settings to the site.</span></span> <span data-ttu-id="7d725-125">Вы можете просмотреть сведения о доступных политиках или создать новую на странице <STRONG>Политика расположения</STRONG> группы <STRONG>Конфигурация сети</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7d725-125">You can view the details of the available location policies, or create a new location policy, from the <STRONG>Location Policy</STRONG> page of the <STRONG>Network Configuration</STRONG> group.</span></span> <span data-ttu-id="7d725-126">Дополнительные сведения см. <A href="lync-server-2013-viewing-location-policy-information.md">в разделе Просмотр сведений о политике расположения в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7d725-126">For details, see <A href="lync-server-2013-viewing-location-policy-information.md">Viewing location policy information in Lync Server 2013</A>.</span></span>

    
    </div>

9.  <span data-ttu-id="7d725-127">(Необязательно) Введите значение в поле **Описание**, чтобы предоставить дополнительную информацию об этом узле, которую нельзя выразить в имени.</span><span class="sxs-lookup"><span data-stu-id="7d725-127">(Optional) Type a value in the **Description** field to provide more information about this site that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="7d725-128">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7d725-128">Click **Commit**.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7d725-129">Таблица <STRONG>Связанные подсети</STRONG> не используется при создании нового сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="7d725-129">You do not use the <STRONG>Associated Subnets</STRONG> table when you create a new network site.</span></span> <span data-ttu-id="7d725-130">Необходимо связать подсеть с узлом при создании или изменении подсети.</span><span class="sxs-lookup"><span data-stu-id="7d725-130">You associate a subnet with a site when you create or modify the subnet.</span></span> <span data-ttu-id="7d725-131">Дополнительные сведения см. <A href="lync-server-2013-create-or-modify-network-subnets.md">в статье Создание или изменение сетевых подсетей в Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="7d725-131">For details, see <A href="lync-server-2013-create-or-modify-network-subnets.md">Create or modify network subnets in Lync Server 2013</A>.</span></span>

    
    </div>

</div>

<div>

## <a name="to-modify-a-network-site"></a><span data-ttu-id="7d725-132">Изменение сетевого узла</span><span class="sxs-lookup"><span data-stu-id="7d725-132">To modify a network site</span></span>

1.  <span data-ttu-id="7d725-133">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="7d725-133">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7d725-134">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d725-134">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7d725-135">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7d725-135">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7d725-136">В левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Узел**.</span><span class="sxs-lookup"><span data-stu-id="7d725-136">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="7d725-137">На странице **Узел** щелкните узел, который требуется изменить.</span><span class="sxs-lookup"><span data-stu-id="7d725-137">On the **Site** page, click the site that you want to modify.</span></span>

5.  <span data-ttu-id="7d725-138">В меню **Правка** выберите команду **Показать подробности**.</span><span class="sxs-lookup"><span data-stu-id="7d725-138">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="7d725-p107">На странице **Редактирование узла** вы можете изменить описание, область, профиль политики полосы пропускания и политику расположения, связанную с узлом. Дополнительные сведения см. в разделе "Создание сетевого узла" ранее в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="7d725-p107">On the **Edit Site** page, you can modify the description, region, bandwidth policy profile, and location policy associated with the site. For details, see "To create a network site" section earlier in this topic.</span></span>

7.  <span data-ttu-id="7d725-141">Нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="7d725-141">Click **Commit**.</span></span>

<span data-ttu-id="7d725-p108">Вы не можете изменить таблицу **Связанные подсети** на этой странице. Список связанных подсетей предоставлен для справки, чтобы вы могли узнать, на что повлияет изменение параметров узла.</span><span class="sxs-lookup"><span data-stu-id="7d725-p108">You cannot modify the **Associated Subnets** table on this page. The list of associated subnets is provided for reference so that you are aware of what subnets will be affected when you modify the site settings.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site"></a><span data-ttu-id="7d725-144">Удаление сетевого узла</span><span class="sxs-lookup"><span data-stu-id="7d725-144">To delete a network site</span></span>

1.  <span data-ttu-id="7d725-145">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="7d725-145">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="7d725-146">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7d725-146">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="7d725-147">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="7d725-147">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="7d725-148">В левой панели навигации щелкните **Конфигурация сети**, а затем щелкните **Узел**.</span><span class="sxs-lookup"><span data-stu-id="7d725-148">In the left navigation bar, click **Network Configuration** and then click **Site**.</span></span>

4.  <span data-ttu-id="7d725-149">На странице **Узел** щелкните узел, который требуется удалить.</span><span class="sxs-lookup"><span data-stu-id="7d725-149">On the **Site** page, click the site that you want to delete.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="7d725-p110">Вы можете удалить несколько узлов за раз. Для этого нажмите клавишу CTRL и выберите несколько узлов, удерживая клавишу CTRL нажатой. Или, чтобы выбрать все узлы, щелкните <STRONG>Выбрать все</STRONG> в меню <STRONG>Правка</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7d725-p110">You can delete more than one site at a time. To do this, press CTRL and select multiple sites while holding down the CTRL key. Or, to select all sites, click <STRONG>Select all</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

5.  <span data-ttu-id="7d725-153">В меню **Правка** выберите команду **Удалить**.</span><span class="sxs-lookup"><span data-stu-id="7d725-153">On the **Edit** menu, click **Delete**.</span></span>

6.  <span data-ttu-id="7d725-154">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="7d725-154">Click **OK**.</span></span>
    
    <div>
    

    > [!WARNING]  
    > <span data-ttu-id="7d725-p111">Вы не можете удалить сетевой узел, если он связан с подсетью. При попытке удаления такого узла отображается сообщение об ошибке. Чтобы увидеть, связал ли узел с какой-либо подсетью, щелкните узел и выберите команду <STRONG>Показать подробности</STRONG> в меню <STRONG>Правка</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="7d725-p111">You cannot remove a network site if it is associated with a network subnet. If you attempt to remove a site associated with a subnet you will receive an error message. To see if a site is associated with any subnets, click the site and then click <STRONG>Show details</STRONG> on the <STRONG>Edit</STRONG> menu.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="7d725-158">См. также</span><span class="sxs-lookup"><span data-stu-id="7d725-158">See Also</span></span>


[<span data-ttu-id="7d725-159">Удаление существующего сетевого сайта в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7d725-159">Deleting an existing network site in Lync Server 2013</span></span>](lync-server-2013-deleting-an-existing-network-site.md)  


[<span data-ttu-id="7d725-160">New — CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="7d725-160">New-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkSite)  
[<span data-ttu-id="7d725-161">Set — CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="7d725-161">Set-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkSite)  
[<span data-ttu-id="7d725-162">Remove — CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="7d725-162">Remove-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkSite)  
[<span data-ttu-id="7d725-163">Get — CsNetworkSite</span><span class="sxs-lookup"><span data-stu-id="7d725-163">Get-CsNetworkSite</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

