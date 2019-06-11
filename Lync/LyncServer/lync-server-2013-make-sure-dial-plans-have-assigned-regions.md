---
title: 'Lync Server 2013: проверка назначения регионов абонентским группам'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Make sure dial plans have assigned regions
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425903(v=OCS.15)
ms:contentKeyID: 48183937
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 75c5aa91470accf0f25478b9233e1efb90357251
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828371"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="make-sure-dial-plans-lync-server-2013-have-assigned-regions"></a><span data-ttu-id="58dd9-102">Проверка абонентских планов Lync Server 2013 назначенные регионы</span><span class="sxs-lookup"><span data-stu-id="58dd9-102">Make sure dial plans Lync Server 2013 have assigned regions</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="58dd9-103">_**Тема последнего изменения:** 2010-11-02_</span><span class="sxs-lookup"><span data-stu-id="58dd9-103">_**Topic Last Modified:** 2010-11-02_</span></span>

<span data-ttu-id="58dd9-104">Для абонентской группы, используемой для конференц-связи с телефонным подключением, необходимо указать **регион Конференц** -связи с телефонным подключением, чтобы связать номера доступа для конференц-связи с телефонным подключением с помощью соответствующей абонентской группы.</span><span class="sxs-lookup"><span data-stu-id="58dd9-104">Dial plans that are used for dial-in conferencing need to have a **Dial-in conferencing region** specified to associate dial-in conferencing access numbers with the appropriate dial plan.</span></span> <span data-ttu-id="58dd9-105">При создании абонентской группы следует задать регион конференц-связи с телефонным подключением, применяемый к этой абонентской группе.</span><span class="sxs-lookup"><span data-stu-id="58dd9-105">When you set up a dial plan, you specify the dial-in conferencing region that applies to that dial plan.</span></span> <span data-ttu-id="58dd9-106">Затем, когда вы создадите номер доступа для телефонного подключения, вы выбираете регионы, связывающие номер доступа с соответствующими абонентской абонентской панелью.</span><span class="sxs-lookup"><span data-stu-id="58dd9-106">Then, when you create the dial-in access number, you select the regions that associate the access number with the appropriate dial plans.</span></span>

<span data-ttu-id="58dd9-107">Так как важно указать регион для всех абонентов, мы рекомендуем использовать эту процедуру, чтобы убедиться, что все абонентские группы имеют регионы.</span><span class="sxs-lookup"><span data-stu-id="58dd9-107">Because it important to specify a region for all dial plans, we recommend that you use this procedure to verify that all dial plans have regions.</span></span> <span data-ttu-id="58dd9-108">Этот шаг является необязательным.</span><span class="sxs-lookup"><span data-stu-id="58dd9-108">This step is optional.</span></span>

<span data-ttu-id="58dd9-109">С помощью командлета **Get-ксдиалплан** убедитесь, что регион задан для всех абонентских планов для конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="58dd9-109">Use the **Get-CsDialPlan** cmdlet to verify whether the region is set for all dial-in conferencing dial plans.</span></span> <span data-ttu-id="58dd9-110">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span><span class="sxs-lookup"><span data-stu-id="58dd9-110">If the region is missing from dial plans, you can use the **Set-CsDialPlan** cmdlet to set the region.</span></span> <span data-ttu-id="58dd9-111">Вы также можете использовать панель управления Lync Server для обновления региона в существующих абонентских тарифах.</span><span class="sxs-lookup"><span data-stu-id="58dd9-111">You can also use Lync Server Control Panel to update the region in existing dial plans.</span></span> <span data-ttu-id="58dd9-112">Подробнее об использовании панели управления Lync Server можно найти [в разделе Изменение абонентской группы в Lync server 2013](lync-server-2013-modify-a-dial-plan.md).</span><span class="sxs-lookup"><span data-stu-id="58dd9-112">For details about using Lync Server Control Panel, see [Modify a dial plan in Lync Server 2013](lync-server-2013-modify-a-dial-plan.md).</span></span>

<div>

## <a name="to-verify-whether-dial-plans-have-the-region-property-set"></a><span data-ttu-id="58dd9-113">Проверка правильности задания регионов для абонентских групп</span><span class="sxs-lookup"><span data-stu-id="58dd9-113">To verify whether dial plans have the region property set</span></span>

1.  <span data-ttu-id="58dd9-114">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="58dd9-114">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="58dd9-115">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="58dd9-115">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="58dd9-116">Выполните следующую команду в командной строке:</span><span class="sxs-lookup"><span data-stu-id="58dd9-116">Run the following at the command prompt:</span></span>
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    <span data-ttu-id="58dd9-117">Например:</span><span class="sxs-lookup"><span data-stu-id="58dd9-117">For example:</span></span>
    
        Get-CsDialPlan
    
    <span data-ttu-id="58dd9-118">В данном примере возвращаются все абонентские группы, настроенные для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="58dd9-118">In this example, all the dial plans configured for your organization are returned.</span></span>

4.  <span data-ttu-id="58dd9-119">Просмотрите возвращенные абонентские группы, чтобы выявить те из них, для которых не задан регион конференц-связи с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="58dd9-119">Review the returned dial plans to identify any that are missing the dial-in conferencing region.</span></span> <span data-ttu-id="58dd9-120">Подробные сведения можно найти в руководстве по среде Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="58dd9-120">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-set-the-region-property-for-a-dial-plan"></a><span data-ttu-id="58dd9-121">Установка свойства региона для абонентской группы</span><span class="sxs-lookup"><span data-stu-id="58dd9-121">To set the region property for a dial plan</span></span>

1.  <span data-ttu-id="58dd9-122">Войдите на компьютер как член группы RTCUniversalServerAdmins или роли **Cs-VoiceAdministrator**, **Cs-ServerAdministrator** или **CsAdministrator**.</span><span class="sxs-lookup"><span data-stu-id="58dd9-122">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the **Cs-VoiceAdministrator**, **Cs-ServerAdministrator**, or **CsAdministrator** role.</span></span>

2.  <span data-ttu-id="58dd9-123">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="58dd9-123">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="58dd9-124">Для всех абонентских групп, у которых не задан регион конференц-связи с телефонным подключением, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="58dd9-124">For any dial plans that are missing the dial-in conferencing region, run:</span></span>
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    <span data-ttu-id="58dd9-125">Например:</span><span class="sxs-lookup"><span data-stu-id="58dd9-125">For example:</span></span>
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    <span data-ttu-id="58dd9-126">В данном примере изменяется абонентская группа с идентификатором Redmond –  для ее свойства DialinConferencingRegion устанавливается значение «US West Coast».</span><span class="sxs-lookup"><span data-stu-id="58dd9-126">In this example, the dial plan with the Identity of Redmond is modified to set the DialinConferencingRegion property to "US West Coast".</span></span> <span data-ttu-id="58dd9-127">Подробные сведения можно найти в руководстве по среде Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="58dd9-127">For details, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

