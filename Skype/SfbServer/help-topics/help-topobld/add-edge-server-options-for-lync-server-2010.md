---
title: Добавление параметров пограничных серверов для Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Вы определяете новый сервер пограничного или пограничного пула и обладаете возможностью определять возможности для нового сервера или пула. Вы можете выбрать один из следующих вариантов:'
ms.openlocfilehash: 4bb364ee24f2e85ec16ff2f972dfe05aea9306cd
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289996"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="a50bb-104">Добавление параметров пограничных серверов для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="a50bb-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="a50bb-105">Вы определяете новый сервер пограничного или пограничного пула и обладаете возможностью определять возможности для нового сервера или пула.</span><span class="sxs-lookup"><span data-stu-id="a50bb-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="a50bb-106">Вы можете выбрать один из следующих вариантов:</span><span class="sxs-lookup"><span data-stu-id="a50bb-106">The options that you can choose are:</span></span>

- <span data-ttu-id="a50bb-107">**Использование одного полного доменного имени и IP-адреса**: установите флажок, чтобы использовать один адрес IPv4 или IPv6 (если вы хотите использовать IPv4 и IPv6, вам потребуется задать один из адресов типа IP-адреса) и полное доменное имя (FQDN) для внешних интерфейсов Edge.</span><span class="sxs-lookup"><span data-stu-id="a50bb-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="a50bb-108">Если выбрать этот параметр, вы будете использовать только один IP-адрес или один и тот же IPv4 и один IPv6, но каждому интерфейсу пограничного сервера должны быть назначены разные номера портов.</span><span class="sxs-lookup"><span data-stu-id="a50bb-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="a50bb-109">**Включить федерацию (порт 5061)**: Установите этот флажок, если вы включаете в Федерацию другие Федерации SIP, поставщики или размещенные предложения, ИСПОЛЬЗУЮЩИЕ протокол SIP.</span><span class="sxs-lookup"><span data-stu-id="a50bb-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="a50bb-110">**Внешний IP-адрес этого пограничного пула преобразуется NAT**: Установите этот флажок, если вы используете частные IP-адреса для внешних интерфейсов EDGE и предоставите устройство преобразования сетевых адресов (NAT) для логического размещения пограничного сервера или пула Edge. плане.</span><span class="sxs-lookup"><span data-stu-id="a50bb-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="a50bb-111">См. также</span><span class="sxs-lookup"><span data-stu-id="a50bb-111">See also</span></span>

[<span data-ttu-id="a50bb-112">Планирование доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="a50bb-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="a50bb-113">Развертывание внешнего доступа пользователей</span><span class="sxs-lookup"><span data-stu-id="a50bb-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
