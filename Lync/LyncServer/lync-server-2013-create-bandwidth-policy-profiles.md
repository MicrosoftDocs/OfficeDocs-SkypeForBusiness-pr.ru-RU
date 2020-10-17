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
ms.openlocfilehash: 173f63fce60215ca0bc68791b0bc051136d931a4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501706"
---
# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="54f55-102">Создание профилей политики пропускной способности в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="54f55-102">Create bandwidth policy profiles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="54f55-103">_**Последнее изменение темы:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="54f55-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="54f55-p101">*Политики пропускной способности* задают ограничения пропускной способности сети для режимов передачи аудио и видеоданных в реальном времени. Политики пропускной способности применяются к *профилям политики пропускной способности*, которые могут применяться к нескольким сетевым узлам для контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="54f55-p101">*Bandwidth policies* define limitations on bandwidth usage for real-time audio and video modalities. Bandwidth policies are applied to *bandwidth policy profiles*, which can be applied to multiple network sites for call admission control.</span></span>

<span data-ttu-id="54f55-106">Инструкции по использованию пределов пропускной способности, которые необходимо задать в развертывании CAC, приведены в статье [Определение требований для контроля допуска звонков в Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="54f55-106">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Defining your requirements for call admission control in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="54f55-107">Для получения подробных сведений о работе с политиками пропускной способности и профилями политики обратитесь к документации по командной консоли Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="54f55-107">For details about working with bandwidth policies and policy profiles, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="54f55-108">New — CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="54f55-108">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="54f55-109">Get — CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="54f55-109">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="54f55-110">Set — CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="54f55-110">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="54f55-111">Remove — CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="54f55-111">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

<span data-ttu-id="54f55-112">Примеры политик, созданных в следующей процедуре, задают ограничения для общего трафика аудиоданных, отдельных аудиосеансов, общего трафика видеоданных и отдельных видеосеансов.</span><span class="sxs-lookup"><span data-stu-id="54f55-112">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="54f55-113">Например, \_ профиль политики пропускной способности канала 5 в определяет следующие пределы:</span><span class="sxs-lookup"><span data-stu-id="54f55-113">For example, the 5Mb\_Link bandwidth policy profile sets the following limits:</span></span>

  - <span data-ttu-id="54f55-114">Аудиоданные: 2 000 кбит/с</span><span class="sxs-lookup"><span data-stu-id="54f55-114">Audio Limit: 2,000 kbps</span></span>

  - <span data-ttu-id="54f55-115">Аудиосеансы: 200 кбит/с</span><span class="sxs-lookup"><span data-stu-id="54f55-115">Audio Session Limit: 200 kbps</span></span>

  - <span data-ttu-id="54f55-116">Видеоданные: 1 400 кбит/с</span><span class="sxs-lookup"><span data-stu-id="54f55-116">Video Limit: 1,400 kbps</span></span>

  - <span data-ttu-id="54f55-117">Видеосеансы: 700 кбит/с</span><span class="sxs-lookup"><span data-stu-id="54f55-117">Video Session Limit: 700 kbps</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="54f55-p103">Минимальное значение для аудиосеанса 40 кбит/с. Минимальное значение для видеосеанса 100 кбит/с.</span><span class="sxs-lookup"><span data-stu-id="54f55-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span>



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a><span data-ttu-id="54f55-120">Создание профилей политики пропускной способности с помощью командной консоли</span><span class="sxs-lookup"><span data-stu-id="54f55-120">To create bandwidth policy profiles by using Management Shell</span></span>

1.  <span data-ttu-id="54f55-121">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="54f55-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="54f55-p104">Выполните командлет New-CsNetworkBandwidthPolicyProfile для каждого создаваемого профиля политики пропускной способности. Пример:</span><span class="sxs-lookup"><span data-stu-id="54f55-p104">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet. For example, run:</span></span>
    
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

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a><span data-ttu-id="54f55-124">Создание профилей политики пропускной способности с помощью панели управления Lync Server</span><span class="sxs-lookup"><span data-stu-id="54f55-124">To create bandwidth policy profiles by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="54f55-125">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="54f55-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="54f55-126">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="54f55-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="54f55-127">В левой панели навигации щелкните **Network Configuration** (Параметры сети).</span><span class="sxs-lookup"><span data-stu-id="54f55-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="54f55-128">Нажмите кнопку навигации **Policy Profile** (Профиль политики).</span><span class="sxs-lookup"><span data-stu-id="54f55-128">Click the **Policy Profile** navigation button.</span></span>

4.  <span data-ttu-id="54f55-129">Щелкните **New** (Создать).</span><span class="sxs-lookup"><span data-stu-id="54f55-129">Click **New**.</span></span>

5.  <span data-ttu-id="54f55-130">На странице **New Policy Profile** (Создание профиля политики) введите имя профиля политики пропускной способности в поле **Name** (Имя).</span><span class="sxs-lookup"><span data-stu-id="54f55-130">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>

6.  <span data-ttu-id="54f55-131">Щелкните **Audio limit** (Ограничение для аудиоданных) и затем введите максимальную скорость (кбит/с) для всех аудиосеансов.</span><span class="sxs-lookup"><span data-stu-id="54f55-131">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>

7.  <span data-ttu-id="54f55-132">Щелкните **Audio session limit** (Ограничение для аудиосеанса) и затем введите максимальную скорость (кбит/с) для отдельного аудиосеанса.</span><span class="sxs-lookup"><span data-stu-id="54f55-132">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>

8.  <span data-ttu-id="54f55-133">Щелкните **Video limit** (Ограничение для видеоданных) и затем введите максимальную скорость (кбит/с) для всех видеосеансов.</span><span class="sxs-lookup"><span data-stu-id="54f55-133">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>

9.  <span data-ttu-id="54f55-134">Щелкните **Video session limit** (Ограничение для видеосеанса) и затем введите максимальную скорость (кбит/с) для отдельного видеосеанса.</span><span class="sxs-lookup"><span data-stu-id="54f55-134">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>

10. <span data-ttu-id="54f55-135">В поле **Description** (Описание) введите дополнительные сведения о профиле политики пропускной способности (необязательно).</span><span class="sxs-lookup"><span data-stu-id="54f55-135">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>

11. <span data-ttu-id="54f55-136">Щелкните **Commit** (Применить).</span><span class="sxs-lookup"><span data-stu-id="54f55-136">Click **Commit**.</span></span>

12. <span data-ttu-id="54f55-137">Чтобы завершить создание профилей политики пропускной способности для топологии, повторите шаги с 4 по 11 для остальных профилей политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="54f55-137">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

