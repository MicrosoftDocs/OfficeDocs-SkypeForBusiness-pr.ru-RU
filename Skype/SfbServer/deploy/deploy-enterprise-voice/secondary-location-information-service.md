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
ms.openlocfilehash: fd70957526d193951b56211c0d5a6623a26419e2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830649"
---
# <a name="configure-a-secondary-location-information-service-in-skype-for-business-server"></a><span data-ttu-id="c30f6-103">Настройка дополнительной службы сведений о местоположении в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="c30f6-103">Configure a secondary Location Information service in Skype for Business Server</span></span>
 
<span data-ttu-id="c30f6-104">Настройка базы данных дополнительного источника расположения (SLS) для E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="c30f6-104">Configure a secondary location source (SLS) database for E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="c30f6-105">Skype для бизнеса Server предоставляет интерфейс веб-службы, который можно использовать, чтобы указать службе сведений о расположении базу данных дополнительного источника расположения (SLS).</span><span class="sxs-lookup"><span data-stu-id="c30f6-105">Skype for Business Server provides a web service interface that you can use to point the Location Information service to a Secondary Location Source (SLS) database.</span></span> <span data-ttu-id="c30f6-106">Интерфейс веб-службы, который подключается к базе данных SLS, должен соответствовать WSDL-службе сведений о расположении.</span><span class="sxs-lookup"><span data-stu-id="c30f6-106">The web service interface that connects to the SLS database must conform to Location Information service WSDL.</span></span> <span data-ttu-id="c30f6-107">Если настроены как база данных расположений, так и база данных дополнительных расположений, служба сведений о расположении сначала запрашивает базу данных расположений и, если совпадение не найдено, отправляет запрос о расположении от клиента в базу данных SLS.</span><span class="sxs-lookup"><span data-stu-id="c30f6-107">If both a location database and secondary location database are configured, the Location Information service first queries the location database, and if no match is found, sends the location request from the client to the SLS database.</span></span> <span data-ttu-id="c30f6-108">Если расположение существует в SLS, служба сведений о расположении отправляет его обратно клиенту.</span><span class="sxs-lookup"><span data-stu-id="c30f6-108">If the location exists in the SLS, the Location Information service then sends the location back to the client.</span></span> 
  
### <a name="to-configure-a-secondary-location-database"></a><span data-ttu-id="c30f6-109">Настройка базы данных дополнительного расположения</span><span class="sxs-lookup"><span data-stu-id="c30f6-109">To configure a Secondary Location database</span></span>

1. <span data-ttu-id="c30f6-110">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="c30f6-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c30f6-111">Чтобы настроить URL-адрес для расположения базы данных дополнительных расположений, запустите следующий cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c30f6-111">Run the following cmdlet to configure the URL for the location of the secondary location database.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -SecondaryLocationSourceURL "<web service url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="c30f6-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c30f6-112">See also</span></span>

[<span data-ttu-id="c30f6-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="c30f6-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

