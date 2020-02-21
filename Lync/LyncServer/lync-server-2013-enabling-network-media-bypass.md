---
title: 'Lync Server 2013: Включение обхода сетевых носителей'
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
ms.openlocfilehash: bbabf2f9ccf606fde60409a32872c09d812ffac5
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42207895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="1e81e-102">Включение обхода сетевых носителей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e81e-102">Enabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1e81e-103">_**Последнее изменение темы:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1e81e-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1e81e-104">Параметры обхода сервера мультимедиа применяются глобально в развертывании Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1e81e-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="1e81e-105">Обход сервера-посредника позволяет звонкам обходить сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="1e81e-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="1e81e-106">Сведения о том, когда следует использовать обход сервера мультимедиа, приведены в разделе [Планирование обхода сервера мультимедиа в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) в разделе Планирование.</span><span class="sxs-lookup"><span data-stu-id="1e81e-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="1e81e-107">Вы можете включить и настроить обход сервера мультимедиа в панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1e81e-107">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="1e81e-108">Включение и настройка обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="1e81e-108">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="1e81e-109">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsAdministrator, войдите на любой компьютер во внутреннем развертывании.</span><span class="sxs-lookup"><span data-stu-id="1e81e-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1e81e-110">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1e81e-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1e81e-111">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1e81e-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1e81e-112">На панели навигации слева выберите пункт **Конфигурация сети** и щелкните **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="1e81e-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="1e81e-p103">На странице **Глобальная** выберите конфигурацию **Глобальная**. На этой странице всегда приводится только одна конфигурация, и она всегда имеет название "Глобальная".</span><span class="sxs-lookup"><span data-stu-id="1e81e-p103">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="1e81e-115">В меню **Правка** выберите команду **Показать сведения**.</span><span class="sxs-lookup"><span data-stu-id="1e81e-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="1e81e-116">На странице **Изменение глобального параметра** установите флажок **Включить обход сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="1e81e-116">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="1e81e-117">Выберите один из следующих вариантов.</span><span class="sxs-lookup"><span data-stu-id="1e81e-117">Select one of the following options:</span></span>
    
      - <span data-ttu-id="1e81e-118">**Всегда обходить**   выберите этот параметр, чтобы попытаться обходить мультимедиа во всех вызовах.</span><span class="sxs-lookup"><span data-stu-id="1e81e-118">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="1e81e-119">Этот параметр будет недоступен, если включен контроль допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="1e81e-119">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="1e81e-120">Если параметр CAC не включен, выберите этот параметр в следующих ситуациях:</span><span class="sxs-lookup"><span data-stu-id="1e81e-120">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="1e81e-121">не требуется контроль за пропускной способностью канала;</span><span class="sxs-lookup"><span data-stu-id="1e81e-121">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="1e81e-122">не требуется выполнять сложный контроль, когда должен происходить обход;</span><span class="sxs-lookup"><span data-stu-id="1e81e-122">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="1e81e-123">между клиентами и шлюзами есть подключение.</span><span class="sxs-lookup"><span data-stu-id="1e81e-123">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="1e81e-124">**Использование конфигурации**   сайтов и регионов если включена поддержка CAC, этот параметр выбирается по умолчанию и не может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="1e81e-124">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="1e81e-125">Если выбран этот параметр, сайты и регионы конфигурации сети будут использоваться для определения того, когда возможен обход сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="1e81e-125">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="1e81e-126">При выборе этого параметра можно включить обход для несопоставленных сайтов.</span><span class="sxs-lookup"><span data-stu-id="1e81e-126">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="1e81e-127">Установите флажок **включить обход для несопоставленных сайтов** только в том случае, если у вас есть один или несколько крупных сайтов, связанных с одним и тем же регионом, не имеющим ограничений пропускной способности (например, с большим центральным сайтом), а также с одним регионом, имеющим ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="1e81e-127">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="1e81e-128">При включении обхода для несопоставленных сайтов Настройка упрощается, так как указываются только подсети, связанные с сайтами филиалов, а не требуется указывать все подсети, связанные со всеми сайтами.</span><span class="sxs-lookup"><span data-stu-id="1e81e-128">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="1e81e-129">Рекомендуется не устанавливать флажок **включить обход для несопоставленных сайтов** , если включена функция CAC.</span><span class="sxs-lookup"><span data-stu-id="1e81e-129">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="1e81e-130">Чтобы сохранить изменения, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="1e81e-130">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1e81e-131">См. также</span><span class="sxs-lookup"><span data-stu-id="1e81e-131">See Also</span></span>


[<span data-ttu-id="1e81e-132">Отключение обхода сетевых носителей в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e81e-132">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="1e81e-133">Глобальные параметры обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e81e-133">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="1e81e-134">Планирование обхода сервера мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1e81e-134">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

