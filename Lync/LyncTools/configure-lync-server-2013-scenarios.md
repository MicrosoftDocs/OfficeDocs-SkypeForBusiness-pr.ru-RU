---
title: Настройка сценариев Lync Server 2013
description: Настройка сценариев Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure Lync Server 2013 Scenarios
ms:assetid: 6705346b-1512-4af3-85e4-64dfa6ee6f80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945596(v=OCS.15)
ms:contentKeyID: 51541420
ms.date: 12/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c4a5b7bd271191067779ac358807cc54918b16bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555465"
---
# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="4cb68-103">Настройка сценариев Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cb68-103">Configure Lync Server 2013 Scenarios</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cb68-104">_**Последнее изменение темы:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="4cb68-104">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="4cb68-105">Для запуска средства нагрузки и производительности Lync Server 2013 (Линкперфтул) сначала необходимо настроить топологию Lync Server 2013, чтобы выполнить сценарии, которые будут выполняться.</span><span class="sxs-lookup"><span data-stu-id="4cb68-105">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="4cb68-106">Если Lync Server 2013 не настроен или настроен неправильно, в большинстве случаев произойдет ошибка моделирования нагрузки.</span><span class="sxs-lookup"><span data-stu-id="4cb68-106">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="4cb68-107">С помощью средства нагрузки и производительности Lync Server 2013 мы предоставили примеры сценариев командной консоли Lync Server и базовых файлов ресурсов, которые можно использовать в качестве отправной точки для настройки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4cb68-107">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="4cb68-108">В этом разделе описываются приведенные примеры Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4cb68-108">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="4cb68-109">Обратите внимание, что в этом разделе нет цели, описывающих, как настроить Lync Server 2013 в целом.</span><span class="sxs-lookup"><span data-stu-id="4cb68-109">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="4cb68-110">Подробные сведения о работе с Windows PowerShell в Lync Server 2013 можно найти в документации по консоли управления Lync Server по адресу <https://technet.microsoft.com/library/gg398474.aspx> :.</span><span class="sxs-lookup"><span data-stu-id="4cb68-110">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="4cb68-111">Сведения о выполнении сценариев командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="4cb68-111">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="4cb68-112">Мы предоставили примеры сценариев командной консоли Lync Server, которые можно использовать при подготовке к запуску нагрузочного моделирования.</span><span class="sxs-lookup"><span data-stu-id="4cb68-112">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="4cb68-113">Так как сценарии предназначены для имитации нагрузки, они просты и отличаются, поэтому могут быть не подходящими для рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="4cb68-113">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="4cb68-114">Все скрипты являются примерами и должны быть просмотрены, а в некоторых случаях изменены в соответствии с топологией.</span><span class="sxs-lookup"><span data-stu-id="4cb68-114">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="4cb68-115">Как минимум, ожидается, что сценарий службы группы ответа (RGS) потребуется изменить, чтобы указать агенты, назначенные группам агентов.</span><span class="sxs-lookup"><span data-stu-id="4cb68-115">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="4cb68-116">Тем не менее, вы можете не имитировать эту нагрузку.</span><span class="sxs-lookup"><span data-stu-id="4cb68-116">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="4cb68-117">Будьте внимательны и ознакомьтесь с представленными примерами.</span><span class="sxs-lookup"><span data-stu-id="4cb68-117">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="4cb68-118">Сценарии заменят все существующие параметры в топологии.</span><span class="sxs-lookup"><span data-stu-id="4cb68-118">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="4cb68-119">Для получения дополнительных сведений об использовании Windows PowerShell и командной консоли Lync Server обратитесь к блогу Lync Server 2013 Windows PowerShell по адресу <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A> .</span><span class="sxs-lookup"><span data-stu-id="4cb68-119">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="4cb68-120">Специальные имена клиента средства нагрузки и производительности</span><span class="sxs-lookup"><span data-stu-id="4cb68-120">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="4cb68-121">Если вы изменили параметры из значений по умолчанию, может потребоваться настроить политику проверки версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="4cb68-121">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="4cb68-122">Дополнительные сведения см. в разделе "Настройка поддерживаемых версий клиентов" <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx> .</span><span class="sxs-lookup"><span data-stu-id="4cb68-122">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="4cb68-123">При обмене данными с Lync Server 2013 средство нагрузки и производительности Lync Server 2013 по умолчанию использует следующие версии агента пользователя:</span><span class="sxs-lookup"><span data-stu-id="4cb68-123">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="4cb68-124">ЛСПТ/15.0.0.0 (средство тестирования нагрузки и производительности Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="4cb68-124">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="4cb68-125">ОКФОНЕ/. 0.522</span><span class="sxs-lookup"><span data-stu-id="4cb68-125">OCPHONE/.0.522</span></span>

<span data-ttu-id="4cb68-126">Они предназначены для клиента Mobility (UCWA) в Линкперфтул:</span><span class="sxs-lookup"><span data-stu-id="4cb68-126">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="4cb68-127">Средство производительности Ucwa/веб-конференция</span><span class="sxs-lookup"><span data-stu-id="4cb68-127">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="4cb68-128">Ucwa Perf Tool/Mobile</span><span class="sxs-lookup"><span data-stu-id="4cb68-128">Ucwa Perf Tool/Mobile</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

