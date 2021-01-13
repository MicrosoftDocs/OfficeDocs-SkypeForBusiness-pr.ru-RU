---
title: Добавление IP-параметров пограничного сервера
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
ROBOTS: NOINDEX, NOFOLLOW
description: 'Skype для бизнеса Server позволяет настраивать IPv4- и IPv6-адреса для каждого интерфейса для edge server и edge pool. Для этого выполните следующие действия:'
ms.openlocfilehash: f940e0480c51b1a2541386401a71f0d7d9818566
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49801079"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="a2c22-104">Добавление IP-параметров пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="a2c22-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="a2c22-105">Skype для бизнеса Server позволяет настраивать IPv4- и IPv6-адреса для каждого интерфейса для edge server и edge pool.</span><span class="sxs-lookup"><span data-stu-id="a2c22-105">Skype for Business Server allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="a2c22-106">Для этого выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="a2c22-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="a2c22-107">**Включить IPv4 на** внутреннем интерфейсе: выберите этот ящик, чтобы применить IPv4-адрес к внутреннему интерфейсу сервера или пула.</span><span class="sxs-lookup"><span data-stu-id="a2c22-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="a2c22-108">**Включить IPv6 во** внутреннем интерфейсе: если нужно применить IPv6-адрес к внутреннему интерфейсу edge Server или пула edge</span><span class="sxs-lookup"><span data-stu-id="a2c22-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="a2c22-109">**Включить IPv4 на** внешнем интерфейсе: если вы хотите применить IPv4-адрес к внешнему интерфейсу edge Server или пула edge</span><span class="sxs-lookup"><span data-stu-id="a2c22-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="a2c22-110">**Включить IPv6 на** внешнем интерфейсе: если вы хотите применить IPv6-адрес к внешнему интерфейсу edge Server или пула edge</span><span class="sxs-lookup"><span data-stu-id="a2c22-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="a2c22-111">Кроме того, можно настроить использование адреса перевода сетевых адресов для внешних IP-адресов на сервере или в пуле.</span><span class="sxs-lookup"><span data-stu-id="a2c22-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="a2c22-112">Для этого установите флажок **Внешний IP-адрес данного пограничного пула преобразуется системой NAT**.</span><span class="sxs-lookup"><span data-stu-id="a2c22-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="a2c22-p104">Поддержка NAT. Преобразование сетевых адресов (NAT) не поддерживается при использовании балансировки нагрузки оборудования, поэтому не выбирайте параметр NAT при развертывании пула пограничного сервера в сочетании с балансировкой нагрузки оборудования.</span><span class="sxs-lookup"><span data-stu-id="a2c22-p104">NAT support. Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

