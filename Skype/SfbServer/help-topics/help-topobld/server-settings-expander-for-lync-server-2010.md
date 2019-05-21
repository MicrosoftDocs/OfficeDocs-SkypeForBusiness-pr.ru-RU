---
title: Расширитель параметров сервера для Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MachineSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e2309ade-f9c7-4cd1-b135-45bf73b0441f
description: Чтобы изменить свойства компьютера, выполните указанные ниже действия.
ms.openlocfilehash: 28261b3637040acda70218f23101b4337b1f90c3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34297612"
---
# <a name="server-settings-expander-for-lync-server-2010"></a><span data-ttu-id="f1000-103">Расширитель параметров сервера для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="f1000-103">Server Settings Expander for Lync Server 2010</span></span>
 
<span data-ttu-id="f1000-104">Чтобы изменить свойства компьютера, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="f1000-104">To edit the properties for this computer, you do the following:</span></span>
  
- <span data-ttu-id="f1000-105">Измените полное **доменное имя (FQDN)** для этого компьютера.</span><span class="sxs-lookup"><span data-stu-id="f1000-105">Edit the **Fully qualified domain name (FQDN)** for this computer.</span></span> <span data-ttu-id="f1000-106">Этот параметр должен совпадать с именем компьютера, указанным в службе доменных имен (DNS), а также в списке альтернативных имен субъектов (SAN) или имени субъекта (SN) сертификата, связанного с этим компьютером.</span><span class="sxs-lookup"><span data-stu-id="f1000-106">This entry must match the computer name as it is defined in the domain name system (DNS), and in subject alternative names (SAN) or subject name (SN) of the certificate associated with this computer.</span></span>
    
- <span data-ttu-id="f1000-107">Вы выбираете один из указанных ниже вариантов.</span><span class="sxs-lookup"><span data-stu-id="f1000-107">You select one of the following:</span></span>
    
    <span data-ttu-id="f1000-108">**Использовать все настроенные IP-адреса**: Выберите этот параметр, чтобы использовать все НАСТРОЕННЫЕ IP-адреса на компьютере.</span><span class="sxs-lookup"><span data-stu-id="f1000-108">**Use all configured IP addresses**: Select this to use all configured IP addresses on the computer.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="f1000-109">Если на компьютере установлено несколько IP-адресов, необходимо помнить, что службы, связанные с этим компьютером, будут использовать все IP-адреса для всех служб.</span><span class="sxs-lookup"><span data-stu-id="f1000-109">If the computer has multiple IP addresses, you must be aware that the services associated with this computer will use all IP addresses for all services.</span></span> <span data-ttu-id="f1000-110">Если сервер или служба ожидает связь с определенным IP-адресом и портом, служба может не выбрать оптимальный IP-адрес для прослушивания.</span><span class="sxs-lookup"><span data-stu-id="f1000-110">If a listening server or service is expecting communication of a specific IP address and port, the service may not make the best selection of which IP address to listen on.</span></span> 
  
    <span data-ttu-id="f1000-111">**Ограничение использования службы до выбранных IP-адресов**: Выберите этот параметр, если вы хотите определить конкретные IP-адреса для **основного IP-адреса** , который компьютер будет прослушивать для обмена данными с другими компьютерами и пулами в развертывании.</span><span class="sxs-lookup"><span data-stu-id="f1000-111">**Limit service usage to selected IP addresses**: Select this option if you want to define specific IP addresses for the **Primary IP address** that this computer will listen on for communication from other computers and pools in the deployment.</span></span> <span data-ttu-id="f1000-112">Определите **IP-адрес PSTN** для определенного IP-адреса, который компьютер и служба будет прослушивать для обмена информацией и отправлять сообщения на определенный шлюз PSTN или IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="f1000-112">Define **PSTN IP address** for the specific IP address that the computer and service will listen for communications and send communications to the defined PSTN gateway or IP-PBX.</span></span>
    

