---
title: Добавление политики расположения на сайт сети в Skype для бизнеса Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Назначьте политики местоположения E9-1-1 на сайты сети в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: 4a74b1ee44d1e2f34a51d7859235e10649d0e2ee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233869"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="0b81f-103">Добавление политики расположения на сайт сети в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0b81f-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="0b81f-104">Назначьте политики местоположения E9-1-1 на сайты сети в Skype для бизнеса Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0b81f-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="0b81f-105">В следующих примерах показано, как добавить политику расположения в **Редмонде** , определенную в разделе [Создание политик местоположений в Skype для бизнеса Server](create-location-policies.md) , на существующий сайт сети и как создать новый сайт сети, использующий политику расположения в **Редмонде** .</span><span class="sxs-lookup"><span data-stu-id="0b81f-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="0b81f-106">Дополнительные сведения о работе с сетевыми сайтами можно найти в документации по оболочке Lync Server Management Shell для следующих командлетов:</span><span class="sxs-lookup"><span data-stu-id="0b81f-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="0b81f-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="0b81f-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="0b81f-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="0b81f-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="0b81f-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="0b81f-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="0b81f-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="0b81f-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="0b81f-111">Назначение политики местоположения существующему сетевому узлу</span><span class="sxs-lookup"><span data-stu-id="0b81f-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="0b81f-112">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="0b81f-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="0b81f-113">Выполните следующие командлеты для изменения существующего сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="0b81f-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="0b81f-114">Назначьте политику расположения с меткой **Redmond** существующему сетевому сайту с именем **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="0b81f-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="0b81f-115">Назначение политики местоположения новому сетевому узлу</span><span class="sxs-lookup"><span data-stu-id="0b81f-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="0b81f-116">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="0b81f-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="0b81f-117">Выполните следующий командлет для создания нового сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="0b81f-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="0b81f-118">Создайте новый сетевой сайт в области сети и назначьте ему политику расположения с меткой **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="0b81f-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


