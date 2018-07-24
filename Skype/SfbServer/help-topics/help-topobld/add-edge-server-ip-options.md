---
title: Добавление параметров IP-адрес пограничного сервера
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: Microsoft Lync Server 2013 позволяет настроить IPv4 и IPv6-адреса для каждого интерфейса пограничного сервера и пограничный пул. Для этого выполните следующие действия.
ms.openlocfilehash: 8bf379c4ce8d23990cd004e8307b9bd4508bc45b
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2018
ms.locfileid: "20999571"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="5d6da-104">Добавление параметров IP-адрес пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="5d6da-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="5d6da-105">Microsoft Lync Server 2013 позволяет настроить IPv4 и IPv6-адреса для каждого интерфейса пограничного сервера и пограничный пул.</span><span class="sxs-lookup"><span data-stu-id="5d6da-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="5d6da-106">Для этого выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="5d6da-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="5d6da-107">**Включить IPv4 на внутренний интерфейс**: установите флажок, если вы хотите применить IPv4-адрес пограничного сервера или пула внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="5d6da-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="5d6da-108">**Включить IPv6 на внутренний интерфейс**: установите флажок, если вы хотите применить IPv6-адрес пограничного сервера или пула внутренний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="5d6da-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="5d6da-109">**Включить IPv4 на внешний интерфейс**: установите флажок, если вы хотите применить IPv4-адрес пограничного сервера или пула внешний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="5d6da-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="5d6da-110">**Включить IPv6 на внешний интерфейс**: установите флажок, если вы хотите применить IPv6-адрес пограничного сервера или пула внешний интерфейс пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="5d6da-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="5d6da-111">Можно также настроить пограничный сервер или пограничный пул для использования адрес перевода адрес сети для внешних IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="5d6da-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="5d6da-112">Для этого флажка **внешний IP-адрес этого пограничного пула преобразовываются NAT**.</span><span class="sxs-lookup"><span data-stu-id="5d6da-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="5d6da-113">Поддержка преобразования сетевых адресов.</span><span class="sxs-lookup"><span data-stu-id="5d6da-113">NAT support.</span></span> <span data-ttu-id="5d6da-114">Преобразование сетевых адресов (NAT) не поддерживается при использовании аппаратная Балансировка нагрузки, поэтому не устанавливайте флажок преобразование сетевых адресов, если выполняется развертывание пула пограничных серверов с балансировкой нагрузки оборудования.</span><span class="sxs-lookup"><span data-stu-id="5d6da-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

