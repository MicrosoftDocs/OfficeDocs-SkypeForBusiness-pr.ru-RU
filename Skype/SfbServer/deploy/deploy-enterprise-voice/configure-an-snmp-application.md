---
title: Настройка SNMP-приложения в Скайп для Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: c4b4a736-3b2e-45b9-a965-19d22161ad57
description: Настройка SNMP-приложения для работы с E9-1-1 в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: 9c325777b43c455016657caf4e15316a07282b52
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20992437"
---
# <a name="configure-an-snmp-application-in-skype-for-business-server"></a><span data-ttu-id="0449c-103">Настройка SNMP-приложения в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="0449c-103">Configure an SNMP application in Skype for Business Server</span></span>
 
<span data-ttu-id="0449c-104">Настройка SNMP-приложения для работы с E9-1-1 в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="0449c-104">Configure an SNMP application to work with E9-1-1 in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="0449c-105">Скайп для Business Server включает в себя стандартных веб-интерфейс службы, которые можно использовать для подключения к сети протокола SNMP (Simple Management) приложений, которые соответствуют MAC-адреса с портом и сведений о переключении службе информирования о местонахождении.</span><span class="sxs-lookup"><span data-stu-id="0449c-105">Skype for Business Server includes a standard web service interface that you can use to connect the Location Information service to Simple Network Management Protocol (SNMP) applications that match MAC addresses with port and switch information.</span></span> 
  
<span data-ttu-id="0449c-106">Если установлено приложение SNMP и происходит сбой службы сведения о расположении для поиска в базе данных местонахождения, сведения о расположении службы автоматически отправляет запрос приложения с помощью MAC-адрес, заданных клиентом.</span><span class="sxs-lookup"><span data-stu-id="0449c-106">If an SNMP application is installed and the Location Information service fails to find a match in the location database, the Location Information service automatically queries the application by using the MAC address provided by the client.</span></span> <span data-ttu-id="0449c-107">Сведения о расположении службы затем использует порт и переключатель информацию, возвращенную приложения SNMP для запроса базы данных местоположений еще раз.</span><span class="sxs-lookup"><span data-stu-id="0449c-107">The Location Information service then uses the port and switch information returned by the SNMP application to query the location database again.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0449c-108">MAC-адреса недоступны на компьютерах под управлением Windows 8.</span><span class="sxs-lookup"><span data-stu-id="0449c-108">MAC addresses are not available on computers running Windows 8.</span></span> 
  
### <a name="to-configure-the-snmp-application-url"></a><span data-ttu-id="0449c-109">Настройка URL-адреса приложения SNMP</span><span class="sxs-lookup"><span data-stu-id="0449c-109">To configure the SNMP application URL</span></span>

1.  <span data-ttu-id="0449c-110">Запустите командную консоль Skype для бизнеса: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Skype для бизнеса 2015** и щелкните элемент **Командная консоль Skype для бизнеса**.</span><span class="sxs-lookup"><span data-stu-id="0449c-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="0449c-111">Запустите следующий командлет для настройки URL-адреса приложения SNMP.</span><span class="sxs-lookup"><span data-stu-id="0449c-111">Run the following cmdlet to configure the URL for the SNMP application.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MACResolverUrl "<SNMP application url>" 
   ```

## <a name="see-also"></a><span data-ttu-id="0449c-112">См. также</span><span class="sxs-lookup"><span data-stu-id="0449c-112">See also</span></span>

[<span data-ttu-id="0449c-113">Командлет Set-CsWebServiceConfiguration</span><span class="sxs-lookup"><span data-stu-id="0449c-113">Set-CsWebServiceConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cswebserviceconfiguration?view=skype-ps)

