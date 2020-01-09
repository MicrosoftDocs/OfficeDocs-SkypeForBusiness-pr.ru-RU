---
title: Обеспечение качества взаимодействия в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Сводка: сведения о том, как включить качество взаимодействия (QoE) в Skype для бизнеса Server.'
ms.openlocfilehash: 0a05266ed88b9d476ca787f1d32b91727e90475c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992939"
---
# <a name="enable-quality-of-experience-in-skype-for-business-server"></a><span data-ttu-id="6ce3e-103">Обеспечение качества взаимодействия в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6ce3e-103">Enable Quality of Experience in Skype for Business Server</span></span>

<span data-ttu-id="6ce3e-104">**Сводка:** сведения о том, как включить качество взаимодействия (QoE) в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6ce3e-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server.</span></span>

<span data-ttu-id="6ce3e-p101">Служба отслеживания качества взаимодействия (QoE) записывает числовые данные, которые показывают качество мультимедиа-данных, и сведения об участниках, именах устройств, драйверах, IP-адресах и типах конечных точек, использованных во время звонка или сеанса. Подробные сведения см. в разделе [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="6ce3e-p101">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions. For details, see [Planning for Monitoring](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation.</span></span>

<span data-ttu-id="6ce3e-107">Используйте следующую процедуру для включения службы качества взаимодействия для всей организации или для отдельных сайтов в организации.</span><span class="sxs-lookup"><span data-stu-id="6ce3e-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="6ce3e-p102">Чтобы включить службу качества взаимодействия, сначала необходимо настроить мониторинг и внутреннюю базу данных мониторинга. Дополнительные сведения см. в разделе [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="6ce3e-p102">To enable QoE, you must first configure monitoring and a monitoring back-end database. For details, see [Deploying Monitoring](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span>

### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="6ce3e-110">Включение QoE с помощью панели управления Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="6ce3e-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="6ce3e-111">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, войдя на любой компьютер в сети, в которой вы развернули Skype для бизнеса Server. .</span><span class="sxs-lookup"><span data-stu-id="6ce3e-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server.</span></span>

2. <span data-ttu-id="6ce3e-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6ce3e-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="6ce3e-113">На панели навигации слева нажмите **Мониторинг и архивация**, затем выберите **Данные о качестве взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="6ce3e-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span>

4. <span data-ttu-id="6ce3e-114">На странице **данных качества взаимодействия** выберите соответствующую коллекцию в таблице и последовательно выберите пункты **Действие** и **Включить отслеживание качества взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="6ce3e-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>

## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="6ce3e-115">Включение QoE с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6ce3e-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="6ce3e-116">Вы можете включить QoE с помощью Windows PowerShell и командлета **Set-кскоеконфигуратион** .</span><span class="sxs-lookup"><span data-stu-id="6ce3e-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="6ce3e-117">Этот командлет можно выполнить либо из командной консоли Skype для бизнеса Server, либо из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ce3e-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="6ce3e-118">Дополнительные сведения об использовании удаленной оболочки Windows PowerShell для подключения к серверу Skype для бизнеса можно найти в статье ["Краткое руководство": Управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="6ce3e-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="6ce3e-119">Этот процесс одинаков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="6ce3e-119">The process is the same in Skype for Business Server.</span></span>

### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="6ce3e-120">Включение службы качества взаимодействия для одного расположения</span><span class="sxs-lookup"><span data-stu-id="6ce3e-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="6ce3e-121">Чтобы включить службу качества взаимодействия, установите параметр EnableQoE в значение True ($True).</span><span class="sxs-lookup"><span data-stu-id="6ce3e-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="6ce3e-122">Отключение службы качества взаимодействия для одного расположения</span><span class="sxs-lookup"><span data-stu-id="6ce3e-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="6ce3e-p104">Чтобы отключить службу качества взаимодействия, установите параметр EnableQoE в значение False ($False). При этом мониторинг не будет удален. Он приостановит сбор и хранение данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="6ce3e-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>

  ```PowerShell
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="6ce3e-126">Использование одной команды для включения службы качества взаимодействия в нескольких расположениях</span><span class="sxs-lookup"><span data-stu-id="6ce3e-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="6ce3e-127">Следующая команда включает службу качества взаимодействия для всех параметров конфигурации качества взаимодействия, используемых в текущий момент в организации.</span><span class="sxs-lookup"><span data-stu-id="6ce3e-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>

  ```PowerShell
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="6ce3e-128">Подробности можно найти в разделе [Set-кскоеконфигуратион](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="6ce3e-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>

## <a name="see-also"></a><span data-ttu-id="6ce3e-129">См. также</span><span class="sxs-lookup"><span data-stu-id="6ce3e-129">See also</span></span>

[<span data-ttu-id="6ce3e-130">Планирование мониторинга</span><span class="sxs-lookup"><span data-stu-id="6ce3e-130">Planning for Monitoring</span></span>](https://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)

[<span data-ttu-id="6ce3e-131">Deploying Monitoring</span><span class="sxs-lookup"><span data-stu-id="6ce3e-131">Deploying Monitoring</span></span>](https://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

