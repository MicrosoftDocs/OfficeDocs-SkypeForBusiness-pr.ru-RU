---
title: Добавление параметров пограничных серверов для Lync Server 2010
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
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: Вы определяете новый пограничный сервер или пограничный пул и обладаете возможностью определять компоненты для нового сервера или пула. Доступные для выбора параметры приведены ниже.
ms.openlocfilehash: 273b2543fc3eea1373817ab38eab39379ec59132
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48216600"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="40535-104">Добавление параметров пограничных серверов для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="40535-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="40535-105">Вы определяете новый пограничный сервер или пограничный пул и обладаете возможностью определять компоненты для нового сервера или пула.</span><span class="sxs-lookup"><span data-stu-id="40535-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="40535-106">Доступные для выбора параметры приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="40535-106">The options that you can choose are:</span></span>

- <span data-ttu-id="40535-107">**Использовать единое полное доменное имя и IP-адрес**. Установите этот флажок, чтобы использовать один адрес IPv4 или IPv6 (если выбрано использование и IPv4, и IPv6, то необходимо определить каждый из этих типов адресов) и одно полное доменное имя для внешних интерфейсов пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="40535-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="40535-108">Если выбрать этот параметр, будет использован только один IP-адрес (или один адрес IPv4 и один адрес IPv6), однако необходимо назначить разные порты для каждого интерфейса пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="40535-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="40535-109">**Включить федерацию (порт 5061)**. Установите этот флажок, если необходимо установить федерацию с другими федерациями, поставщиками или узлами SIP.</span><span class="sxs-lookup"><span data-stu-id="40535-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="40535-110">**Внешний IP-адрес пограничного пула транслируется NAT**: Установите этот флажок, если вы используете частные IP-адреса для пограничных внешних интерфейсов и предложит устройство преобразования сетевых адресов (NAT) для пограничного логического сервера или пограничного пула.</span><span class="sxs-lookup"><span data-stu-id="40535-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="40535-111">См. также</span><span class="sxs-lookup"><span data-stu-id="40535-111">See also</span></span>

[<span data-ttu-id="40535-112">Планирование доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="40535-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="40535-113">Развертывание доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="40535-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
