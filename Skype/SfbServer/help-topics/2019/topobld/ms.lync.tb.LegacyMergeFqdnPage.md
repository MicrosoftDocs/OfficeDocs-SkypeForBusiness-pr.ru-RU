---
title: Полное доменное имя для объединения с устаревшей версией
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.LegacyMergeFqdnPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d72841ff-3c4d-4233-a933-f3a95d75d89b
ROBOTS: NOINDEX, NOFOLLOW
description: Внутреннее полное доменное имя пула пограничного сервера доступа используется для различных сценариев, где внутренним пользователям взаимодействовать с внешними пользователями для федерации, удаленного доступа пользователей и общедоступной службы обмена Мгновенными сообщениями. Если со сбалансированной нагрузкой пограничный сервер был развернут в старой среды, введите полное доменное имя (FQDN) балансировщика нагрузки внутренней.
ms.openlocfilehash: df1def59a082942554e46bc7de75474c3df5aa23
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32220560"
---
# <a name="legacy-merge-fqdn"></a><span data-ttu-id="36b3c-104">Полное доменное имя для объединения с устаревшей версией</span><span class="sxs-lookup"><span data-stu-id="36b3c-104">Legacy Merge FQDN</span></span>
 
<span data-ttu-id="36b3c-105">**Внутреннее полное доменное имя пула пограничного сервера доступа** используется для различных сценариев, где внутренним пользователям взаимодействовать с внешними пользователями для федерации, удаленного доступа пользователей и общедоступной службы обмена Мгновенными сообщениями.</span><span class="sxs-lookup"><span data-stu-id="36b3c-105">The **Access Edge Pool internal FQDN** is used for a variety of scenarios where internal users communicate with external users for federation, remote user access, and public IM connectivity.</span></span> <span data-ttu-id="36b3c-106">Если со сбалансированной нагрузкой пограничный сервер был развернут в старой среды, введите полное доменное имя (FQDN) балансировщика нагрузки внутренней.</span><span class="sxs-lookup"><span data-stu-id="36b3c-106">If a load-balanced Edge Server was deployed in your legacy environment, enter the fully qualified domain name (FQDN) of the internal load balancer.</span></span>
  
<span data-ttu-id="36b3c-107">Значение **внутреннего SIP-порт** **5061** — порт SIP протокол TCP (Transmission Control) по умолчанию для общения с клиентами, прежних версий пулов переднего плана и серверов.</span><span class="sxs-lookup"><span data-stu-id="36b3c-107">The **Internal SIP access port** value of **5061** is the default Transmission Control Protocol (TCP) SIP port for communicating with clients, legacy Front End pools and servers.</span></span> <span data-ttu-id="36b3c-108">Если значение по умолчанию не используется, обновите **Внутренний SIP-порт:** значение.</span><span class="sxs-lookup"><span data-stu-id="36b3c-108">If the default value was not used, update the **Internal SIP access port:** value.</span></span>
  

