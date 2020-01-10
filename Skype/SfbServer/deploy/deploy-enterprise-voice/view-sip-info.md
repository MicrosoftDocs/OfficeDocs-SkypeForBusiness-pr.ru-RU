---
title: Просмотр сведений об отдельных магистральных линиях SIP в Skype для бизнеса Server
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
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Сводка: сведения о том, как просматривать сведения о магистральных линиях SIP в Skype для бизнеса Server.'
ms.openlocfilehash: 366e03c1a3ceef345a52bca6e038c9311fcc3003
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001129"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="92033-103">Просмотр сведений об отдельных магистральных линиях SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="92033-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="92033-104">**Сводка:** Сведения о том, как просматривать сведения о магистральных линиях SIP в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="92033-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="92033-105">Магистральные линии SIP используются для подключения к голосовой сети Skype для бизнеса Server с помощью коммутируемой телефонной сети с открытым коммутируемым телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="92033-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="92033-106">В предыдущих версиях продукта магистрали использовались для маршрутизации исходящих звонков с сервера-посредника на шлюз ТСОП, причем для каждого шлюза использовалась только одна магистраль.</span><span class="sxs-lookup"><span data-stu-id="92033-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="92033-107">Поэтому шлюз ТСОП и магистраль SIP были практически равнозначны.</span><span class="sxs-lookup"><span data-stu-id="92033-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="92033-108">Для администраторов это означало возможность просмотра сведений об отдельной магистрали SIP путем просмотра сведений о связанном шлюзе ТСОП.</span><span class="sxs-lookup"><span data-stu-id="92033-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="92033-109">Однако в Skype для бизнеса Server для одного шлюза PSTN может быть назначено несколько каналов. Это означает, что шлюзы и магистральные линии больше не являются одними и теми же.</span><span class="sxs-lookup"><span data-stu-id="92033-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="92033-110">В свою очередь, это означает, что администраторы должны использовать новый командлет [Get-кструнк](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) для просмотра сведений о отдельной внешней магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="92033-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="92033-111">Просмотр сведений о всех магистралях SIP</span><span class="sxs-lookup"><span data-stu-id="92033-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="92033-112">Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="92033-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="92033-113">Просмотр сведений об определенной магистрали SIP</span><span class="sxs-lookup"><span data-stu-id="92033-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="92033-114">Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="92033-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="92033-115">Просмотр информации обо всех линиях связи SIP, назначенных пулу</span><span class="sxs-lookup"><span data-stu-id="92033-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="92033-116">В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="92033-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```
