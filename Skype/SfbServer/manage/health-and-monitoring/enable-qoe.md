---
title: Включить качество работы в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: Сводка. Узнайте, как включить качество работы (QoE) в Skype для бизнеса Server.
ms.openlocfilehash: 9f3e032506641cd22fbaa78054fcf6e40a72665e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095213"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="234ef-103">Включить качество работы в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="234ef-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="234ef-104">**Сводка.** Узнайте, как включить качество работы (QoE) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="234ef-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="234ef-105">Служба качества взаимодействия (QoE) записывает числовые данные, которые показывают качество мультимедиа-данных, и сведения об участниках, именах устройств, драйверах, IP-адресах и типах конечных точек, использованных во время звонка или сеанса.</span><span class="sxs-lookup"><span data-stu-id="234ef-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="234ef-106">Подробные сведения см. в разделе [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="234ef-106">For details, see [Planning for Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring) in the Planning documentation.</span></span>

<span data-ttu-id="234ef-107">Используйте следующую процедуру для включения службы качества взаимодействия для всей организации или для отдельных сайтов в организации.</span><span class="sxs-lookup"><span data-stu-id="234ef-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="234ef-108">Чтобы включить службу качества взаимодействия, сначала необходимо настроить мониторинг и внутреннюю базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="234ef-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="234ef-109">Дополнительные сведения см. в разделе [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span><span class="sxs-lookup"><span data-stu-id="234ef-109">For details, see [Deploying Monitoring](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="234ef-110">Чтобы включить QoE с помощью панели управления Skype для бизнес-серверов</span><span class="sxs-lookup"><span data-stu-id="234ef-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="234ef-111">С учетной записи пользователя, которая входит в группу RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначена роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в которой развернут Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="234ef-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="234ef-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнес-серверов.</span><span class="sxs-lookup"><span data-stu-id="234ef-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="234ef-113">В левой навигационной панели щелкните элемент **Мониторинг и архивация** и выберите пункт **Quality of Experience Data** (Данные качества взаимодействия).</span><span class="sxs-lookup"><span data-stu-id="234ef-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="234ef-114">На странице **данных качества взаимодействия** щелкните соответствующую коллекцию в таблице и последовательно выберите пункты **Action** (Действие) и **Enable QoE** (Включить QoE).</span><span class="sxs-lookup"><span data-stu-id="234ef-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="234ef-115">Включение QoE с помощью Windows PowerShell cmdlets</span><span class="sxs-lookup"><span data-stu-id="234ef-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="234ef-116">Включить QoE можно с помощью Windows PowerShell **и комлета Set-CsQoEConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="234ef-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="234ef-117">Этот комлет можно выполнить либо из оболочки управления skype для бизнес-серверов, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="234ef-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="234ef-118">Сведения об использовании удаленных Windows PowerShell для подключения к Skype для бизнеса Server см. в статье блога ["Быстрый запуск: управление Microsoft Lync Server 2010 с](https://go.microsoft.com/fwlink/p/?linkId=255876)помощью удаленной powerShell".</span><span class="sxs-lookup"><span data-stu-id="234ef-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="234ef-119">В Skype для бизнеса Server этот процесс является одинаковым.</span><span class="sxs-lookup"><span data-stu-id="234ef-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="234ef-120">Включение службы качества взаимодействия для одного расположения</span><span class="sxs-lookup"><span data-stu-id="234ef-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="234ef-121">Чтобы включить службу качества взаимодействия, установите параметр EnableQoE в значение True ($True).</span><span class="sxs-lookup"><span data-stu-id="234ef-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="234ef-122">Отключение службы качества взаимодействия для одного расположения</span><span class="sxs-lookup"><span data-stu-id="234ef-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="234ef-p104">Чтобы отключить службу качества взаимодействия, установите параметр EnableQoE в значение False ($False). При этом мониторинг не будет удален. Он приостановит сбор и хранение данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="234ef-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="234ef-126">Использование одной команды для включения службы качества взаимодействия в нескольких расположениях</span><span class="sxs-lookup"><span data-stu-id="234ef-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="234ef-127">Следующая команда включает службу качества взаимодействия для всех параметров конфигурации качества взаимодействия, используемых в текущий момент в организации.</span><span class="sxs-lookup"><span data-stu-id="234ef-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="234ef-128">Подробные сведения [см. в материале Set-CsQoEConfiguration.](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="234ef-128">For details, see [Set-CsQoEConfiguration](/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="234ef-129">См. также</span><span class="sxs-lookup"><span data-stu-id="234ef-129">See also</span></span>

[<span data-ttu-id="234ef-130">Планирование мониторинга</span><span class="sxs-lookup"><span data-stu-id="234ef-130">Planning for Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-monitoring)

[<span data-ttu-id="234ef-131">Мониторинг развертывания</span><span class="sxs-lookup"><span data-stu-id="234ef-131">Deploying Monitoring</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-monitoring)