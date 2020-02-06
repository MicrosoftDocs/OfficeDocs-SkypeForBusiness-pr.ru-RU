---
title: Связывание сервера переднего плана с пограничным
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
ROBOTS: NOINDEX, NOFOLLOW
description: С каждым пулом переднего плана может быть связан только один пограничный сервер или пограничный пул. Если к сайту разрешен доступ внешних пользователей, можно включить поддержку удаленных пользователей. Возможна также поддержка федеративных пользователей, включая пользователей конкретных поставщиков общедоступных услуг связи для обмена мгновенными сообщениями (например, Windows Live), и поддержка анонимных пользователей.
ms.openlocfilehash: 8c59423562ebc511e8947d9448010b1f097df96d
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793997"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="72a18-105">Связывание сервера переднего плана с пограничным</span><span class="sxs-lookup"><span data-stu-id="72a18-105">Associate Front End With Edge</span></span>

<span data-ttu-id="72a18-p102">С каждым пулом переднего плана может быть связан только один пограничный сервер или пограничный пул. Если к сайту разрешен доступ внешних пользователей, можно включить поддержку удаленных пользователей. Возможна также поддержка федеративных пользователей, включая пользователей конкретных поставщиков общедоступных услуг связи для обмена мгновенными сообщениями (например, Windows Live), и поддержка анонимных пользователей.</span><span class="sxs-lookup"><span data-stu-id="72a18-p102">Each Front End pool can have only one Edge Server or Edge pool associated with it. When you enable external user access for a site, you can provide support for remote users. You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>

<span data-ttu-id="72a18-p103">Со всеми пулами на сайте, а также с пулами на нескольких центральных сайтах, может применяться один и тот же пограничный сервер достаточной производительности. О наблюдении, включая масштабирование, см. в разделе [Planning for External User Access](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx) руководства по развертыванию. О разработке топологии для поддержки доступа внешних пользователей см. в разделе [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) руководства по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="72a18-p103">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server. For details about monitoring, including scaling, see [Planning for External User Access](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx) in the Planning documentation. For details about designing a topology to support external user access, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Deployment documentation.</span></span>


