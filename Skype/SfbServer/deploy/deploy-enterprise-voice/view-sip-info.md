---
title: Просмотр сведений об отдельных магистралях SIP в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: adfacb74-7ea5-4c53-934e-ba7ec59879eb
description: 'Сводка: Узнайте, как для просмотра сведений о магистралях SIP в Скайп для Business Server 2015.'
ms.openlocfilehash: c307d4e9b18b7ff5fda8d8d0deaa4eb88ba5b6b0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="view-information-about-individual-sip-trunks-in-skype-for-business-server-2015"></a><span data-ttu-id="997f7-103">Просмотр сведений об отдельных магистралях SIP в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="997f7-103">View information about individual SIP trunks in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="997f7-104">**Сводка:** Узнайте, как для просмотра сведений о магистралях SIP в Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="997f7-104">**Summary:** Learn how to view information about SIP trunks in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="997f7-105">Магистралях SIP, используются для подключения Скайп Business Server голосовой связи через IP-телефона сеть с общей переключения телефонной сети общего пользования (PSTN).</span><span class="sxs-lookup"><span data-stu-id="997f7-105">SIP trunks are used to connect Skype for Business Server Voice over IP phone network with the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="997f7-106">В предыдущих версиях продукта магистрали использовались для маршрутизации исходящих звонков с сервера-посредника на шлюз ТСОП, причем для каждого шлюза использовалась только одна магистраль.</span><span class="sxs-lookup"><span data-stu-id="997f7-106">In previous version of the product, trunks were used to route outbound calls from a Mediation Server to a PSTN gateway and each gateway was limited to a single trunk.</span></span> <span data-ttu-id="997f7-107">Поэтому шлюз ТСОП и магистраль SIP были практически равнозначны.</span><span class="sxs-lookup"><span data-stu-id="997f7-107">As a result, a PSTN gateway and a SIP trunk were essentially identical.</span></span> <span data-ttu-id="997f7-108">Для администраторов это означало возможность просмотра сведений об отдельной магистрали SIP путем просмотра сведений о связанном шлюзе ТСОП.</span><span class="sxs-lookup"><span data-stu-id="997f7-108">For administrators, that meant they could view information about an individual SIP trunk simply by viewing information about the associated PSTN gateway.</span></span>
  
<span data-ttu-id="997f7-109">В Скайп Business Server Однако несколько магистралей можно теперь назначить один шлюз ТСОП; Это означает, что магистральных линий связи и шлюзами больше не одной и той же.</span><span class="sxs-lookup"><span data-stu-id="997f7-109">In Skype for Business Server, however, multiple trunks can now be assigned to a single PSTN gateway; this means that gateways and trunks are no longer one and the same.</span></span> <span data-ttu-id="997f7-110">В свою очередь, это означает, что администраторы должны использовать новый командлет [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) для просмотра сведений об отдельных канала SIP.</span><span class="sxs-lookup"><span data-stu-id="997f7-110">In turn, that means that administrators must use the new [Get-CsTrunk](https://docs.microsoft.com/powershell/module/skype/get-cstrunk?view=skype-ps) cmdlet in order to view information about an individual SIP trunk.</span></span>
  
### <a name="to-view-information-for-all-your-sip-trunks"></a><span data-ttu-id="997f7-111">Просмотр сведений о всех магистралях SIP</span><span class="sxs-lookup"><span data-stu-id="997f7-111">To view information for all your SIP trunks</span></span>

- <span data-ttu-id="997f7-112">Следующая команда возвращает сведения о всех магистралях SIP, используемых в организации.</span><span class="sxs-lookup"><span data-stu-id="997f7-112">The following command returns information about all the SIP trunks in use in your organization:</span></span>
    
  ```
  Get-CsTrunk
  ```

### <a name="to-view-information-for-a-specific-sip-trunk"></a><span data-ttu-id="997f7-113">Просмотр сведений об определенной магистрали SIP</span><span class="sxs-lookup"><span data-stu-id="997f7-113">To view information for a specific SIP trunk</span></span>

- <span data-ttu-id="997f7-114">Эта команда возвращает сведения только о магистрали SIP с идентификатором PstnGateway:192.168.0.240:</span><span class="sxs-lookup"><span data-stu-id="997f7-114">This command returns information only for the SIP trunk with the Identity PstnGateway:192.168.0.240:</span></span>
    
  ```
  Get-CsTrunk -Identity "PstnGateway:192.168.0.240"
  ```

### <a name="view-information-for-all-the-sip-trunks-assigned-to-a-pool"></a><span data-ttu-id="997f7-115">Просмотр информации обо всех линиях связи SIP, назначенных пулу</span><span class="sxs-lookup"><span data-stu-id="997f7-115">View information for all the SIP trunks assigned to a pool</span></span>

- <span data-ttu-id="997f7-116">В этом примере возвращаются сведения о всех магистралях SIP, назначенных пулу atl-cs-001.litwareinc.com.</span><span class="sxs-lookup"><span data-stu-id="997f7-116">In this example, information is returned for all the SIP trunks assigned to the pool atl-cs-001.litwareinc.com:</span></span>
    
  ```
  Get-CsTrunk -PoolFqdn "atl-cs-001.litwareinc.com"
  ```


