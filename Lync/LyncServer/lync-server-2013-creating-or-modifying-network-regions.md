---
title: 'Lync Server 2013: создание или изменение областей сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0b3ca5d44fd2278ffee8a3e9dd4494575cc64c65
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34834759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="d4f5b-102">Создание и изменение областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4f5b-102">Creating or modifying network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d4f5b-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="d4f5b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="d4f5b-104">Сетевой регион соединяет различные части сети в нескольких географических регионах.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="d4f5b-105">Каждый сетевой регион должен быть связан с центральным сайтом.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="d4f5b-106">Центральный сайт — это сайт центра обработки данных, на котором запущена служба политики "Управление допуском звонков" (CAC).</span><span class="sxs-lookup"><span data-stu-id="d4f5b-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="d4f5b-107">Вы можете настроить регионы сети с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="d4f5b-108">Сетевые регионы включают параметры, определяющие, разрешены ли для аудио-и видеоподключений альтернативные пути через Интернет.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="d4f5b-109">С помощью панели управления Lync Server вы можете создавать, изменять и удалять сетевые регионы.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="d4f5b-110">Используйте этот раздел для создания и изменения областей сети.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-110">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="d4f5b-111">Подробнее об удалении существующих областей сети можно узнать [в разделе Удаление существующих областей сети в Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="d4f5b-111">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="d4f5b-112">Создание сетевого региона</span><span class="sxs-lookup"><span data-stu-id="d4f5b-112">To create a network region</span></span>

1.  <span data-ttu-id="d4f5b-113">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d4f5b-114">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d4f5b-115">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d4f5b-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d4f5b-116">На панели навигации слева выберите пункт **Настройка сети** , а затем — **регион**.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="d4f5b-117">На странице **регион** нажмите кнопку **создать**.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-117">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="d4f5b-118">На странице **новый регион** введите значение в поле **имя** .</span><span class="sxs-lookup"><span data-stu-id="d4f5b-118">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="d4f5b-119">Это значение должно быть уникальным в рамках развертывания Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-119">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="d4f5b-120">Из раскрывающегося списка **центральное место** выберите Центральный сайт для этого сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-120">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="d4f5b-121">Флажок **включить звуковой путь** по умолчанию установлен.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-121">The **Enable audio alternate path** check box is checked by default.</span></span> <span data-ttu-id="d4f5b-122">Это поле определяет, следует ли перенаправлять голосовые звонки по альтернативному пути, если в основном пути нет необходимой пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-122">This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="d4f5b-123">Снимите этот флажок, только если вам нужно отключить разгрузку в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-123">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="d4f5b-124">Если какой-либо из ваших звонков будет звонить через Интернет, этот флажок должен быть установлен, независимо от настройки пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-124">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="d4f5b-125">Флажок **включить альтернативный путь** для видеоролика установлен по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-125">The **Enable video alternate path** check box is checked by default.</span></span> <span data-ttu-id="d4f5b-126">Это поле определяет, следует ли перенаправлять видеозвонки по альтернативному пути, если в основном пути нет необходимой пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-126">This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path.</span></span> <span data-ttu-id="d4f5b-127">Снимите этот флажок, только если вам нужно отключить разгрузку в Интернете.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-127">Clear this check box only if you need to turn off the offload to the Internet.</span></span> <span data-ttu-id="d4f5b-128">Если какой-либо из ваших звонков будет звонить через Интернет, этот флажок должен быть установлен, независимо от настройки пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-128">If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="d4f5b-129">Необязательно Введите значение в поле **Описание** , чтобы получить дополнительные сведения об этой области, которые нельзя выразить только именем.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-129">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="d4f5b-130">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-130">Click **Commit**.</span></span>

<span data-ttu-id="d4f5b-131">Таблица " **связанные сайты** " не используется для создания сетевого региона.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-131">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="d4f5b-132">Вы связываете сайт с регионом при создании или изменении сайта.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-132">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="d4f5b-133">Подробные сведения можно найти [в разделе Создание или изменение сетевых сайтов в Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="d4f5b-133">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="d4f5b-134">Изменение сетевого региона</span><span class="sxs-lookup"><span data-stu-id="d4f5b-134">To modify a network region</span></span>

1.  <span data-ttu-id="d4f5b-135">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d4f5b-136">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="d4f5b-137">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="d4f5b-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="d4f5b-138">На панели навигации слева выберите пункт **Настройка сети** , а затем — **регион**.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-138">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="d4f5b-139">На странице **регион** щелкните область, которую вы хотите изменить.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-139">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="d4f5b-140">В меню **Правка** щелкните **Подробнее**.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="d4f5b-141">На странице **изменить область** вы можете изменить параметры включения и отключения звуковых и видеофайлов, а также изменения их описания (Дополнительные сведения можно найти в разделе "Создание сетевого региона" ранее в этой статье.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-141">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="d4f5b-142">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-142">Click **Commit**.</span></span>

<span data-ttu-id="d4f5b-143">На этой странице невозможно изменить **связанные сайты** .</span><span class="sxs-lookup"><span data-stu-id="d4f5b-143">You cannot modify the **Associated sites** on this page.</span></span> <span data-ttu-id="d4f5b-144">Список связанных сайтов предоставляется для справки, поэтому вы узнаете, какие сайты будут затронуты при изменении параметров региона.</span><span class="sxs-lookup"><span data-stu-id="d4f5b-144">The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d4f5b-145">См. также</span><span class="sxs-lookup"><span data-stu-id="d4f5b-145">See Also</span></span>


[<span data-ttu-id="d4f5b-146">Удаление существующих областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4f5b-146">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="d4f5b-147">Настройка регионов сети для CAC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d4f5b-147">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="d4f5b-148">New-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d4f5b-148">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="d4f5b-149">Set-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d4f5b-149">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="d4f5b-150">Remove-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d4f5b-150">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="d4f5b-151">Get-CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="d4f5b-151">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

