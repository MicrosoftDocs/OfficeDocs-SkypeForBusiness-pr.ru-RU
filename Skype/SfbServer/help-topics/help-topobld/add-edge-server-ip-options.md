---
title: Добавление IP-параметров пограничного сервера
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
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: 'Microsoft Lync Server 2013 позволяет настраивать IPv4-и IPv6-адреса для каждого интерфейса пограничного сервера и пограничного пула. Для этого выполните следующие действия:'
ms.openlocfilehash: 2c68fcfcb2e99759536224889a818639b61d5fcc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219794"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="6b4da-104">Добавление IP-параметров пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="6b4da-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="6b4da-105">Microsoft Lync Server 2013 позволяет настраивать IPv4-и IPv6-адреса для каждого интерфейса пограничного сервера и пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="6b4da-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="6b4da-106">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="6b4da-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="6b4da-107">**Включить IPv4 во внутреннем интерфейсе**: Установите этот флажок, если требуется применить IPv4-адрес к пограничному серверу или внутреннему интерфейсу пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="6b4da-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="6b4da-108">**Включить IPv6 во внутреннем интерфейсе**: Установите этот флажок, если вы хотите применить IPv6-адрес к внутреннему интерфейсу пограничного сервера или пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="6b4da-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="6b4da-109">**Включить IPv4 на внешнем интерфейсе**: Установите этот флажок, если требуется применить IPv4-адрес к пограничному серверу или внешнему интерфейсу пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="6b4da-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="6b4da-110">**Включить IPv6 на внешнем интерфейсе**: Установите этот флажок, если требуется применить IPv6-адрес к внешнему серверу или внешнему интерфейсу пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="6b4da-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="6b4da-111">Вы также можете настроить пограничный сервер или пограничный пул на использование адреса преобразования сетевых адресов для внешних IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="6b4da-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="6b4da-112">Для этого установите флажок **Внешний IP-адрес данного пограничного пула преобразуется системой NAT**.</span><span class="sxs-lookup"><span data-stu-id="6b4da-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="6b4da-p104">Поддержка NAT. Преобразование сетевых адресов (NAT) не поддерживается при использовании балансировки нагрузки оборудования, поэтому не выбирайте параметр NAT при развертывании пула пограничного сервера в сочетании с балансировкой нагрузки оборудования.</span><span class="sxs-lookup"><span data-stu-id="6b4da-p104">NAT support. Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

