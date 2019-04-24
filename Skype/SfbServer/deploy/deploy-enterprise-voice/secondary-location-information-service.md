---
title: Настройка дополнительных сведений о расположении службы в Скайп для Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Настройка базы данных-источника (SLS) дополнительных расположений для E9-1-1 в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: d5ff35be38030cc6081224e11431463e30696e4e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222986"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="2a567-103">Настройка дополнительных сведений о расположении службы в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="2a567-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="2a567-104">Настройка базы данных-источника (SLS) дополнительных расположений для E9-1-1 в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="2a567-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="2a567-105">Скайп для Business Server предоставляет интерфейс веб-службы, которые можно использовать для указания службе информирования о местонахождении к базе данных дополнительного источника местоположения (SLS).</span><span class="sxs-lookup"><span data-stu-id="2a567-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="2a567-106">Интерфейс веб-службы, который подключается к базе данных SLS должен соответствовать типу WSDL службы и сведения о расположении.</span><span class="sxs-lookup"><span data-stu-id="2a567-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="2a567-107">Если расположение базы данных и базы данных дополнительных расположений службе информирования о местонахождении сначала отправляет запрос базы данных местоположений и если совпадение не найдено, отправляет запрос местоположения из клиента в SLS базу данных.</span><span class="sxs-lookup"><span data-stu-id="2a567-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="2a567-108">Если оно существует в SLS, сведения о расположении службы отправляет расположение клиенту.</span><span class="sxs-lookup"><span data-stu-id="2a567-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="2a567-109">Настройка базы данных дополнительных расположений</span><span class="sxs-lookup"><span data-stu-id="2a567-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="2a567-110">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="2a567-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="2a567-111">Чтобы настроить URL-адрес базы данных дополнительных расположений, выполните следующий командлет.</span><span class="sxs-lookup"><span data-stu-id="2a567-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="2a567-112">См. также</span><span class="sxs-lookup"><span data-stu-id="2a567-112">See also</span></span>

[<span data-ttu-id="2a567-113">Командлет Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="2a567-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

