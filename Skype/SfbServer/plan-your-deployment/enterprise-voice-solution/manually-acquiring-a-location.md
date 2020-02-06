---
title: Определение взаимодействия с пользователем при получении местоположения в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d37f67d3-e248-483b-b64c-3986559ef357
description: Планирование перемещаемых пользователей в E9 развертывание 1-1 с помощью провайдеров магистральных каналов SIP в корпоративной голосовой связи Skype для бизнеса Server.
ms.openlocfilehash: 85bf13325d3c7c16958877d50f49057a7f402226
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802719"
---
# <a name="define-the-user-experience-for-manually-acquiring-a-location-in-skype-for-business-server"></a><span data-ttu-id="3db98-103">Определение взаимодействия с пользователем при получении местоположения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="3db98-103">Define the user experience for manually acquiring a location in Skype for Business Server</span></span>
 
<span data-ttu-id="3db98-104">Планирование перемещаемых пользователей в E9 развертывание 1-1 с помощью провайдеров магистральных каналов SIP в корпоративной голосовой связи Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="3db98-104">Planning for roaming users in an E9-1-1 deployment using SIP trunking providers, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="3db98-p101">Если клиент размещается за пределами сети или в неопределенной подсети, пользователь может вручную указать расположение. Однако при выполнении аварийного вызова он будет сначала направляться диспетчеру национального/регионального центра обработки аварийных вызовов E9-1-1 (ECRC), прежде чем звонок будет передаваться в пункт реагирования PSAP. ECRC устно запросит у абонента адрес и затем направит вызов в соответствующий пункт PSAP на основе полученных данных.</span><span class="sxs-lookup"><span data-stu-id="3db98-p101">If a client is located outside the network, or in an undefined subnet, the user can manually enter a location. But during an emergency call, the call will first be routed to a national/regional E9-1-1 Emergency Call Response Center (ECRC) dispatcher before being routed to a Public Safety Answering Point (PSAP). The ECRC will verbally query the caller for a location and then forward the call to the appropriate PSAP, based on the information provided.</span></span> 
  
<span data-ttu-id="3db98-108">**Должны ли пользователи получать запрос на ввод местоположения, если оно не предоставлено службой сведений о расположении автоматически?**</span><span class="sxs-lookup"><span data-stu-id="3db98-108">**Should users be prompted to enter a location when one is not automatically provided by the Location Information service?**</span></span>
  
<span data-ttu-id="3db98-109">Например, если клиент подключен к неизвестной подсети, находится дома, в гостинице или где-либо еще за пределами сети, следует ли требовать ввода адреса пользователем?</span><span class="sxs-lookup"><span data-stu-id="3db98-109">For example, if a client is located in an undefined subnet, at home, in a hotel, or anywhere else outside the network, should the user be required to enter a location?</span></span>
    
<span data-ttu-id="3db98-p102">Вы можете задать режим работы клиента, настроив параметр **Требуется расположение** в политике расположения. Если задать для этого параметра значение "Нет", запрос на ввод расположения пользователем выдаваться не будет. Если задать значение "Да", пользователю будет выдаваться запрос на ввод расположения, но он сможет отклонить его. Если задать значение "Заявление об отказе", будет выдаваться запрос, а при попытке отклонить его будет отображаться заявление об отказе. В любом случае пользователь сможет продолжать использовать клиент как обычно.</span><span class="sxs-lookup"><span data-stu-id="3db98-p102">You can configure the **Location Required** setting in the location policy to define the client behavior. Setting this value to No means that the user will not be prompted for a location. Setting this value to Yes means that the user will be prompted for a location, but can dismiss the prompt. Setting this value to Disclaimer means that the user will be prompted for a location, and will be shown a disclaimer if they try to dismiss the prompt. In all cases, the user can continue to use the client as usual.</span></span>
    
<span data-ttu-id="3db98-115">Когда пользователь вручную вводит расположение, оно сопоставляется с MAC-адресом шлюза по умолчанию в сети клиента и хранится в таблице для каждого пользователя, которая находится на клиенте.</span><span class="sxs-lookup"><span data-stu-id="3db98-115">When a user manually enters a location, the location is mapped to the MAC address of the default gateway of the client's network, and is stored in a per-user table located on the client.</span></span> <span data-ttu-id="3db98-116">Когда пользователь возвращается к любому расположению, сохраненному ранее, клиент Skype для бизнеса автоматически настраивается в этом расположении.</span><span class="sxs-lookup"><span data-stu-id="3db98-116">When the user returns to any previously stored location, the Skype for Business client automatically sets itself to that location.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3db98-117">Вы можете изменить только текущее расположение клиента, но вы также можете удалить любое место, которое хранится в таблице локального пользователя.</span><span class="sxs-lookup"><span data-stu-id="3db98-117">You can modify only the current location of your client, but you can also delete any location stored in the local user's table.</span></span> 
  

