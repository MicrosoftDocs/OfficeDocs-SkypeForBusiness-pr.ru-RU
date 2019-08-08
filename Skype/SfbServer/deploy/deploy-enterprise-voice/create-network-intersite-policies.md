---
title: Создание политик межсайтовой сети в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: b0714aae-55dc-4587-b718-34a03f596b22
description: Создавайте сетевые политики для разных сайтов, которые используются для управления допуском голосовых вызовов в Skype для бизнеса Server.
ms.openlocfilehash: ac03057de5b6e25e2b9de812f0d53ae02811d456
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233484"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="ada2e-103">Создание политик межсайтовой сети в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ada2e-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="ada2e-104">Создавайте сетевые политики для разных сайтов, которые используются для управления допуском голосовых вызовов в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ada2e-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="ada2e-105">Межсайтовая сетевая политика определяет ограничения пропускной способности между сайтами, соединенными прямыми каналами связи по глобальной сети.</span><span class="sxs-lookup"><span data-stu-id="ada2e-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ada2e-106">Сетевая политика межсайтовой сети требуется *только* в том случае, если имеется прямая перекрестная ссылка между двумя сетевыми сайтами.</span><span class="sxs-lookup"><span data-stu-id="ada2e-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="ada2e-p101">В примере топологии для Северной Америки показано прямое соединение между узлами Reno (г. Рино) и Albuquerque (г. Альбукерке). Этим двум узлам требуется межузловая политика, которая применяет соответствующий профиль политики пропускной способности. В следующем примере показано применение профиля 20Mb_Link.</span><span class="sxs-lookup"><span data-stu-id="ada2e-p101">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites. These two sites require an inter-site policy that applies an appropriate bandwidth policy profile. The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="ada2e-110">Создание межсайтовой сетевой политики</span><span class="sxs-lookup"><span data-stu-id="ada2e-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="ada2e-111">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="ada2e-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ada2e-p102">Чтобы создать межсайтовые сетевые политики и применить соответствующий профиль политики пропускной способности для двух узлов с прямым соединением, выполните командлет New-CsNetworkInterSitePolicy. Пример:</span><span class="sxs-lookup"><span data-stu-id="ada2e-p102">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link. For example, run:</span></span>
    
   ```
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="ada2e-114">Повторите шаг 2 для всех пар сетевых узлов, имеющих прямое соединение.</span><span class="sxs-lookup"><span data-stu-id="ada2e-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ada2e-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ada2e-115">See also</span></span>

[<span data-ttu-id="ada2e-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ada2e-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="ada2e-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ada2e-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="ada2e-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ada2e-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="ada2e-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ada2e-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
