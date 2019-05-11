---
title: Добавление политики расположения в области сети, в Скайп для Business Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Назначение политик расположения E9-1-1 для сетевых узлов в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: d30f9295b633ccfa7439e697931b13bd92b1cc0b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33893177"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="7c7c7-103">Добавление политики расположения в области сети, в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="7c7c7-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="7c7c7-104">Назначение политик расположения E9-1-1 для сетевых узлов в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="7c7c7-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="7c7c7-105">В следующих примерах показано, как добавить политику расположения **Redmond** , определенных в [Создание политик расположения в Скайп для Business Server](create-location-policies.md) для существующего сетевого узла, а также для создания нового сетевого узла, использующего политику расположения **Redmond** .</span><span class="sxs-lookup"><span data-stu-id="7c7c7-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="7c7c7-106">Для получения дополнительных сведений о работе с сетевыми узлами обратитесь к документации Командная консоль Lync Server для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="7c7c7-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="7c7c7-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="7c7c7-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="7c7c7-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="7c7c7-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="7c7c7-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="7c7c7-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="7c7c7-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="7c7c7-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="7c7c7-111">Назначение политики местоположения существующему сетевому узлу</span><span class="sxs-lookup"><span data-stu-id="7c7c7-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="7c7c7-112">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="7c7c7-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="7c7c7-113">Выполните следующие командлеты для изменения существующего сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="7c7c7-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="7c7c7-114">Назначьте политику расположения с меткой **Redmond** существующему сетевому сайту с именем **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="7c7c7-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="7c7c7-115">Назначение политики местоположения новому сетевому узлу</span><span class="sxs-lookup"><span data-stu-id="7c7c7-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="7c7c7-116">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="7c7c7-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="7c7c7-117">Выполните следующий командлет для создания нового сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="7c7c7-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="7c7c7-118">Создайте новый сетевой сайт в области сети и назначьте ему политику расположения с меткой **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="7c7c7-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


