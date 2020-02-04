---
title: 'Lync Server 2013: создание профилей политики пропускной способности'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d3eef3ea6dfb349f0f712c1127adb8310d90c27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726339"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="f88c8-102">Создание профилей политики пропускной способности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f88c8-102">Create bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f88c8-103">_**Тема последнего изменения:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="f88c8-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="f88c8-p101">*Политики пропускной способности* определяют ограничения пропускной способности сети для режимов передачи звука и видеоизображения в реальном времени. Политики пропускной способности применяются к *профилям политики пропускной способности*, которые могут применяться к нескольким сетевым сайтам для контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="f88c8-p101">*Bandwidth policies* define limitations on bandwidth usage for real-time audio and video modalities. Bandwidth policies are applied to *bandwidth policy profiles*, which can be applied to multiple network sites for call admission control.</span></span>

<span data-ttu-id="f88c8-106">Рекомендации по выбору ограничений пропускной способности, которые следует настроить в развертывании CAC, описаны в разделе [Определение требований к управлению допуском звонков в Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="f88c8-106">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Defining your requirements for call admission control in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="f88c8-107">Дополнительные сведения о работе с политиками пропускной способности и профилями политики можно найти в документации по оболочке Lync Server Management Shell для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="f88c8-107">For details about working with bandwidth policies and policy profiles, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="f88c8-108">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f88c8-108">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="f88c8-109">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f88c8-109">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="f88c8-110">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f88c8-110">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="f88c8-111">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="f88c8-111">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

<span data-ttu-id="f88c8-112">Примеры политик, созданных в следующей процедуре, задают ограничения для общего трафика аудиоданных, отдельных аудиосеансов, общего трафика видеоданных и отдельных видеосеансов.</span><span class="sxs-lookup"><span data-stu-id="f88c8-112">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="f88c8-113">Например, в профиле\_политики пропускной способности связи объемом 5 задаются указанные ниже ограничения.</span><span class="sxs-lookup"><span data-stu-id="f88c8-113">For example, the 5Mb\_Link bandwidth policy profile sets the following limits:</span></span>

  - <span data-ttu-id="f88c8-114">Аудиоданные: 2 000 кбит/с</span><span class="sxs-lookup"><span data-stu-id="f88c8-114">Audio Limit: 2,000 kbps</span></span>

  - <span data-ttu-id="f88c8-115">Аудиосеансы: 200 кбит/с</span><span class="sxs-lookup"><span data-stu-id="f88c8-115">Audio Session Limit: 200 kbps</span></span>

  - <span data-ttu-id="f88c8-116">Видеоданные: 1 400 кбит/с</span><span class="sxs-lookup"><span data-stu-id="f88c8-116">Video Limit: 1,400 kbps</span></span>

  - <span data-ttu-id="f88c8-117">Видеосеансы: 700 кбит/с</span><span class="sxs-lookup"><span data-stu-id="f88c8-117">Video Session Limit: 700 kbps</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="f88c8-p103">Минимальное значение для аудиосеанса 40 кбит/с. Минимальное значение для видеосеанса 100 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="f88c8-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span>



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a><span data-ttu-id="f88c8-120">Создание профилей политики пропускной способности с помощью командной консоли</span><span class="sxs-lookup"><span data-stu-id="f88c8-120">To create bandwidth policy profiles by using Management Shell</span></span>

1.  <span data-ttu-id="f88c8-121">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="f88c8-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="f88c8-122">Выполните командлет New-CsNetworkBandwidthPolicyProfile для каждого создаваемого профиля политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="f88c8-122">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="f88c8-123">Пример:</span><span class="sxs-lookup"><span data-stu-id="f88c8-123">For example, run:</span></span>
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
       ```
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
       ```

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a><span data-ttu-id="f88c8-124">Создание профилей политики пропускной способности с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="f88c8-124">To create bandwidth policy profiles by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="f88c8-125">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f88c8-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="f88c8-126">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="f88c8-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="f88c8-127">В левой области навигации щелкните **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="f88c8-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="f88c8-128">Нажмите кнопку навигации **Профиль политики**.</span><span class="sxs-lookup"><span data-stu-id="f88c8-128">Click the **Policy Profile** navigation button.</span></span>

4.  <span data-ttu-id="f88c8-129">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="f88c8-129">Click **New**.</span></span>

5.  <span data-ttu-id="f88c8-130">На странице **создания профиля политики** в поле щелкните **Имя**, затем введите имя профиля политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="f88c8-130">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>

6.  <span data-ttu-id="f88c8-131">Щелкните **Ограничение для звукового сеанса**, затем введите максимальную скорость в кбит/с, общую для всех сеансов звуковой связи.</span><span class="sxs-lookup"><span data-stu-id="f88c8-131">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>

7.  <span data-ttu-id="f88c8-132">Щелкните **Ограничение для видео**, затем введите максимальную скорость в кбит/с для отдельного сеанса звуковой связи.</span><span class="sxs-lookup"><span data-stu-id="f88c8-132">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>

8.  <span data-ttu-id="f88c8-133">Щелкните **Ограничение для видео**, затем введите максимальную скорость в кбит/с, общую для всех сеансов видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="f88c8-133">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>

9.  <span data-ttu-id="f88c8-134">Щелкните **Ограничение для видеосеанса**, затем введите максимальную скорость в кбит/с для отдельного сеанса видеосвязи.</span><span class="sxs-lookup"><span data-stu-id="f88c8-134">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>

10. <span data-ttu-id="f88c8-135">Щелкните **Описание** и введите дополнительные сведения о профиле политики пропускной способности (не обязательно).</span><span class="sxs-lookup"><span data-stu-id="f88c8-135">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>

11. <span data-ttu-id="f88c8-136">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="f88c8-136">Click **Commit**.</span></span>

12. <span data-ttu-id="f88c8-137">Чтобы завершить создание профилей политики пропускной способности для топологии, повторите шаги с 4 по 11 для остальных профилей политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="f88c8-137">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

