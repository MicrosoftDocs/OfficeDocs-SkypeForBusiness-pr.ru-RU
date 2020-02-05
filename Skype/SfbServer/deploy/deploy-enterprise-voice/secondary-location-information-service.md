---
title: Настройка дополнительной службы сведений о расположении в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Настройте базу данных дополнительного расположения (СЛС) для E9-1-1 в корпоративной голосовой связи Skype для бизнеса Server.
ms.openlocfilehash: 28168bb10017ccc1e56ce26bb5a88629f19aff41
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767082"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="50a0c-103">Настройка дополнительной службы сведений о расположении в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="50a0c-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="50a0c-104">Настройте базу данных дополнительного расположения (СЛС) для E9-1-1 в корпоративной голосовой связи Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="50a0c-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="50a0c-105">Skype для бизнеса Server предоставляет интерфейс веб-службы, который можно использовать для указания службы сведений о расположении в базу данных дополнительного расположения (СЛС).</span><span class="sxs-lookup"><span data-stu-id="50a0c-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="50a0c-106">Интерфейс веб-службы, который подключается к базе данных СЛС, должен соответствовать WSDL службы сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="50a0c-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="50a0c-107">Если вы настроили базу данных расположения и дополнительную базу данных расположения, Служба сведений о расположении сначала запрашивает базу данных расположения, а если совпадений не найдено, отправляет запрос на расположение от клиента в базу данных СЛС.</span><span class="sxs-lookup"><span data-stu-id="50a0c-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="50a0c-108">Если расположение находится в СЛС, служба сведения о местоположении затем отправляет клиенту расположение обратно.</span><span class="sxs-lookup"><span data-stu-id="50a0c-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="50a0c-109">Настройка базы данных дополнительных расположений</span><span class="sxs-lookup"><span data-stu-id="50a0c-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="50a0c-110">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="50a0c-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="50a0c-111">Чтобы настроить URL-адрес базы данных дополнительных расположений, выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="50a0c-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="50a0c-112">См. также</span><span class="sxs-lookup"><span data-stu-id="50a0c-112">See also</span></span>

[<span data-ttu-id="50a0c-113">Set-Ксвебсервицеконфигуратион</span><span class="sxs-lookup"><span data-stu-id="50a0c-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

