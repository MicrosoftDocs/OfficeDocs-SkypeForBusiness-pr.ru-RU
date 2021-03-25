---
title: Добавление параметров пограничных серверов для Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Вы определяете новый пул Edge Server или Edge и имеете возможность определить возможности для нового сервера или пула. Доступные для выбора параметры приведены ниже.
ms.openlocfilehash: dfc8238bbbe4899f9819118a11fc11ba47fe21f3
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119808"
---
# <a name="add-edge-server-options-for-lync-server-2010"></a><span data-ttu-id="0e6de-104">Добавление параметров пограничных серверов для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="0e6de-104">Add Edge Server Options for Lync Server 2010</span></span>

<span data-ttu-id="0e6de-105">Вы определяете новый пул Edge Server или Edge и имеете возможность определить возможности для нового сервера или пула.</span><span class="sxs-lookup"><span data-stu-id="0e6de-105">You define a new Edge Server or Edge pool and are presented with the opportunity to define features for the new server or pool.</span></span> <span data-ttu-id="0e6de-106">Доступные для выбора параметры приведены ниже.</span><span class="sxs-lookup"><span data-stu-id="0e6de-106">The options that you can choose are:</span></span>

- <span data-ttu-id="0e6de-107">**Использовать единое полное доменное имя и IP-адрес**. Установите этот флажок, чтобы использовать один адрес IPv4 или IPv6 (если выбрано использование и IPv4, и IPv6, то необходимо определить каждый из этих типов адресов) и одно полное доменное имя для внешних интерфейсов пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="0e6de-107">**Use a single FQDN and IP address**: Select the check box to use a single IPv4 or IPv6 (if you choose to use both IPv4 and IPv6, then you will need to define one of each IP address type) address and fully qualified domain name (FQDN) for the external Edge interfaces.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="0e6de-108">Если выбрать этот параметр, будет использован только один IP-адрес (или один адрес IPv4 и один адрес IPv6), однако необходимо назначить разные порты для каждого интерфейса пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="0e6de-108">If you choose this option, you will use only one IP address, or one IPv4 and one IPv6, but you must assign different port numbers to each Edge interface.</span></span>

- <span data-ttu-id="0e6de-109">**Включить федерацию (порт 5061)**. Установите этот флажок, если необходимо установить федерацию с другими федерациями, поставщиками или узлами SIP.</span><span class="sxs-lookup"><span data-stu-id="0e6de-109">**Enable federation (port 5061)**: Select this check box if you will federate with other SIP federations, providers, or hosted offerings that use the session initiation protocol (SIP).</span></span>

- <span data-ttu-id="0e6de-110">Внешний IP-адрес этого пула **Edge** переведен nat : Выберите этот контрольный ящик, если вы используете частные IP-адреса для внешних интерфейсов Edge и предоставит устройство для перевода сетевых адресов (NAT), чтобы логически разместить пул Edge Server или Edge.</span><span class="sxs-lookup"><span data-stu-id="0e6de-110">**The external IP address of this Edge pool is translated by NAT**: Select this check box if you use private IP addresses for the Edge external interfaces and will provide a network address translation (NAT) device to place the Edge Server or Edge pool logically behind.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e6de-111">См. также</span><span class="sxs-lookup"><span data-stu-id="0e6de-111">See also</span></span>

[<span data-ttu-id="0e6de-112">Планирование доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="0e6de-112">Planning for External User Access</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access)

[<span data-ttu-id="0e6de-113">Развертывание доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="0e6de-113">Deploying External User Access</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-external-user-access)