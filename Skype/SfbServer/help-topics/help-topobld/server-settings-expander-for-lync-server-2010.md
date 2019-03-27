---
title: Расширитель параметров сервера для Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: Для изменения свойств этого компьютера, выполните следующие действия.
ms.openlocfilehash: 4b05c52d92d3702c76afd6c7b682c1c9ffda7ab9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879723"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="556bd-103">Расширитель параметров сервера для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="556bd-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="556bd-104">Для изменения свойств этого компьютера, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="556bd-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="556bd-105">Измените **полное доменное имя (FQDN)** для данного компьютера.</span><span class="sxs-lookup"><span data-stu-id="556bd-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="556bd-106">В этой записи должно совпадать с именем компьютера, как оно указано в доменных имен (DNS) и альтернативные имена субъекта (SAN) или имя субъекта (SN) сертификат, связанный с этим компьютером.</span><span class="sxs-lookup"><span data-stu-id="556bd-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="556bd-107">Выберите один из следующих:</span><span class="sxs-lookup"><span data-stu-id="556bd-107">You select one of the following:</span></span>
    
    <span data-ttu-id="556bd-108">**Использовать все настроенные IP-адреса**: выберите этот параметр для использовать все настроенные IP-адреса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="556bd-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="556bd-109">Если на компьютере установлено несколько IP-адресов, необходимо принять во внимание, что службы, связанные с этим компьютером будет использовать все IP-адреса для всех служб.</span><span class="sxs-lookup"><span data-stu-id="556bd-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="556bd-110">Если требующую связи определенный IP-адрес и порт прослушивания сервера или службы, служба не может сделать лучший выбор IP-адреса для прослушивания.</span><span class="sxs-lookup"><span data-stu-id="556bd-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="556bd-111">**Ограничьте использование службы выбранных IP-адресов**: выберите этот параметр, если нужно определить конкретные IP-адреса для **основной IP-адрес** , который будет прослушивать этот компьютер для подключений от других компьютерах и в пулах в развертывании.</span><span class="sxs-lookup"><span data-stu-id="556bd-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="556bd-112">Определение **PSTN IP-адрес** для определенного IP-адреса, что компьютер и службы будут прослушивать коммуникаций и отправить сообщения для определенного шлюз ТСОП или IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="556bd-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

