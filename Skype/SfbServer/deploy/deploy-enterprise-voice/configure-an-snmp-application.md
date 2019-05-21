---
title: Настройка SNMP-приложения в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Настройте приложение SNMP для работы с E9-1-1 в корпоративной голосовой связи Skype для бизнеса Server.
ms.openlocfilehash: 575c982dae20ed085e49690edfbb141786390516
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303420"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="8db43-103">Настройка SNMP-приложения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="8db43-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="8db43-104">Настройте приложение SNMP для работы с E9-1-1 в корпоративной голосовой связи Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="8db43-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="8db43-105">В Skype для бизнеса Server есть стандартный интерфейс веб-службы, который можно использовать для подключения службы сведений о расположении к приложениям SNMP, которые соответствуют MAC-адресам с портом и коммутатором.</span><span class="sxs-lookup"><span data-stu-id="8db43-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="8db43-106">Если установлено приложение SNMP и служба "сведения о местоположении" не может найти соответствие в базе данных расположения, Служба сведений о расположении автоматически запрашивает это приложение, используя MAC-адрес, предоставленный клиентом.</span><span class="sxs-lookup"><span data-stu-id="8db43-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="8db43-107">Затем служба сведения о местоположении использует данные порта и коммутатора, возвращенные приложением SNMP, для повторного запроса к базе данных о расположении.</span><span class="sxs-lookup"><span data-stu-id="8db43-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8db43-108">MAC-адреса недоступны на компьютерах под управлением Windows 8.</span><span class="sxs-lookup"><span data-stu-id="8db43-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="8db43-109">Настройка URL-адреса приложения SNMP</span><span class="sxs-lookup"><span data-stu-id="8db43-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="8db43-110">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="8db43-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="8db43-111">Запустите следующий командлет для настройки URL-адреса приложения SNMP.</span><span class="sxs-lookup"><span data-stu-id="8db43-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="8db43-112">См. также</span><span class="sxs-lookup"><span data-stu-id="8db43-112">See also</span></span>

[<span data-ttu-id="8db43-113">Set-Ксвебсервицеконфигуратион</span><span class="sxs-lookup"><span data-stu-id="8db43-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

