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
ms.openlocfilehash: eb1947f24968dccc6f45b6d8ea3a7df42282a58f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804159"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="36b45-103">Настройка приложения SNMP в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="36b45-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="36b45-104">Настройка приложения SNMP для работы с E9-1-1 в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="36b45-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="36b45-105">Skype для бизнеса Server включает стандартный интерфейс веб-службы, который можно использовать для подключения службы сведений о расположении к приложениям SNMP, которые соответствуют MAC-адресам с данными о портах и коммутаторах.</span><span class="sxs-lookup"><span data-stu-id="36b45-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="36b45-106">Если приложение SNMP установлено и службе сведений о расположении не удается найти совпадение в базе данных расположений, служба сведений о расположении автоматически запрашивает приложение с помощью MAC-адреса, предоставленного клиентом.</span><span class="sxs-lookup"><span data-stu-id="36b45-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="36b45-107">Затем служба сведений о расположении использует порт и сведения о коммутаторе, возвращенные приложением SNMP, для повторного запроса базы данных расположений.</span><span class="sxs-lookup"><span data-stu-id="36b45-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="36b45-108">MAC-адреса недоступны на компьютерах с Windows 8.</span><span class="sxs-lookup"><span data-stu-id="36b45-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="36b45-109">Настройка URL-адреса приложения SNMP</span><span class="sxs-lookup"><span data-stu-id="36b45-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="36b45-110">Запустите оболочку управления Skype для бизнеса Server: нажмите кнопку "Начните", выберите "Все программы", "Skype для бизнеса **2015",** а затем щелкните "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="36b45-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="36b45-111">Запустите следующий командлет для настройки URL-адреса приложения SNMP.</span><span class="sxs-lookup"><span data-stu-id="36b45-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```powershell
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="36b45-112">См. также</span><span class="sxs-lookup"><span data-stu-id="36b45-112">See also</span></span>

[<span data-ttu-id="36b45-113">Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="36b45-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

