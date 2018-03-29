---
title: Настройка SNMP-приложения в Skype для бизнеса Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Настройка SNMP-приложения для работы с E9-1-1 в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 5c10d00e05979c2a3e0efff015da61e5ff2c6ee9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-an-snmp-application-in-skype-for-business-server-2015"></a><span data-ttu-id="c601a-103">Настройка SNMP-приложения в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="c601a-103">Configure an SNMP application in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c601a-104">Настройка SNMP-приложения для работы с E9-1-1 в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="c601a-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="c601a-105">Скайп для Business Server включает в себя стандартных веб-интерфейс службы, которые можно использовать для подключения к сети протокола SNMP (Simple Management) приложений, которые соответствуют MAC-адреса с портом и сведений о переключении службе информирования о местонахождении.</span><span class="sxs-lookup"><span data-stu-id="c601a-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="c601a-106">Если установлено приложение SNMP и происходит сбой службы сведения о расположении для поиска в базе данных местонахождения, сведения о расположении службы автоматически отправляет запрос приложения с помощью MAC-адрес, заданных клиентом.</span><span class="sxs-lookup"><span data-stu-id="c601a-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="c601a-107">Сведения о расположении службы затем использует порт и переключатель информацию, возвращенную приложения SNMP для запроса базы данных местоположений еще раз.</span><span class="sxs-lookup"><span data-stu-id="c601a-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c601a-108">MAC-адреса недоступны на компьютерах под управлением Windows 8.</span><span class="sxs-lookup"><span data-stu-id="c601a-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="c601a-109">Настройка URL-адреса приложения SNMP</span><span class="sxs-lookup"><span data-stu-id="c601a-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="c601a-110">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="c601a-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="c601a-111">Запустите следующий командлет для настройки URL-адреса приложения SNMP.</span><span class="sxs-lookup"><span data-stu-id="c601a-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="c601a-112">См. также</span><span class="sxs-lookup"><span data-stu-id="c601a-112">See also</span></span>

#### 

[<span data-ttu-id="c601a-113">Командлет Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="c601a-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

