---
title: 'Lync Server 2013: Включение или отключение функции горячей замены'
description: 'Lync Server 2013: Включение или отключение функции "горячая".'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enable or disable hot desking
ms:assetid: 93a7fed6-f61a-4b41-9336-a8320afa87cf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994057(v=OCS.15)
ms:contentKeyID: 51803968
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3fd22c9bf51078324cfe5e215bd154503c2d9b57
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552435"
---
# <a name="enable-or-disable-hot-desking-in-lync-server-2013"></a><span data-ttu-id="9e523-103">Включение и отключение функции "горячая" в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9e523-103">Enable or disable hot desking in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9e523-104">_**Последнее изменение темы:** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="9e523-104">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="9e523-105">Вы можете настроить телефонные телефоны в качестве *телефонов для стационарных устройств*.</span><span class="sxs-lookup"><span data-stu-id="9e523-105">You can set up common area phones as *hot-desk phones*.</span></span> <span data-ttu-id="9e523-106">С помощью стационарных телефонов пользователи могут входить в систему с помощью собственной учетной записи пользователя, а после входа в систему использовать функции Lync Server и собственные параметры профилей пользователей.</span><span class="sxs-lookup"><span data-stu-id="9e523-106">With hot-desk phones, users can log on to their own user account, and, after they are logged on, use Lync Server features and their own user profile settings.</span></span> <span data-ttu-id="9e523-107">Управление возможностью горячей замены осуществляется с помощью политик клиентов: чтобы включить или отключить функцию "горячего", необходимо изменить политики клиентов, используемые телефонными телефонами.</span><span class="sxs-lookup"><span data-stu-id="9e523-107">Hot desking is managed by using client policies: to enable or disable hot desking, you need to modify the client policies that are used by your common area phones.</span></span> <span data-ttu-id="9e523-108">Сведения о том, как определить политики конференц-связи, назначенные телефонным телефонам, можно узнать [в статье Просмотр сведений о телефонах общей области в Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span><span class="sxs-lookup"><span data-stu-id="9e523-108">For details about how to determine the conferencing policies that have been assigned to your common area phones, see [View common area phone information in Lync Server 2013](lync-server-2013-view-common-area-phone-information.md).</span></span>

<span data-ttu-id="9e523-109">Используйте параметр Енаблехотдескинг командлета **New – CSClientPolicy** или командлета **Set – CSClientPolicy** , чтобы включить или отключить функцию горячей замены на телефоне, как показано ниже.</span><span class="sxs-lookup"><span data-stu-id="9e523-109">You use the EnableHotdesking parameter of the **New-CSClientPolicy** cmdlet or the **Set-CSClientPolicy** cmdlet to enable or disable hot desking on a phone, as follows.</span></span> <span data-ttu-id="9e523-110">Выполните эти командлеты в командной консоли Lync Server 2013 или в удаленном сеансе Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e523-110">Run these cmdlets from either the Lync Server 2013 Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="9e523-111">Сведения об использовании удаленной оболочки Windows PowerShell для подключения к Lync Server приведены в статье "Краткое руководство по управлению Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell" в статье Lync Server Windows PowerShell в блоге [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .</span><span class="sxs-lookup"><span data-stu-id="9e523-111">For details about using remote Windows PowerShell to connect to Lync Server, see the Lync Server Windows PowerShell blog article "Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876).</span></span>

<div>


<div>

## <a name="enabling-hot-desking"></a><span data-ttu-id="9e523-112">Включение функции Hot Desk</span><span class="sxs-lookup"><span data-stu-id="9e523-112">Enabling hot desking</span></span>

  - <span data-ttu-id="9e523-113">Чтобы включить поддержку горячей замены для телефонного телефона общего пользования, необходимо изменить клиентскую политику, назначенную этому телефону (или набору телефонов).</span><span class="sxs-lookup"><span data-stu-id="9e523-113">To enable hot desking for a common area phone, you must modify the client policy that has been assigned to that phone (or collection of phones).</span></span>
    
    <span data-ttu-id="9e523-114">После определения политики, которую необходимо изменить, следующим шагом является использование командлета **Set-CsClientPolicy** для установки параметра Енаблехотдескинг в значение true.</span><span class="sxs-lookup"><span data-stu-id="9e523-114">After you have identified the policy that needs to be modified, the next step is to use the **Set-CsClientPolicy** cmdlet to set the EnableHotdesking parameter to True.</span></span> <span data-ttu-id="9e523-115">Например:</span><span class="sxs-lookup"><span data-stu-id="9e523-115">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $True

  - <span data-ttu-id="9e523-116">Кроме того, вы можете использовать командлет **New – CsClientPolicy** для создания новой клиентской политики, обеспечивающей горячую службу.</span><span class="sxs-lookup"><span data-stu-id="9e523-116">Alternatively, you can use the **New-CsClientPolicy** cmdlet to create a new client policy that enables hot desking.</span></span> <span data-ttu-id="9e523-117">Например:</span><span class="sxs-lookup"><span data-stu-id="9e523-117">For example:</span></span>
    
        New-CsClientPolicy -Identity "NewCommonAreaPhonePolicy" - EnableHotdesking $True

</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="9e523-118">После создания этой политики ее необходимо назначить соответствующим телефонам общего пользования.</span><span class="sxs-lookup"><span data-stu-id="9e523-118">After this policy has been created, you must assign it to the appropriate common area phones.</span></span> <span data-ttu-id="9e523-119">Сведения о том, <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">как назначить политики в Lync Server 2013, можно найти на общем телефоне</A>.</span><span class="sxs-lookup"><span data-stu-id="9e523-119">For details, see <A href="lync-server-2013-assign-policies-to-a-common-area-phone.md">Assign policies in Lync Server 2013 to a common area phone</A>.</span></span>



</div>

<div>

## <a name="disabling-hot-desking"></a><span data-ttu-id="9e523-120">Отключение функции горячей замены</span><span class="sxs-lookup"><span data-stu-id="9e523-120">Disabling hot desking</span></span>

  - <span data-ttu-id="9e523-121">Чтобы отключить функцию горячей замены для телефонного телефона общего пользования, сбросьте параметр Енаблехотдескинг командлета **Set – CsClientPolicy** в значение по умолчанию, равное false.</span><span class="sxs-lookup"><span data-stu-id="9e523-121">To disable hot desking for a common area phone, reset the EnableHotdesking parameter of the **Set-CsClientPolicy** cmdlet to the default value of False.</span></span> <span data-ttu-id="9e523-122">Например:</span><span class="sxs-lookup"><span data-stu-id="9e523-122">For example:</span></span>
    
        Set-CsClientPolicy -Identity "CommonAreaPhonePolicy" - EnableHotdesking $False

</div>

<span data-ttu-id="9e523-123">Дополнительные сведения можно найти в разделах справки для командлета [New – CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) и командлета [Set – CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) .</span><span class="sxs-lookup"><span data-stu-id="9e523-123">For details, see the Help topics for the [New-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsClientPolicy) cmdlet and the [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

