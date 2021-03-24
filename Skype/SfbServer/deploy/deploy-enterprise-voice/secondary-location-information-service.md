---
title: Настройка дополнительной службы сведений о местоположении в Skype для бизнеса Server
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
ms.assetid: 083ffbc6-7c18-4141-85f9-8825b62c3d10
description: Настройка базы данных дополнительного источника расположения (SLS) для E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 7a81d8573ca0425d4d445dc00f257f014a39d8c6
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103385"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="c7034-103">Настройка дополнительной службы сведений о местоположении в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c7034-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="c7034-104">Настройка базы данных дополнительного источника расположения (SLS) для E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="c7034-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="c7034-105">Skype для бизнеса Server предоставляет интерфейс веб-службы, который можно использовать для указать службу сведений о расположении на базу данных secondary Location Source (SLS).</span><span class="sxs-lookup"><span data-stu-id="c7034-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="c7034-106">Интерфейс веб-службы, подключается к базе данных SLS, должен соответствовать службе сведений о расположении WSDL.</span><span class="sxs-lookup"><span data-stu-id="c7034-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="c7034-107">Если настроена база данных расположения и вторичная база данных расположения, служба сведений о расположении сначала запрашивает базу данных расположения, а если совпадение не найдено, отправляет запрос о расположении от клиента в базу данных SLS.</span><span class="sxs-lookup"><span data-stu-id="c7034-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="c7034-108">Если расположение существует в службе SLS, служба сведений о расположении отправляет его клиенту.</span><span class="sxs-lookup"><span data-stu-id="c7034-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="c7034-109">Настройка базы данных вторичного расположения</span><span class="sxs-lookup"><span data-stu-id="c7034-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="c7034-110">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="c7034-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c7034-111">Запустите следующий комдлет, чтобы настроить URL-адрес для расположения базы данных вторичного расположения.</span><span class="sxs-lookup"><span data-stu-id="c7034-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="c7034-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c7034-112">See also</span></span>

[<span data-ttu-id="c7034-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="c7034-113">Set-CsWebServiceConfiguration</span></span>](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)