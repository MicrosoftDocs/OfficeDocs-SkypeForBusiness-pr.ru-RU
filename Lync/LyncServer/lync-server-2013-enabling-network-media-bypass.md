---
title: 'Lync Server 2013: Включение обхода сетевых мультимедийных файлов'
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
ms.openlocfilehash: 4e0b5e7b060d056a785e80fdf29ded718d120bc1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735799"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="cd41b-102">Включение обхода сетевых мультимедийных файлов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd41b-102">Enabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd41b-103">_**Тема последнего изменения:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="cd41b-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="cd41b-104">Параметры обхода мультимедиа применяются глобально в рамках развертывания Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cd41b-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="cd41b-105">Обойти функцию мультимедиа позволяет обходить сервер.</span><span class="sxs-lookup"><span data-stu-id="cd41b-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="cd41b-106">Сведения о том, когда следует использовать обход мультимедиа, приведены в статье [Планирование обхода мультимедиа в Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) в разделе Планирование.</span><span class="sxs-lookup"><span data-stu-id="cd41b-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="cd41b-107">Вы можете включить и настроить обход мультимедиа с помощью панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cd41b-107">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="cd41b-108">Включение и Настройка обхода мультимедиа</span><span class="sxs-lookup"><span data-stu-id="cd41b-108">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="cd41b-109">Войдите на любой компьютер, находящийся во внутреннем развертывании, с использованием учетной записи, входящей в группу RTCUniversalServerAdmins (или имеющей равнозначные права пользователя) либо назначенной роли CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="cd41b-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="cd41b-110">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cd41b-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cd41b-111">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cd41b-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="cd41b-112">На панели навигации слева выберите пункт **Конфигурация сети** , а затем — **Глобальная**.</span><span class="sxs-lookup"><span data-stu-id="cd41b-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="cd41b-113">На **глобальной** странице щелкните **глобальную** конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="cd41b-113">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="cd41b-114">Всегда существует только одна конфигурация, и она всегда имеет имя Global.</span><span class="sxs-lookup"><span data-stu-id="cd41b-114">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="cd41b-115">В меню **Правка** выберите команду **Просмотреть сведения**.</span><span class="sxs-lookup"><span data-stu-id="cd41b-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="cd41b-116">На странице " **изменение глобальных параметров** " установите флажок **включить обход мультимедиа** .</span><span class="sxs-lookup"><span data-stu-id="cd41b-116">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="cd41b-117">Выберите один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="cd41b-117">Select one of the following options:</span></span>
    
      - <span data-ttu-id="cd41b-118">**Всегда не использовать**   . Выберите этот параметр, чтобы попытаться обойти все звонки мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="cd41b-118">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="cd41b-119">Этот параметр будет недоступен, если включен элемент управления допуском звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="cd41b-119">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="cd41b-120">Если функция CAC не включена, выберите этот параметр в указанных ниже случаях.</span><span class="sxs-lookup"><span data-stu-id="cd41b-120">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="cd41b-121">Контроль за пропускной способностью не требуется.</span><span class="sxs-lookup"><span data-stu-id="cd41b-121">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="cd41b-122">Не нужно детально настраивать конфигурацию, чтобы определить, когда должно происходить обход.</span><span class="sxs-lookup"><span data-stu-id="cd41b-122">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="cd41b-123">Существует полная связь между шлюзами и клиентами.</span><span class="sxs-lookup"><span data-stu-id="cd41b-123">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="cd41b-124">**Использование сайтов и конфигурации**   областей если включена функция CAC, этот параметр установлен по умолчанию и не может быть изменен.</span><span class="sxs-lookup"><span data-stu-id="cd41b-124">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="cd41b-125">Если выбран этот параметр, сайты и регионы настройки сети будут использоваться для определения способа обхода мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="cd41b-125">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="cd41b-126">Если выбрать этот параметр, вы можете включить обход для несопоставленных сайтов.</span><span class="sxs-lookup"><span data-stu-id="cd41b-126">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="cd41b-127">Установите флажок **Разрешить игнорировать для несопоставленных сайтов** только в том случае, если у вас есть один или несколько крупных сайтов, связанных с тем же регионом, но не пропускаемых ограничений (например, для крупного центрального сайта), а также есть некоторые сайты филиалов, связанные с тем же регионом, в котором есть ограничения пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="cd41b-127">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="cd41b-128">При включении обхода для несопоставленных сайтов Настройка оптимизируется, так как вы указываете только подсети, связанные с сайтами филиалов, а не необходимость указывать все подсети, связанные со всеми сайтами.</span><span class="sxs-lookup"><span data-stu-id="cd41b-128">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="cd41b-129">Мы рекомендуем не устанавливать флажок **включить обход для несопоставленных сайтов** , если включен параметр CAC.</span><span class="sxs-lookup"><span data-stu-id="cd41b-129">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="cd41b-130">Нажмите **кнопку Сохранить,** чтобы сохранить изменения.</span><span class="sxs-lookup"><span data-stu-id="cd41b-130">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="cd41b-131">См. также</span><span class="sxs-lookup"><span data-stu-id="cd41b-131">See Also</span></span>


[<span data-ttu-id="cd41b-132">Отключение обхода сетевых мультимедийных файлов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd41b-132">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="cd41b-133">Глобальные параметры обхода мультимедиа в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd41b-133">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="cd41b-134">Планирование обхода серверов-посредников в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd41b-134">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

