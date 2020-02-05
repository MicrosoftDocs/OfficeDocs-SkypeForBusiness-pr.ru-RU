---
title: Создание политик межсайтовой сети в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Создавайте сетевые политики для разных сайтов, которые используются для управления допуском голосовых вызовов в Skype для бизнеса Server.
ms.openlocfilehash: f24d0ad289d9388c45a5dbd9a31aa60e8c41e357
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767922"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="7d3ac-103">Создание политик межсайтовой сети в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="7d3ac-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="7d3ac-104">Создавайте сетевые политики для разных сайтов, которые используются для управления допуском голосовых вызовов в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="7d3ac-105">Межсайтовая сетевая политика определяет ограничения пропускной способности между сайтами, соединенными прямыми каналами связи по глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7d3ac-106">Сетевая политика межсайтовой сети требуется *только* в том случае, если имеется прямая перекрестная ссылка между двумя сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="7d3ac-p101">В примере топологии для Северной Америки показано прямое соединение между узлами Reno (г. Рино) и Albuquerque (г. Альбукерке). Этим двум узлам требуется межузловая политика, которая применяет соответствующий профиль политики пропускной способности. В следующем примере показано применение профиля 20Mb_Link.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-p101">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites. These two sites require an inter-site policy that applies an appropriate bandwidth policy profile. The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="7d3ac-110">Создание межсайтовой сетевой политики</span><span class="sxs-lookup"><span data-stu-id="7d3ac-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="7d3ac-111">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="7d3ac-p102">Чтобы создать межсайтовые сетевые политики и применить соответствующий профиль политики пропускной способности для двух узлов с прямым соединением, выполните командлет New-CsNetworkInterSitePolicy. Пример:</span><span class="sxs-lookup"><span data-stu-id="7d3ac-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="7d3ac-114">Повторите шаг 2 для всех пар сетевых узлов, имеющих прямое соединение.</span><span class="sxs-lookup"><span data-stu-id="7d3ac-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7d3ac-115">См. также</span><span class="sxs-lookup"><span data-stu-id="7d3ac-115">See also</span></span>

[<span data-ttu-id="7d3ac-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="7d3ac-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="7d3ac-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="7d3ac-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="7d3ac-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="7d3ac-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="7d3ac-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="7d3ac-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
