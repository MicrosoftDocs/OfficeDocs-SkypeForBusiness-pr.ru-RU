---
title: 'Lync Server 2013: Включение обхода сетевых носителей'
description: 'Lync Server 2013: Включение обхода сетевых носителей.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1218376903aa42e1ea55205e3a9e8d16aade9a3a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546555"
---
# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="a76d3-103">Включение обхода сетевых носителей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a76d3-103">Enabling network media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a76d3-104">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="a76d3-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="a76d3-105">Параметры обхода сервера мультимедиа применяются глобально в развертывании Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a76d3-105">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="a76d3-106">Обход сервера-посредника позволяет звонкам обходить сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="a76d3-106">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="a76d3-107">Сведения о том, когда следует использовать обход сервера мультимедиа, приведены в разделе [Планирование обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) в разделе Планирование.</span><span class="sxs-lookup"><span data-stu-id="a76d3-107">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="a76d3-108">Вы можете включить и настроить обход сервера мультимедиа в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a76d3-108">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="a76d3-109">Включение и настройка обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="a76d3-109">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="a76d3-110">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="a76d3-110">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="a76d3-111">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="a76d3-111">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="a76d3-112">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="a76d3-112">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="a76d3-113">На панели навигации слева выберите пункт **Конфигурация сети** и щелкните **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="a76d3-113">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="a76d3-p103">На странице **Глобальная** выберите конфигурацию **Глобальная**. На этой странице всегда приводится только одна конфигурация, и она всегда имеет название "Глобальная".</span><span class="sxs-lookup"><span data-stu-id="a76d3-p103">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="a76d3-116">В меню **Правка** выберите команду **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="a76d3-116">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="a76d3-117">На странице **Изменение глобального параметра** установите флажок **Включить обход сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="a76d3-117">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="a76d3-118">Выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="a76d3-118">Select one of the following options:</span></span>
    
      - <span data-ttu-id="a76d3-119">**Всегда обходить**     Выберите этот параметр, чтобы попытаться обходить мультимедиа по всем вызовам.</span><span class="sxs-lookup"><span data-stu-id="a76d3-119">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="a76d3-120">Этот параметр будет недоступен, если включен контроль допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="a76d3-120">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="a76d3-121">Если параметр CAC не включен, выберите этот параметр в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="a76d3-121">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="a76d3-122">не требуется контроль за пропускной способностью канала;</span><span class="sxs-lookup"><span data-stu-id="a76d3-122">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="a76d3-123">не требуется выполнять сложный контроль, когда должен происходить обход;</span><span class="sxs-lookup"><span data-stu-id="a76d3-123">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="a76d3-124">между клиентами и шлюзами есть подключение.</span><span class="sxs-lookup"><span data-stu-id="a76d3-124">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="a76d3-125">**Использование конфигурации**     сайтов и регионов Если включена поддержка контроля допуска звонков, этот параметр выбирается по умолчанию и не может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="a76d3-125">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="a76d3-126">Если выбран этот параметр, сайты и регионы конфигурации сети будут использоваться для определения того, когда возможен обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="a76d3-126">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="a76d3-127">При выборе этого параметра можно включить обход для несопоставленных сайтов.</span><span class="sxs-lookup"><span data-stu-id="a76d3-127">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="a76d3-128">Установите флажок **включить обход для несопоставленных сайтов** только в том случае, если у вас есть один или несколько крупных сайтов, связанных с одним и тем же регионом, не имеющим ограничений пропускной способности (например, с большим центральным сайтом), а также с одним регионом, имеющим ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="a76d3-128">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="a76d3-129">При включении обхода для несопоставленных сайтов Настройка упрощается, так как указываются только подсети, связанные с сайтами филиалов, а не требуется указывать все подсети, связанные со всеми сайтами.</span><span class="sxs-lookup"><span data-stu-id="a76d3-129">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="a76d3-130">Рекомендуется не устанавливать флажок **включить обход для несопоставленных сайтов** , если включена функция CAC.</span><span class="sxs-lookup"><span data-stu-id="a76d3-130">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="a76d3-131">Чтобы сохранить изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="a76d3-131">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a76d3-132">См. также</span><span class="sxs-lookup"><span data-stu-id="a76d3-132">See Also</span></span>


[<span data-ttu-id="a76d3-133">Отключение обхода сетевых носителей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a76d3-133">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="a76d3-134">Глобальные параметры обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a76d3-134">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="a76d3-135">Планирование обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a76d3-135">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

