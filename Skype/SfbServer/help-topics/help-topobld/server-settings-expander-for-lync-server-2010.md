---
title: Расширитель параметров сервера для Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: Для изменения свойств этого компьютера выполните следующие действия.
ms.openlocfilehash: c0eb39a516cbcce18940abe7936747fc18db9761
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215700"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="cfe7a-103">Расширитель параметров сервера для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="cfe7a-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="cfe7a-104">Для изменения свойств этого компьютера выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="cfe7a-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="cfe7a-p101">Измените **Полное доменное имя** компьютера. Эта запись должна совпадать с именем компьютера, определенным в службе доменных имен (DNS) и альтернативных именах субъекта (SAN) или в имени субъекта (SN) сертификата, связанного с данным компьютером.</span><span class="sxs-lookup"><span data-stu-id="cfe7a-p101">Edit the **Fully qualified domain name (FQDN)** for this computer. This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="cfe7a-107">Выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="cfe7a-107">You select one of the following:</span></span>
    
    <span data-ttu-id="cfe7a-108">**Использовать все настроенные IP-адреса**. Выберите этот параметр, чтобы использовать все настроенные IP-адреса компьютера.</span><span class="sxs-lookup"><span data-stu-id="cfe7a-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cfe7a-p102">Если в компьютере используется несколько IP-адресов, важно знать, что службы, связанные с этим компьютером, будут использовать все IP-адреса для всех служб. Если сервер или служба ожидают вызова по конкретному IP-адресу и порту, служба не сможет определить оптимальный IP-адрес для прослушивания.</span><span class="sxs-lookup"><span data-stu-id="cfe7a-p102">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services. If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="cfe7a-p103">**Ограничить использования службы выбранными IP-адресами**. Выберите этот параметр, если необходимо определить конкретные IP-адреса для **основного IP-адреса**, который этот компьютер будет прослушивать при взаимодействии с другими компьютерами и пулами в развертывании. Определите **IP-адрес для ТСОП** для конкретного IP-адреса, который компьютер и служба будут прослушивать и передавать данные на указанный шлюз ТСОП или IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="cfe7a-p103">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment. Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

