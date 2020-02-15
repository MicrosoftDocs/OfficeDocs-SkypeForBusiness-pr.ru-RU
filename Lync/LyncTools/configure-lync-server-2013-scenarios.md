---
title: Настройка сценариев Lync Server 2013
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
ms.openlocfilehash: 60da62851580487ea04dd1797ed91a1f8acd251b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036167"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-lync-server-2013-scenarios"></a><span data-ttu-id="97898-102">Настройка сценариев Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97898-102">Configure Lync Server 2013 Scenarios</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97898-103">_**Последнее изменение темы:** 2016-12-28_</span><span class="sxs-lookup"><span data-stu-id="97898-103">_**Topic Last Modified:** 2016-12-28_</span></span>

<span data-ttu-id="97898-104">Для запуска средства нагрузки и производительности Lync Server 2013 (Линкперфтул) сначала необходимо настроить топологию Lync Server 2013, чтобы выполнить сценарии, которые будут выполняться.</span><span class="sxs-lookup"><span data-stu-id="97898-104">To run the Lync Server 2013 Stress and Performance Tool (LyncPerfTool), the Lync Server 2013 topology must first be configured for the scenarios that will be executed.</span></span> <span data-ttu-id="97898-105">Если Lync Server 2013 не настроен или настроен неправильно, в большинстве случаев произойдет ошибка моделирования нагрузки.</span><span class="sxs-lookup"><span data-stu-id="97898-105">If Lync Server 2013 is not configured or is configured incorrectly, load simulation will fail in most cases.</span></span> <span data-ttu-id="97898-106">С помощью средства нагрузки и производительности Lync Server 2013 мы предоставили примеры сценариев командной консоли Lync Server и базовых файлов ресурсов, которые можно использовать в качестве отправной точки для настройки Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="97898-106">With the Lync Server 2013 Stress and Performance Tool, we have provided example Lync Server Management Shell scripts and basic resource files that can be used as a starting point for configuring Lync Server 2013.</span></span> <span data-ttu-id="97898-107">В этом разделе описываются приведенные примеры Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="97898-107">This topic describes the Windows PowerShell examples provided.</span></span> <span data-ttu-id="97898-108">Обратите внимание, что в этом разделе нет цели, описывающих, как настроить Lync Server 2013 в целом.</span><span class="sxs-lookup"><span data-stu-id="97898-108">Note that it is not the goal of this topic to describe how to configure Lync Server 2013 in general.</span></span> <span data-ttu-id="97898-109">Подробные сведения о работе с Windows PowerShell в Lync Server 2013 можно найти в документации по консоли управления Lync Server <https://technet.microsoft.com/library/gg398474.aspx>по адресу:.</span><span class="sxs-lookup"><span data-stu-id="97898-109">For details about working with Windows PowerShell in Lync Server 2013, see the Lync Server Management Shell documentation at <https://technet.microsoft.com/library/gg398474.aspx>.</span></span>

<div>

## <a name="about-running-lync-server-management-shell-scripts"></a><span data-ttu-id="97898-110">Сведения о выполнении сценариев командной консоли Lync Server</span><span class="sxs-lookup"><span data-stu-id="97898-110">About Running Lync Server Management Shell Scripts</span></span>

<span data-ttu-id="97898-111">Мы предоставили примеры сценариев командной консоли Lync Server, которые можно использовать при подготовке к запуску нагрузочного моделирования.</span><span class="sxs-lookup"><span data-stu-id="97898-111">We have provided example Lync Server Management Shell scripts that may be used in preparation for running load simulation.</span></span> <span data-ttu-id="97898-112">Так как сценарии предназначены для имитации нагрузки, они просты и отличаются, поэтому могут быть не подходящими для рабочей среды.</span><span class="sxs-lookup"><span data-stu-id="97898-112">Because the scripts are intended for load simulation, they are simple and permissive, and therefore may not be appropriate for production.</span></span> <span data-ttu-id="97898-113">Все скрипты являются примерами и должны быть просмотрены, а в некоторых случаях изменены в соответствии с топологией.</span><span class="sxs-lookup"><span data-stu-id="97898-113">All scripts are examples and must be reviewed, and, in some cases, modified to reflect your topology.</span></span> <span data-ttu-id="97898-114">Как минимум, ожидается, что сценарий службы группы ответа (RGS) потребуется изменить, чтобы указать агенты, назначенные группам агентов.</span><span class="sxs-lookup"><span data-stu-id="97898-114">At a minimum, we expect that the Response Group Service (RGS) scenario would need to be modified to specify the agents that are assigned to the agent groups.</span></span> <span data-ttu-id="97898-115">Тем не менее, вы можете не имитировать эту нагрузку.</span><span class="sxs-lookup"><span data-stu-id="97898-115">However, you have the option to not simulate this load.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="97898-116">Будьте внимательны и ознакомьтесь с представленными примерами.</span><span class="sxs-lookup"><span data-stu-id="97898-116">Take care in reviewing and understanding the examples provided.</span></span> <span data-ttu-id="97898-117">Сценарии заменят все существующие параметры в топологии.</span><span class="sxs-lookup"><span data-stu-id="97898-117">Scripts will overwrite any existing settings in the topology.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="97898-118">Для получения дополнительных сведений об использовании Windows PowerShell и командной консоли Lync Server обратитесь к блогу Lync Server 2013 Windows PowerShell <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>по адресу.</span><span class="sxs-lookup"><span data-stu-id="97898-118">For details about using Windows PowerShell and the Lync Server Management Shell, see the Lync Server 2013 Windows PowerShell Blog at <A href="https://go.microsoft.com/fwlink/?linkid=203150">https://go.microsoft.com/fwlink/?LinkId=203150</A>.</span></span>



</div>

</div>

<div>

## <a name="stress-and-performance-tool-client-version-monikers"></a><span data-ttu-id="97898-119">Специальные имена клиента средства нагрузки и производительности</span><span class="sxs-lookup"><span data-stu-id="97898-119">Stress and Performance Tool Client Version Monikers</span></span>

<span data-ttu-id="97898-120">Если вы изменили параметры из значений по умолчанию, может потребоваться настроить политику проверки версий клиентов.</span><span class="sxs-lookup"><span data-stu-id="97898-120">You may need to configure the Client Version Check policy if you have changed the settings from the default values.</span></span> <span data-ttu-id="97898-121">Дополнительные сведения см. в <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>разделе "Настройка поддерживаемых версий клиентов".</span><span class="sxs-lookup"><span data-stu-id="97898-121">For details, see “Configuring supported client versions” at <https://technet.microsoft.com/library/gg412832(v=ocs.15).aspx>.</span></span> <span data-ttu-id="97898-122">При обмене данными с Lync Server 2013 средство нагрузки и производительности Lync Server 2013 по умолчанию использует следующие версии агента пользователя:</span><span class="sxs-lookup"><span data-stu-id="97898-122">The Lync Server 2013 Stress and Performance Tool uses the following User Agent Versions by default when communicating with Lync Server 2013:</span></span>

  - <span data-ttu-id="97898-123">ЛСПТ/15.0.0.0 (средство тестирования нагрузки и производительности Lync Server 2013)</span><span class="sxs-lookup"><span data-stu-id="97898-123">LSPT/15.0.0.0 (Lync Server 2013 Stress and Performance Tool)</span></span>

  - <span data-ttu-id="97898-124">ОКФОНЕ/. 0.522</span><span class="sxs-lookup"><span data-stu-id="97898-124">OCPHONE/.0.522</span></span>

<span data-ttu-id="97898-125">Они предназначены для клиента Mobility (UCWA) в Линкперфтул:</span><span class="sxs-lookup"><span data-stu-id="97898-125">These are for the Mobility (UCWA) client in LyncPerfTool:</span></span>

  - <span data-ttu-id="97898-126">Средство производительности Ucwa/веб-конференция</span><span class="sxs-lookup"><span data-stu-id="97898-126">Ucwa Perf Tool/Web Conference</span></span>

  - <span data-ttu-id="97898-127">Ucwa Perf Tool/Mobile</span><span class="sxs-lookup"><span data-stu-id="97898-127">Ucwa Perf Tool/Mobile</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

