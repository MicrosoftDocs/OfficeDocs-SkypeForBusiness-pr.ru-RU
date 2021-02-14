---
title: Расширитель параметров сервера для Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 8b05fa82bcfeb10caa201ce303ddbbd8e8378b7e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806659"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="fe2b3-103">Расширитель параметров сервера для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="fe2b3-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="fe2b3-104">Для изменения свойств этого компьютера выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="fe2b3-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="fe2b3-p101">Измените **Полное доменное имя** компьютера. Эта запись должна совпадать с именем компьютера, определенным в службе доменных имен (DNS) и альтернативных именах субъекта (SAN) или в имени субъекта (SN) сертификата, связанного с данным компьютером.</span><span class="sxs-lookup"><span data-stu-id="fe2b3-p101">Edit the **Fully qualified domain name (FQDN)** for this computer. This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="fe2b3-107">Выберите один из следующих параметров.</span><span class="sxs-lookup"><span data-stu-id="fe2b3-107">You select one of the following:</span></span>
    
    <span data-ttu-id="fe2b3-108">**Использовать все настроенные IP-адреса**. Выберите этот параметр, чтобы использовать все настроенные IP-адреса компьютера.</span><span class="sxs-lookup"><span data-stu-id="fe2b3-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="fe2b3-p102">Если в компьютере используется несколько IP-адресов, важно знать, что службы, связанные с этим компьютером, будут использовать все IP-адреса для всех служб. Если сервер или служба ожидают вызова по конкретному IP-адресу и порту, служба не сможет определить оптимальный IP-адрес для прослушивания.</span><span class="sxs-lookup"><span data-stu-id="fe2b3-p102">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services. If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="fe2b3-p103">**Ограничить использования службы выбранными IP-адресами**. Выберите этот параметр, если необходимо определить конкретные IP-адреса для **основного IP-адреса**, который этот компьютер будет прослушивать при взаимодействии с другими компьютерами и пулами в развертывании. Определите **IP-адрес для ТСОП** для конкретного IP-адреса, который компьютер и служба будут прослушивать и передавать данные на указанный шлюз ТСОП или IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="fe2b3-p103">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment. Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

