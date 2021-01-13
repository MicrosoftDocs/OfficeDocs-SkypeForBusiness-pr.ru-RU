---
title: Добавление политики расположения на сетевой сайт в Skype для бизнеса Server
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
ms.assetid: 43bfab8a-3d6b-4ca4-8425-879fd910502e
description: Назначьте политики расположения E9-1-1 сетевым сайтам в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 887c2fcab63acd5d143ba80f6be6976e8fe2b39f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804279"
---
# <a name="add-a-location-policy-to-a-network-site-in-skype-for-business-server"></a><span data-ttu-id="f2030-103">Добавление политики расположения на сетевой сайт в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f2030-103">Add a location policy to a network site in Skype for Business Server</span></span>
 
<span data-ttu-id="f2030-104">Назначьте политики расположения E9-1-1 сетевым сайтам в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="f2030-104">Assign E9-1-1 location policies to network sites in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="f2030-105">В следующих примерах покажем, как добавить политику расположения **Redmond,** задаемую в области "Создание политик расположения" в Skype для бизнеса [Server,](create-location-policies.md) к существующему сетевому сайту и создать новый сетевой сайт, использующий политику расположения **Redmond.**</span><span class="sxs-lookup"><span data-stu-id="f2030-105">The following examples show how to add the **Redmond** location policy defined in [Create location policies in Skype for Business Server](create-location-policies.md) to an existing network site and how to create a new network site that uses the **Redmond** location policy.</span></span>
  
<span data-ttu-id="f2030-106">Подробные сведения о работе с сетевыми сайтами см. в документации по Lync Server Management Shell для следующих cmdlets:</span><span class="sxs-lookup"><span data-stu-id="f2030-106">For details about working with network sites, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>
  
- <span data-ttu-id="f2030-107">**New-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="f2030-107">**New-CsNetworkSite**</span></span>
    
- <span data-ttu-id="f2030-108">**Get-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="f2030-108">**Get-CsNetworkSite**</span></span>
    
- <span data-ttu-id="f2030-109">**Set-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="f2030-109">**Set-CsNetworkSite**</span></span>
    
- <span data-ttu-id="f2030-110">**Remove-CsNetworkSite**</span><span class="sxs-lookup"><span data-stu-id="f2030-110">**Remove-CsNetworkSite**</span></span>
    
### <a name="to-assign-a-location-policy-to-an-existing-network-site"></a><span data-ttu-id="f2030-111">Назначение политики местоположения существующему сетевому узлу</span><span class="sxs-lookup"><span data-stu-id="f2030-111">To assign a location policy to an existing network site</span></span>

1. <span data-ttu-id="f2030-112">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="f2030-112">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f2030-113">Выполните следующие командлеты для изменения существующего сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="f2030-113">Run the following cmdlets to modify an existing network site.</span></span>
    
    <span data-ttu-id="f2030-114">Назначьте политику расположения с тегами **Redmond** существующему сетевому сайту **с именем Redmond.**</span><span class="sxs-lookup"><span data-stu-id="f2030-114">Assign the **Redmond** tagged Location policy to an existing network site named **Redmond**.</span></span>
    
   ```powershell
   Set-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```

### <a name="to-assign-a-location-policy-to-a-new-network-site"></a><span data-ttu-id="f2030-115">Назначение политики местоположения новому сетевому узлу</span><span class="sxs-lookup"><span data-stu-id="f2030-115">To assign a location policy to a new network site</span></span>

1. <span data-ttu-id="f2030-116">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="f2030-116">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="f2030-117">Выполните следующий командлет для создания нового сетевого узла.</span><span class="sxs-lookup"><span data-stu-id="f2030-117">Run the following cmdlet to create a new network site.</span></span>
    
    <span data-ttu-id="f2030-118">Создайте новый сетевой узел в области сети и назначьте ему политику местоположения с меткой **Redmond**.</span><span class="sxs-lookup"><span data-stu-id="f2030-118">Create a new network site in the network region and assign the **Redmond** tagged Location policy.</span></span>
    
   ```powershell
   New-CsNetworkSite -Identity "Redmond" -NetworkRegionID "NorthAmerica" -LocationPolicy "Redmond"
   ```


