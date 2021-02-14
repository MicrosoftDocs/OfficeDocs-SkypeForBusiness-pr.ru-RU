---
title: Создание сетевых политик межсайтов в Skype для бизнеса Server
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
description: Создайте сетевые политики межсайтов, которые используются Корпоративная голосовая связь контроля допуска звонков в Skype для бизнеса Server.
ms.openlocfilehash: 69609da75fdfa87309743920eace59892a440f2b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822479"
---
# <a name="create-network-intersite-policies-in-skype-for-business-server"></a><span data-ttu-id="ea2f2-103">Создание сетевых политик межсайтов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ea2f2-103">Create network intersite policies in Skype for Business Server</span></span>
 
<span data-ttu-id="ea2f2-104">Создайте сетевые политики межсайтов, которые используются Корпоративная голосовая связь контроля допуска звонков в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="ea2f2-104">Create network inter-site policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="ea2f2-105">Политика межсайтовой сети определяет ограничения пропускной способности между сайтами, которые имеют прямые связи WAN между ними.</span><span class="sxs-lookup"><span data-stu-id="ea2f2-105">A network inter-site policy defines bandwidth limitations between sites that have direct WAN links between them.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ea2f2-106">Сетовая межсайтовая политика необходима, только если между двумя сетевыми узлами существует прямая межсайтовая связь. </span><span class="sxs-lookup"><span data-stu-id="ea2f2-106">A network inter-site policy is required  *only*  if there is a direct cross link between two network sites.</span></span>
  
<span data-ttu-id="ea2f2-107">В примере топологии "Северная Америка" имеется прямая связь между сайтами Reno и Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="ea2f2-107">In the example topology North America region, there is a direct link between the Reno and Albuquerque sites.</span></span> <span data-ttu-id="ea2f2-108">Для этих двух сайтов требуется межсайтовая политика, которая применяет соответствующий профиль политики пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="ea2f2-108">These two sites require an inter-site policy that applies an appropriate bandwidth policy profile.</span></span> <span data-ttu-id="ea2f2-109">В следующем примере применяется 20Mb_Link профиля.</span><span class="sxs-lookup"><span data-stu-id="ea2f2-109">The following example applies the 20Mb_Link profile.</span></span>
  
### <a name="to-create-a-network-inter-site-policy"></a><span data-ttu-id="ea2f2-110">Создание сетевой политики межсайтов</span><span class="sxs-lookup"><span data-stu-id="ea2f2-110">To create a network inter-site policy</span></span>

1. <span data-ttu-id="ea2f2-111">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="ea2f2-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ea2f2-112">Запустите New-CsNetworkInterSitePolicy, чтобы создать сетевые межсайтовую политику и применить соответствующий профиль политики пропускной способности для двух сайтов с прямым перекрестным соединением.</span><span class="sxs-lookup"><span data-stu-id="ea2f2-112">Run the New-CsNetworkInterSitePolicy cmdlet to create network inter-site policies and apply an appropriate bandwidth policy profile for two sites that have a direct cross link.</span></span> <span data-ttu-id="ea2f2-113">Например, выполните команду:</span><span class="sxs-lookup"><span data-stu-id="ea2f2-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link
   ```

3. <span data-ttu-id="ea2f2-114">Повторите шаг 2 по мере необходимости, чтобы создать сетевые политики межсайтов для всех пар сетевых сайтов с прямым перекрестным соединением.</span><span class="sxs-lookup"><span data-stu-id="ea2f2-114">Repeat step 2 as needed to create network inter-site policies for all network sites pairs that have a direct cross link.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ea2f2-115">См. также</span><span class="sxs-lookup"><span data-stu-id="ea2f2-115">See also</span></span>

[<span data-ttu-id="ea2f2-116">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ea2f2-116">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="ea2f2-117">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ea2f2-117">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="ea2f2-118">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ea2f2-118">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkintersitepolicy?view=skype-ps)
  
[<span data-ttu-id="ea2f2-119">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="ea2f2-119">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkintersitepolicy?view=skype-ps)
