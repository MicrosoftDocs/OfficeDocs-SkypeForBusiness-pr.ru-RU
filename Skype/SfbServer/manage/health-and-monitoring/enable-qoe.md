---
title: Включение функции отслеживания качества взаимодействия в Skype для бизнеса Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c8bb3c67-b324-4d94-8158-00c792c7ac42
description: 'Сводка: Узнайте, как включить качества взаимодействия (QoE) в Скайп для Business Server 2015.'
ms.openlocfilehash: 8c63a1bf493e601c4936b83cc9edfaa6e3727f26
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="enable-quality-of-experience-in-skype-for-business-server-2015"></a><span data-ttu-id="396e9-103">Включение функции отслеживания качества взаимодействия в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="396e9-103">Enable Quality of Experience in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="396e9-104">**Сводка:** Включение качества взаимодействия (QoE) в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="396e9-104">**Summary:** learn how to enable Quality of Experience (QoE) in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="396e9-105">Служба отслеживания качества взаимодействия (QoE) записывает числовые данные, которые показывают качество мультимедиа-данных, и сведения об участниках, именах устройств, драйверах, IP-адресах и типах конечных точек, использованных во время звонка или сеанса.</span><span class="sxs-lookup"><span data-stu-id="396e9-105">Quality of Experience (QoE) records numeric data that indicates the media quality and information about participants, device names, drivers, IP addresses, and endpoint types involved in calls and sessions.</span></span> <span data-ttu-id="396e9-106">Дополнительные сведения см [мониторинг](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) в документации по планированию.</span><span class="sxs-lookup"><span data-stu-id="396e9-106">For details, see [Planning for Monitoring](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx) in the Planning documentation.</span></span>
  
<span data-ttu-id="396e9-107">Используйте следующую процедуру для включения службы качества взаимодействия для всей организации или для отдельных сайтов в организации.</span><span class="sxs-lookup"><span data-stu-id="396e9-107">Use the following procedure to enable QoE for your whole organization or each site in your organization.</span></span>
  
> [!NOTE]
> <span data-ttu-id="396e9-108">Чтобы включить службу качества взаимодействия, сначала необходимо настроить мониторинг и внутреннюю базу данных мониторинга.</span><span class="sxs-lookup"><span data-stu-id="396e9-108">To enable QoE, you must first configure monitoring and a monitoring back-end database.</span></span> <span data-ttu-id="396e9-109">Дополнительные сведения см [Развертывание мониторинга](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span><span class="sxs-lookup"><span data-stu-id="396e9-109">For details, see [Deploying Monitoring](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx).</span></span> 
  
### <a name="to-enable-qoe-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="396e9-110">Включение службы качества взаимодействия с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="396e9-110">To enable QoE by using Skype for Business Server Control Panel</span></span>

1.  <span data-ttu-id="396e9-111">Используя учетную запись пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или роль CsServerAdministrator или CsAdministrator, войдите на любой компьютер, который находится в сети, в котором вы развернули Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="396e9-111">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Skype for Business Server 2015.</span></span>
    
2. <span data-ttu-id="396e9-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="396e9-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="396e9-113">На панели навигации слева нажмите **Мониторинг и архивация**, затем выберите **Данные о качестве взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="396e9-113">In the left navigation bar, click **Monitoring and Archiving**, and then click **Quality of Experience Data**.</span></span> 
    
4. <span data-ttu-id="396e9-114">На странице **данных качества взаимодействия** выберите соответствующую коллекцию в таблице и последовательно выберите пункты **Действие** и **Включить отслеживание качества взаимодействия**.</span><span class="sxs-lookup"><span data-stu-id="396e9-114">On the **Quality of Experience Data** page, click the appropriate collection from the table, click **Action**, and then click **Enable QoE**.</span></span>
    
## <a name="enabling-qoe-by-using-windows-powershell-cmdlets"></a><span data-ttu-id="396e9-115">Включение службы качества взаимодействия с помощью командлетов Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="396e9-115">Enabling QoE by Using Windows PowerShell Cmdlets</span></span>

<span data-ttu-id="396e9-116">Можно включить качества взаимодействия с помощью Windows PowerShell и командлет **Set-CsQoEConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="396e9-116">You can enable QoE by using Windows PowerShell and the **Set-CsQoEConfiguration** cmdlet.</span></span> <span data-ttu-id="396e9-117">Можно выполнить этот командлет из Скайп для консоли Business Server или из удаленного сеанса Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="396e9-117">You can run this cmdlet either from the Skype for Business Server Management Shell or from a remote session of Windows PowerShell.</span></span> <span data-ttu-id="396e9-118">Для получения дополнительных сведений об использовании удаленной оболочки Windows PowerShell для подключения к Скайп для Business Server в статье блога [«Быстрый запуск: управление Microsoft Lync Server 2010 с помощью удаленной оболочки PowerShell»](https://go.microsoft.com/fwlink/p/?linkId=255876).</span><span class="sxs-lookup"><span data-stu-id="396e9-118">For details about using remote Windows PowerShell to connect to Skype for Business Server, see the blog article ["Quick Start: Managing Microsoft Lync Server 2010 Using Remote PowerShell"](https://go.microsoft.com/fwlink/p/?linkId=255876).</span></span> <span data-ttu-id="396e9-119">Процесс одинаков в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="396e9-119">The process is the same in Skype for Business Server.</span></span>
  
### <a name="to-enable-qoe-for-a-single-location"></a><span data-ttu-id="396e9-120">Включение службы качества взаимодействия для одного расположения</span><span class="sxs-lookup"><span data-stu-id="396e9-120">To enable QoE for a single location</span></span>

 <span data-ttu-id="396e9-121">Чтобы включить службу качества взаимодействия, установите параметр EnableQoE в значение True ($True).</span><span class="sxs-lookup"><span data-stu-id="396e9-121">To enable QoE, set the EnableQoE parameter to True ($True).</span></span>
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $True
  ```

### <a name="to-disable-qoe-for-a-single-location"></a><span data-ttu-id="396e9-122">Отключение службы качества взаимодействия для одного расположения</span><span class="sxs-lookup"><span data-stu-id="396e9-122">To disable QoE for a single location</span></span>

 <span data-ttu-id="396e9-p104">Чтобы отключить службу качества взаимодействия, установите параметр EnableQoE в значение False ($False). При этом мониторинг не будет удален. Он приостановит сбор и хранение данных качества взаимодействия.</span><span class="sxs-lookup"><span data-stu-id="396e9-p104">To disable QoE, set the EnableQoE parameter to False ($False). This does not uninstall monitoring. It pauses the collection and storage of QoE data.</span></span>
    
  ```
  Set-CsQoEConfiguration -Identity "site:Redmond" -EnableQoE $False
  ```

### <a name="to-use-a-single-command-to-enable-qoe-in-multiple-locations"></a><span data-ttu-id="396e9-126">Использование одной команды для включения службы качества взаимодействия в нескольких расположениях</span><span class="sxs-lookup"><span data-stu-id="396e9-126">To use a single command to enable QoE in multiple locations</span></span>

 <span data-ttu-id="396e9-127">Следующая команда включает службу качества взаимодействия для всех параметров конфигурации качества взаимодействия, используемых в текущий момент в организации.</span><span class="sxs-lookup"><span data-stu-id="396e9-127">This command enables QoE for all the QoE configuration settings currently in use in your organization.</span></span>
    
  ```
  Get-CsQoEConfiguration | Set-CsQoEConfiguration "site:Redmond" -EnableQoE $True
  ```

<span data-ttu-id="396e9-128">Дополнительные сведения см [Командлета Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="396e9-128">For details, see [Set-CsQoEConfiguration](https://docs.microsoft.com/powershell/module/skype/set-csqoeconfiguration?view=skype-ps).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="396e9-129">См. также</span><span class="sxs-lookup"><span data-stu-id="396e9-129">See also</span></span>

[<span data-ttu-id="396e9-130">Планирование мониторинга</span><span class="sxs-lookup"><span data-stu-id="396e9-130">Planning for Monitoring</span></span>](http://technet.microsoft.com/library/26cead5a-183c-42f1-a4b0-0e8d61c6159d.aspx)
  
[<span data-ttu-id="396e9-131">Мониторинг развертывания</span><span class="sxs-lookup"><span data-stu-id="396e9-131">Deploying Monitoring</span></span>](http://technet.microsoft.com/library/117f4a3e-0670-4388-a553-b9854921145f.aspx)

