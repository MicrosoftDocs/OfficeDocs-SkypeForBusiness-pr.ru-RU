---
title: Настройка приложения SNMP в Skype для бизнеса Server
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
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Настройка приложения SNMP для работы с E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: f8b4c7503524dacdc20e85fc68f0a79286e38c2e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103635"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="4ec51-103">Настройка приложения SNMP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="4ec51-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="4ec51-104">Настройка приложения SNMP для работы с E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="4ec51-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="4ec51-105">Skype для бизнеса Server включает стандартный интерфейс веб-службы, который можно использовать для подключения службы информации о расположении к приложениям простого протокола управления сетью (SNMP), которые соответствуют mac-адресам с портом и сведениями о переключениях.</span><span class="sxs-lookup"><span data-stu-id="4ec51-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="4ec51-106">Если приложение SNMP установлено и служба сведений о расположении не находит совпадение в базе данных расположения, служба информации о расположении автоматически запрашивает приложение с помощью mac-адреса, предоставленного клиентом.</span><span class="sxs-lookup"><span data-stu-id="4ec51-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="4ec51-107">Затем служба сведений о расположении использует порт и переключение сведений, возвращаемой приложением SNMP, для повторного запроса базы данных расположения.</span><span class="sxs-lookup"><span data-stu-id="4ec51-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4ec51-108">Mac-адреса недоступны на компьютерах с Windows 8.</span><span class="sxs-lookup"><span data-stu-id="4ec51-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="4ec51-109">Настройка URL-адреса приложения SNMP</span><span class="sxs-lookup"><span data-stu-id="4ec51-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="4ec51-110">Запустите оболочку управления Skype для бизнес-серверов: нажмите кнопку Начните, щелкните Все **программы,** щелкните Skype для бизнеса **2015,** а затем нажмите **кнопку Skype для управления бизнес-серверами.**</span><span class="sxs-lookup"><span data-stu-id="4ec51-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="4ec51-111">Запустите следующий командлет для настройки URL-адреса приложения SNMP.</span><span class="sxs-lookup"><span data-stu-id="4ec51-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="4ec51-112">См. также</span><span class="sxs-lookup"><span data-stu-id="4ec51-112">See also</span></span>

[<span data-ttu-id="4ec51-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="4ec51-113">Set-CsWebServiceConfiguration</span></span>](/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)