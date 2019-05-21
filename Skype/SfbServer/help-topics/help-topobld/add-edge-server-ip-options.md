---
title: Добавление IP-параметров пограничного сервера
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerIPOptionsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f458287f-e7a5-45f2-8393-3e1377be81d9
description: Microsoft Lync Server 2013 позволяет настраивать адреса IPv4 и IPv6 для каждого интерфейса пограничного сервера и пула Edge. Для этого выполните указанные ниже действия.
ms.openlocfilehash: de0b0e0c050721a4fb54a450db89e34f65ea7f7f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34293975"
---
# <a name="add-edge-server-ip-options"></a><span data-ttu-id="df4c7-104">Добавление IP-параметров пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="df4c7-104">Add Edge Server IP Options</span></span>
 
<span data-ttu-id="df4c7-105">Microsoft Lync Server 2013 позволяет настраивать адреса IPv4 и IPv6 для каждого интерфейса пограничного сервера и пула Edge.</span><span class="sxs-lookup"><span data-stu-id="df4c7-105">Microsoft Lync Server 2013 allows you to configure IPv4 and IPv6 addresses for each interface for the Edge Server and Edge pool.</span></span> <span data-ttu-id="df4c7-106">Для этого выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="df4c7-106">To do this, you do the following:</span></span>
  
- <span data-ttu-id="df4c7-107">**Включить IPv4 на внутреннем интерфейсе**: установите флажок, если вы хотите применить IPv4-адрес к внешнему интерфейсу пограничного сервера или пула Edge.</span><span class="sxs-lookup"><span data-stu-id="df4c7-107">**Enable IPv4 on internal interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="df4c7-108">**Включить IPv6 на внутреннем интерфейсе**: установите флажок, если вы хотите применить IPv6-адрес к внешнему интерфейсу пограничного сервера или пула Edge.</span><span class="sxs-lookup"><span data-stu-id="df4c7-108">**Enable IPv6 on internal interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool internal interface</span></span>
    
- <span data-ttu-id="df4c7-109">**Включение IPv4 во внешнем интерфейсе**: Установите этот флажок, если вы хотите применить IPv4-адрес к внешнему серверу пограничного сервера или пулу пограничных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="df4c7-109">**Enable IPv4 on external interface**: Select the check box if you want to apply an IPv4 address to the Edge Server or Edge pool external interface</span></span>
    
- <span data-ttu-id="df4c7-110">**Включить IPv6 во внешнем интерфейсе**: установите флажок, если вы хотите применить IPv6-адрес к внешнему серверу или пулу пограничных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="df4c7-110">**Enable IPv6 on external interface**: Select the check box if you want to apply an IPv6 address to the Edge Server or Edge pool external interface</span></span>
    
<span data-ttu-id="df4c7-111">Вы также можете настроить пограничный сервер или пул EDGE, чтобы использовать адрес преобразования сетевых адресов для внешних IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="df4c7-111">You can also configure the Edge Server or Edge pool to use a network address translation address for the external IP addresses.</span></span> <span data-ttu-id="df4c7-112">Для этого установите флажок **внешний IP-адрес этого пограничного пула преобразуется посредством NAT**.</span><span class="sxs-lookup"><span data-stu-id="df4c7-112">You do this by selecting the check box **The external IP address of this Edge pool is translated by NAT**.</span></span>
  
<span data-ttu-id="df4c7-113">Поддержка NAT.</span><span class="sxs-lookup"><span data-stu-id="df4c7-113">NAT support.</span></span> <span data-ttu-id="df4c7-114">Преобразование сетевых адресов (NAT) не поддерживается при использовании аппаратной балансировки нагрузки, поэтому не выбирайте параметр NAT при развертывании пула пограничного сервера с аппаратной балансировкой нагрузки.</span><span class="sxs-lookup"><span data-stu-id="df4c7-114">Network address translation (NAT) is not supported when you are using hardware load balancing, so do not select the NAT option if you are deploying an Edge Server pool with hardware load balancing.</span></span>
  

