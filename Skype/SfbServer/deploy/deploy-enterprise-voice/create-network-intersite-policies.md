---
title: Создание сетевых межсетных политик в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Создайте сетевые политики межсайтов, которые используются Корпоративная голосовая связь управления приемом вызовов в Skype для бизнеса Server.
ms.openlocfilehash: 7c0ca45c691ab1ef70d3660c3d49a08c40bdd40d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093087"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="72277-103">Создание сетевых межсетных политик в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="72277-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="72277-104">Создайте сетевые политики межсайтов, которые используются Корпоративная голосовая связь управления приемом вызовов в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="72277-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="72277-105">Политика межсайтовой сети определяет ограничения пропускной способности между сайтами, у которых между ними есть прямые связи WAN.</span><span class="sxs-lookup"><span data-stu-id="72277-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="72277-106">Политика межсайтов сети  необходима только в том случае, если между двумя сетевыми сайтами существует прямая перекрестная связь.</span><span class="sxs-lookup"><span data-stu-id="72277-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="72277-107">В примере топологии Северной Америки существует прямая связь между сайтами Reno и Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="72277-107">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="72277-108">Для этих двух сайтов требуется политика межсайтов, которая применяет соответствующий профиль политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="72277-108">These two sites require an inter-site policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="72277-109">В следующем примере применяется 20Mb_Link профиль.</span><span class="sxs-lookup"><span data-stu-id="72277-109">The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="72277-110">Создание сетевой политики межсайтов</span><span class="sxs-lookup"><span data-stu-id="72277-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="72277-111">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="72277-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="72277-112">Запустите New-CsNetworkInterSitePolicy, чтобы создать сетевые политики межсайтов и применить соответствующий профиль политики пропускной способности для двух сайтов с прямым перекрестным соединением.</span><span class="sxs-lookup"><span data-stu-id="72277-112">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="72277-113">Например, выполните команду:</span><span class="sxs-lookup"><span data-stu-id="72277-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="72277-114">Повторите шаг 2 по мере необходимости для создания сетевых политик межсайтов для всех пар сетевых сайтов, которые имеют прямую перекрестную связь.</span><span class="sxs-lookup"><span data-stu-id="72277-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="72277-115">См. также</span><span class="sxs-lookup"><span data-stu-id="72277-115">See also</span></span>

[<span data-ttu-id="72277-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="72277-116">New-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="72277-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="72277-117">Get-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="72277-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="72277-118">Set-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="72277-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="72277-119">Remove-CsNetworkInterSitePolicy</span></span>](/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)