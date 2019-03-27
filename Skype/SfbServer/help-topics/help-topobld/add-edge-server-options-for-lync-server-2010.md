---
title: Добавление параметров пограничных серверов для Lync Server 2010
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddEdgeServerOptionsPage2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b059af5-e83f-4564-90b2-d7ebb9e551c2
description: 'Определите новый пограничный сервер или пограничный пул и предоставляется возможность определения компонентов для нового сервера или пула. Параметры, которые можно выбрать, являются:'
ms.openlocfilehash: 57c3916b1a43812c1f647f425fc9df65f99cff35
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897460"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="61c39-104">Добавление параметров пограничных серверов для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="61c39-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="61c39-105">Определите новый пограничный сервер или пограничный пул и предоставляется возможность определения компонентов для нового сервера или пула.</span><span class="sxs-lookup"><span data-stu-id="61c39-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="61c39-106">Параметры, которые можно выбрать, являются:</span><span class="sxs-lookup"><span data-stu-id="61c39-106">The options that you can choose are:</span></span>

- <span data-ttu-id="61c39-107">**Используйте один полное доменное имя и IP-адрес**: установите флажок для использования в одном IPv4 или IPv6 (Если выбрано использование IPv4 и IPv6, необходимо определить один из каждого типа адреса IP-адрес) адрес и полное доменное имя (FQDN) для внешних пограничных интерфейсов.</span><span class="sxs-lookup"><span data-stu-id="61c39-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="61c39-108">Если выбран этот параметр, будет использоваться только один IP-адрес, или один адрес IPv4 и один адрес IPv6, но необходимо назначить разные порты для каждого интерфейса пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="61c39-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="61c39-109">**Включение федерации (порт 5061)**: Установите этот флажок, если будет создать федерацию с другими федерации SIP, поставщиков или размещенной и услуги, использующих протокол (SIP).</span><span class="sxs-lookup"><span data-stu-id="61c39-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="61c39-110">**Внешний IP-адрес этого пограничного пула преобразовываются NAT**: Установите этот флажок, если использовать частные IP-адреса для внешних пограничных интерфейсов и предоставляющие устройства преобразования Сетевых адресов адрес сети установите пограничный сервер или пограничный пул логически назад.</span><span class="sxs-lookup"><span data-stu-id="61c39-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="61c39-111">См. также</span><span class="sxs-lookup"><span data-stu-id="61c39-111">See also</span></span>

[<span data-ttu-id="61c39-112">Планирование доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="61c39-112">Planning for External User Access</span></span>](https://technet.microsoft.com/library/ea098933-eff5-461e-aba3-e7f128784dc2.aspx)

[<span data-ttu-id="61c39-113">Развертывание доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="61c39-113">Deploying External User Access</span></span>](https://technet.microsoft.com/library/d40c9574-c16b-4fe6-b848-21ae0b7e4f0e.aspx)
