---
title: 'Lync Server 2013: Убедитесь, что абонентским группам назначены регионы'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4a1982a3625fce40eee9b46036fa4e294ed75edd
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185992"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a><span data-ttu-id="7fe43-102">Убедитесь, что в телефонных планах Lync Server 2013 назначены регионы</span><span class="sxs-lookup"><span data-stu-id="7fe43-102">Make sure dial plans Lync Server 2013 have assigned regions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7fe43-103">_**Последнее изменение темы:** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="7fe43-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="7fe43-p101">Для абонентских групп, используемых при конференц-связи с телефонным подключением, должен быть указан **Dial-in conferencing region** (Регион конференц-связи с телефонным подключением), чтобы связать номера доступа к конференц-связи с телефонным подключением с соответствующей абонентской группой. При настройке абонентской группы вы указываете применяемый к ней регион конференц-связи с телефонным подключением. Потом при создании номеров доступа для телефонного подключения вы выбираете регионы, которые связывают номер доступа с соответствующими абонентскими группами.</span><span class="sxs-lookup"><span data-stu-id="7fe43-p101">Dial plans that are used for dial-in conferencing need to have a **Dial-in conferencing region** specified to associate dial-in conferencing access numbers with the appropriate dial plan. When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan. Then, when you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="7fe43-p102">Поскольку важно указать регион для всех абонентских групп, мы рекомендуем вам использовать данную процедуру, чтобы проверить наличие регионов у всех абонентских групп. Этот этап не является обязательным.</span><span class="sxs-lookup"><span data-stu-id="7fe43-p102">Because it important to specify a region for all dial plans, we recommend that you use this procedure to verify that all dial plans have regions. This step is optional.</span></span>

<span data-ttu-id="7fe43-109">Используйте командлет **Get-CsDialPlan**, чтобы убедиться, что регион установлен для всех абонентских групп конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="7fe43-109">Use the **Get-CsDialPlan** cmdlet to verify whether the region is set for all dial-in conferencing dial plans.</span></span> <span data-ttu-id="7fe43-110">Если регион для абонентских групп не задан, вы можете воспользоваться командлетом **Set-CsDialPlan** и задать такой регион.</span><span class="sxs-lookup"><span data-stu-id="7fe43-110">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="7fe43-111">Вы также можете использовать панель управления Lync Server для обновления региона в существующих абонентских планах.</span><span class="sxs-lookup"><span data-stu-id="7fe43-111">You can also use Lync Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="7fe43-112">Более подробную информацию об использовании панели управления Lync Server можно узнать [в статье Изменение абонентской группы в Lync server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="7fe43-112">For details about using Lync Server Control Panel, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="7fe43-113">Проверка правильности задания регионов для абонентских групп</span><span class="sxs-lookup"><span data-stu-id="7fe43-113">To verify whether dial plans have the region property set</span></span>

1.  <span data-ttu-id="7fe43-114">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="7fe43-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="7fe43-115">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7fe43-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7fe43-116">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="7fe43-116">Run the following at the command prompt:</span></span>
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    <span data-ttu-id="7fe43-117">Например:</span><span class="sxs-lookup"><span data-stu-id="7fe43-117">For example:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="7fe43-118">В данном примере возвращаются все абонентские группы, настроенные для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7fe43-118">In this example, all the dial plans configured for your organization are returned.</span></span>

4.  <span data-ttu-id="7fe43-119">Просмотрите возвращенные абонентские группы, чтобы выявить те из них, для которых не задан регион конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="7fe43-119">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> <span data-ttu-id="7fe43-120">Дополнительные сведения см. в документации Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7fe43-120">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="7fe43-121">Установка свойства региона для абонентской группы</span><span class="sxs-lookup"><span data-stu-id="7fe43-121">To set the region property for a dial plan</span></span>

1.  <span data-ttu-id="7fe43-122">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="7fe43-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="7fe43-123">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="7fe43-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="7fe43-124">Для всех абонентских групп, у которых не задан регион конференц-связи с телефонным подключением, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="7fe43-124">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    <span data-ttu-id="7fe43-125">Например:</span><span class="sxs-lookup"><span data-stu-id="7fe43-125">For example:</span></span>
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    <span data-ttu-id="7fe43-126">В данном примере изменяется абонентская группа с идентификатором Redmond — для ее свойства DialinConferencingRegion устанавливается значение «US West Coast».</span><span class="sxs-lookup"><span data-stu-id="7fe43-126">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> <span data-ttu-id="7fe43-127">Дополнительные сведения см. в документации Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7fe43-127">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

