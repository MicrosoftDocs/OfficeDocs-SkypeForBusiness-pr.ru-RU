---
title: Просмотр сведений об отдельных магистральных серверах SIP в Skype для бизнеса Server
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
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: Сводка. Узнайте, как просматривать сведения о магистральных серверах SIP в Skype для бизнеса Server.
ms.openlocfilehash: 989f9fea44bfcce67eba71b9f0b495b924f9e3a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103235"
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server"></a><span data-ttu-id="479e7-103">Просмотр сведений об отдельных магистральных серверах SIP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="479e7-103">View information about individual SIP trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="479e7-104">**Сводка:** Узнайте, как просматривать сведения о магистральных серверах SIP в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="479e7-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server.</span></span>
  
<span data-ttu-id="479e7-105">Магистрали SIP используются для подключения голосовой связи Skype для бизнеса Server через сеть IP-телефонов с открытой телефонной сетью (PSTN).</span><span class="sxs-lookup"><span data-stu-id="479e7-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="479e7-106">В предыдущих версиях продукта магистрали использовались для маршрутизации исходящих звонков с сервера-посредника на шлюз ТСОП, причем для каждого шлюза использовалась только одна магистраль.</span><span class="sxs-lookup"><span data-stu-id="479e7-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="479e7-107">Поэтому шлюз ТСОП и магистраль SIP были практически равнозначны.</span><span class="sxs-lookup"><span data-stu-id="479e7-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="479e7-108">Для администраторов это означало возможность просмотра сведений об отдельной магистрали SIP путем просмотра сведений о связанном шлюзе ТСОП.</span><span class="sxs-lookup"><span data-stu-id="479e7-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="479e7-109">Однако в Skype для бизнеса Server теперь несколько магистральных серверов могут быть назначены одному шлюзу PSTN; это означает, что шлюзы и магистрали больше не одно и то же.</span><span class="sxs-lookup"><span data-stu-id="479e7-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="479e7-110">В свою очередь, это означает, что администраторы должны использовать новый комлет [Get-CsTrunk](/powershell/module/skype/get-cstrunk?view=skype-ps) для просмотра сведений об отдельном магистрали SIP.</span><span class="sxs-lookup"><span data-stu-id="479e7-110">In turn, that means that administrators must use the new [Get-CsTrunk](/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="479e7-111">Просмотр сведений для всех магистральных SIP</span><span class="sxs-lookup"><span data-stu-id="479e7-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="479e7-112">Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="479e7-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```powershell
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="479e7-113">Просмотр сведений для определенного магистрали SIP</span><span class="sxs-lookup"><span data-stu-id="479e7-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="479e7-114">Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="479e7-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```powershell
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="479e7-115">Просмотр сведений для всех магистральных SIP, задаваемой пулу</span><span class="sxs-lookup"><span data-stu-id="479e7-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="479e7-116">В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="479e7-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```powershell
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```