---
title: Создание связей между областями в Скайп для Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f8163910-8935-475d-88a2-3aa44feb9dbe
description: Создание или изменение связей между областями сети, используемые с корпоративной голосовой связи контроля допуска звонков в Скайп Business Server.
ms.openlocfilehash: c3b0f24ffdeea1724c89951ffc88516aea4dffb5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33892960"
---
# <a name="create-network-region-links-in-skype-for-business-server"></a><span data-ttu-id="b7c7b-103">Создание связей между областями в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="b7c7b-103">Create network region links in Skype for Business Server</span></span>
 
<span data-ttu-id="b7c7b-104">Создание или изменение связей между областями сети, используемые с корпоративной голосовой связи контроля допуска звонков в Скайп Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-104">Create or modify network region links, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="b7c7b-105">Регионы в сети связываются с помощью физического подключения глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-105">Regions within a network are linked through physical WAN connectivity.</span></span> <span data-ttu-id="b7c7b-106">Связь между областями сети создает канал между двумя областями, настроенными для контроля допуска звонков (CAC), и задает ограничения пропускной способности трафика аудио- и видеоданных между этими областями.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-106">A network region link creates a link between two regions configured for Call Admission Control (CAC) and sets the bandwidth limitations on audio and video traffic between these regions.</span></span>
  
<span data-ttu-id="b7c7b-107">Пример топологии имеет связь между Северной Америке, а также Азиатско-Тихоокеанском регионе и ссылки между EMEA, а также Азиатско-Тихоокеанском регионе.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-107">The example topology has a link between the North America and APAC regions, and a link between the EMEA and APAC regions.</span></span> <span data-ttu-id="b7c7b-108">Каждый из этих связей между областями ограниченной пропускной способностью глобальной сети, как описано в таблице сведения о пропускной способности связи между областями в [Пример: сбор требований для контроля допуска звонков в Скайп для Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b7c7b-108">Each of these region links is constrained by WAN bandwidth, as described in Region Link Bandwidth Information table in [Example: Gathering requirements for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/example-gathering-requirements.md).</span></span>
  
### <a name="to-create-network-region-links-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="b7c7b-109">Создание связей между областями с помощью Скайп для консоли Business Server</span><span class="sxs-lookup"><span data-stu-id="b7c7b-109">To create network region links by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="b7c7b-110">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="b7c7b-111">Запустите командлет New-CsNetworkRegionLink, чтобы создать связи между областями и примените соответствующие профили политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-111">Run the New-CsNetworkRegionLink cmdlet to create the region links and apply appropriate bandwidth policy profiles.</span></span> <span data-ttu-id="b7c7b-112">Например, выполните командлет:</span><span class="sxs-lookup"><span data-stu-id="b7c7b-112">For example, run:</span></span>
    
   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID NA-EMEA-LINK -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -BWPolicyProfileID 50Mb_Link
   ```

   ```
   New-CsNetworkRegionLink -NetworkRegionLinkID EMEA-APAC-LINK -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -BWPolicyProfileID 25Mb_Link
   ```

### <a name="to-create-network-region-links-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="b7c7b-113">Создание связей между областями с помощью Скайп для панели управления Business Server</span><span class="sxs-lookup"><span data-stu-id="b7c7b-113">To create network region links by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="b7c7b-114">Откройте Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-114">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="b7c7b-115">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-115">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="b7c7b-116">Нажмите кнопку навигации **Связь между областями**.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-116">Click the **Region Link** navigation button.</span></span>
    
4. <span data-ttu-id="b7c7b-117">Выберите **Создать**.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-117">Click **New**.</span></span>
    
5. <span data-ttu-id="b7c7b-118">На странице **Создание связи между областями** щелкните поле **Имя** и введите имя для связи между областями сети.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-118">On the **New Region Link** page, click **Name** and then type a name for the network region link.</span></span>
    
6. <span data-ttu-id="b7c7b-119">Щелкните **Область сети 1**, затем в списке выберите область сети, которую требуется связать с областью сети 2.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-119">Click **Network Region #1**, and then click the network region in the list that you want to link to Network Region #2.</span></span>
    
7. <span data-ttu-id="b7c7b-120">Щелкните **Область сети 2**, а затем выберите в списке область, которую требуется связать с областью сети 1.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-120">Click **Network Region #2**, and then click a network region in the list that you want to link to Network Region #1.</span></span>
    
8. <span data-ttu-id="b7c7b-121">Кроме того, можно щелкнуть элемент **Политика пропускной способности**, а затем выбрать профиль политики пропускной способности, который требуется применить к связи между областями сети.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-121">Optionally, click **Bandwidth policy**, and then select the bandwidth policy profile that you want to apply to the network region link.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b7c7b-122">Применять политику пропускной способности следует только в том случае, если для связи между областями сети имеются ограничения полосы пропускания и требуется использовать CAC для управления трафиком среды по этому каналу.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-122">Apply a bandwidth policy only if the network region link is bandwidth-constrained and you want to use CAC to control media traffic on that link.</span></span> 
  
9. <span data-ttu-id="b7c7b-123">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-123">Click **Commit**.</span></span>
    
10. <span data-ttu-id="b7c7b-124">Чтобы завершить создание связи между областями сети для топологии, повторите шаги с 4 по 9 с настройками для других областей.</span><span class="sxs-lookup"><span data-stu-id="b7c7b-124">To finish creating network region links for your topology, repeat steps 4 through 9 with settings for other regions.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="b7c7b-125">См. также</span><span class="sxs-lookup"><span data-stu-id="b7c7b-125">See also</span></span>

[<span data-ttu-id="b7c7b-126">New-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b7c7b-126">New-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="b7c7b-127">Get-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b7c7b-127">Get-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="b7c7b-128">Set-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b7c7b-128">Set-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkregionlink?view=skype-ps)
  
[<span data-ttu-id="b7c7b-129">Remove-CsNetworkRegionLink</span><span class="sxs-lookup"><span data-stu-id="b7c7b-129">Remove-CsNetworkRegionLink</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkregionlink?view=skype-ps)
