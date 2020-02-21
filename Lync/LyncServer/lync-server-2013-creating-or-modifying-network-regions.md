---
title: 'Lync Server 2013: создание или изменение областей сети'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network regions
ms:assetid: bd08bb66-5976-4ece-b45c-7de19569f814
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182579(v=OCS.15)
ms:contentKeyID: 48185266
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52518c76efdb302661ed3f097cb382d399299798
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42196202"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-regions-in-lync-server-2013"></a><span data-ttu-id="40150-102">Создание или изменение областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40150-102">Creating or modifying network regions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40150-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="40150-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="40150-104">Область сети связывает части сети, расположенные в различных географических районах.</span><span class="sxs-lookup"><span data-stu-id="40150-104">A network region interconnects various parts of a network across multiple geographic areas.</span></span> <span data-ttu-id="40150-105">Каждый регион сети должен быть связан с центральным сайтом.</span><span class="sxs-lookup"><span data-stu-id="40150-105">Every network region must be associated with a central site.</span></span> <span data-ttu-id="40150-106">Центральный сайт — это сайт центра обработки данных, на котором выполняется служба политики пропускной способности для контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="40150-106">The central site is the data center site on which the call admission control (CAC) bandwidth policy service is running.</span></span> <span data-ttu-id="40150-107">Для настройки областей сети можно использовать панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40150-107">You can use Lync Server Control Panel to configure network regions.</span></span> <span data-ttu-id="40150-108">Области сети включают параметры, которые определяют, разрешены ли альтернативные пути через Интернет для аудио- и видеоподключений.</span><span class="sxs-lookup"><span data-stu-id="40150-108">Network regions include settings that determine whether alternate paths through the Internet are allowed for audio and video connections.</span></span> <span data-ttu-id="40150-109">С помощью панели управления Lync Server можно создавать, изменять и удалять области сети.</span><span class="sxs-lookup"><span data-stu-id="40150-109">From the Lync Server Control Panel, you can create, modify, or delete a network region.</span></span> <span data-ttu-id="40150-110">Используйте этот раздел для создания и изменения областей сети.</span><span class="sxs-lookup"><span data-stu-id="40150-110">Use this topic to create and modify network regions.</span></span> <span data-ttu-id="40150-111">Дополнительные сведения об удалении существующих областей сети приведены [в статье Удаление существующих областей сети в Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span><span class="sxs-lookup"><span data-stu-id="40150-111">For details about deleting existing network regions, see [Deleting existing network regions in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md).</span></span>

<div>

## <a name="to-create-a-network-region"></a><span data-ttu-id="40150-112">Создание области сети</span><span class="sxs-lookup"><span data-stu-id="40150-112">To create a network region</span></span>

1.  <span data-ttu-id="40150-113">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="40150-113">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="40150-114">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40150-114">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="40150-115">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="40150-115">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="40150-116">В левой панели навигации щелкните элемент **Конфигурация сети** и выберите элемент **Область**.</span><span class="sxs-lookup"><span data-stu-id="40150-116">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="40150-117">На странице **Область**  щелкните **Создать**.</span><span class="sxs-lookup"><span data-stu-id="40150-117">On the **Region** page, click **New**.</span></span>

5.  <span data-ttu-id="40150-118">На странице **Создание области** введите имя области сети в поле **Имя**.</span><span class="sxs-lookup"><span data-stu-id="40150-118">In the **New Region** page, type a value in the **Name** field.</span></span> <span data-ttu-id="40150-119">Это значение должно быть уникальным в пределах развертывания Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="40150-119">This value must be unique within your Microsoft Lync Server 2013 deployment.</span></span>

6.  <span data-ttu-id="40150-120">В раскрывающемся списке **Центральный сайт** выберите центральный сайт для этой области сети.</span><span class="sxs-lookup"><span data-stu-id="40150-120">From the **Central site** drop-down list, select the central site for this network region.</span></span>

7.  <span data-ttu-id="40150-p104">Флажок **Включить альтернативный путь для звонков** установлен по умолчанию. Этот параметр указывает, будут ли звонки перенаправляться по альтернативному пути, если пропускной способности основного пути недостаточно. Этот флажок нужно снимать только в том случае, если требуется отключить разгрузку в Интернет. При наличии звонков по Интернету этот флажок должен быть установлен независимо от параметров пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="40150-p104">The **Enable audio alternate path** check box is checked by default. This field determines whether audio calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

8.  <span data-ttu-id="40150-p105">Флажок **Включить альтернативный путь видеозвонков** установлен по умолчанию. Этот параметр указывает, будут ли видеозвонки перенаправляться по альтернативному пути, если пропускной способности основного пути недостаточно. Этот флажок нужно снимать только в том случае, если требуется отключить разгрузку в Интернет. При наличии звонков по Интернету этот флажок должен быть установлен независимо от параметров пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="40150-p105">The **Enable video alternate path** check box is checked by default. This field determines whether video calls will be routed through an alternate path if adequate bandwidth does not exist in the primary path. Clear this check box only if you need to turn off the offload to the Internet. If any of your calls will be Internet calls, this check box must be checked, regardless of bandwidth settings.</span></span>

9.  <span data-ttu-id="40150-129">Введите дополнительные сведения об области сети в поле **Описание** (необязательно).</span><span class="sxs-lookup"><span data-stu-id="40150-129">(Optional) Type a value in the **Description** field to provide more information about this region that cannot be expressed by the name alone.</span></span>

10. <span data-ttu-id="40150-130">Щелкните **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="40150-130">Click **Commit**.</span></span>

<span data-ttu-id="40150-131">При создании области сети таблица **Связанные сайты** не используется.</span><span class="sxs-lookup"><span data-stu-id="40150-131">The **Associated sites** table is not used for creating a network region.</span></span> <span data-ttu-id="40150-132">Вы можете связать сайт с областью при создании или изменении сайта.</span><span class="sxs-lookup"><span data-stu-id="40150-132">You associate a site with a region when you create or modify the site.</span></span> <span data-ttu-id="40150-133">Дополнительные сведения см. [в статье Создание или изменение сетевых сайтов в Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span><span class="sxs-lookup"><span data-stu-id="40150-133">For details, see [Creating or modifying network sites in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).</span></span>

</div>

<div>

## <a name="to-modify-a-network-region"></a><span data-ttu-id="40150-134">Изменение области сети</span><span class="sxs-lookup"><span data-stu-id="40150-134">To modify a network region</span></span>

1.  <span data-ttu-id="40150-135">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="40150-135">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="40150-136">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="40150-136">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="40150-137">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="40150-137">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="40150-138">В левой панели навигации щелкните **Конфигурация сети** и затем щелкните **Область**.</span><span class="sxs-lookup"><span data-stu-id="40150-138">In the left navigation bar, click **Network Configuration** and then click **Region**.</span></span>

4.  <span data-ttu-id="40150-139">На странице **Область** щелкните область, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="40150-139">On the **Region** page, click the region that you want to modify.</span></span>

5.  <span data-ttu-id="40150-140">В меню **Правка** выберите команду **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="40150-140">On the **Edit** menu, click **Show details**.</span></span>

6.  <span data-ttu-id="40150-141">На странице **Изменение области** можно изменить параметры включения и отключения альтернативных путей для звонков и видеозвонков, а также изменить описание (дополнительные сведения см. в подразделе "Создание области сети" настоящего раздела).</span><span class="sxs-lookup"><span data-stu-id="40150-141">On the **Edit Region** page, you can modify the settings for enabling and disabling audio and video alternate paths, and change the description (for details, see the "To create a network region" section earlier in this topic.</span></span>

7.  <span data-ttu-id="40150-142">Щелкните **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="40150-142">Click **Commit**.</span></span>

<span data-ttu-id="40150-p108">На этой странице нельзя изменить **Связанные сайты**. В этом списке указаны сайты, на которые может повлиять изменение параметров области.</span><span class="sxs-lookup"><span data-stu-id="40150-p108">You cannot modify the **Associated sites** on this page. The list of associated sites is provided for reference so you are aware of which sites will be affected when you modify the region settings.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="40150-145">См. также</span><span class="sxs-lookup"><span data-stu-id="40150-145">See Also</span></span>


[<span data-ttu-id="40150-146">Удаление существующих областей сети в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40150-146">Deleting existing network regions in Lync Server 2013</span></span>](lync-server-2013-deleting-existing-network-regions.md)  
[<span data-ttu-id="40150-147">Настройка сетевых регионов для CAC в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40150-147">Configure network regions for CAC in Lync Server 2013</span></span>](lync-server-2013-configure-network-regions-for-cac.md)  


[<span data-ttu-id="40150-148">New — CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="40150-148">New-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)  
[<span data-ttu-id="40150-149">Set — CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="40150-149">Set-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)  
[<span data-ttu-id="40150-150">Remove — CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="40150-150">Remove-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)  
[<span data-ttu-id="40150-151">Get — CsNetworkRegion</span><span class="sxs-lookup"><span data-stu-id="40150-151">Get-CsNetworkRegion</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

