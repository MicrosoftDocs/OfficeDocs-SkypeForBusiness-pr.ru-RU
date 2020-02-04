---
title: Добавление IP-адреса NAT пограничного сервера
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddEdgeServerNatIpPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: aa97fd0e-48b9-4a66-b55a-12291641c967
ROBOTS: NOINDEX, NOFOLLOW
description: Общедоступный IP-адрес — это IP-адрес, который используется для преобразования сетевых адресов (NAT). IP-адрес должен быть общедоступным для маршрутизации. Это необходимо, так как вы выбрали внешний IP-адрес этого пограничного пула преобразуются с помощью функции "NAT" на странице "Выбор компонентов" этого мастера.
ms.openlocfilehash: f06d9b61d5ffad29d24e143cf3afbbc4501a67d4
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689418"
---
# <a name="add-edge-server-nat-ip"></a><span data-ttu-id="c684e-105">Добавление IP-адреса NAT пограничного сервера</span><span class="sxs-lookup"><span data-stu-id="c684e-105">Add Edge Server NAT IP</span></span>

<span data-ttu-id="c684e-106">Общедоступный IP-адрес — это IP-адрес, который используется для преобразования сетевых адресов (NAT).</span><span class="sxs-lookup"><span data-stu-id="c684e-106">The public IP address is the IP address that is used by network address translation (NAT).</span></span> <span data-ttu-id="c684e-107">IP-адрес должен быть общедоступным для маршрутизации.</span><span class="sxs-lookup"><span data-stu-id="c684e-107">The IP address must be publicly routable.</span></span> <span data-ttu-id="c684e-108">Это необходимо, так как вы выбрали **внешний IP-адрес этого пограничного пула преобразуются с помощью** функции "NAT" на странице " **Выбор компонентов** " этого мастера.</span><span class="sxs-lookup"><span data-stu-id="c684e-108">This is required because you selected **The external IP address of this Edge pool is translated by NAT** option on the **Select features** page of this wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="c684e-109">Преобразование сетевых адресов (NAT) позволяет клиентам и серверам в частной сети (например, в диапазоне 192.168.0.0) взаимодействовать с системами в удаленных сетях через общедоступные Интернет-сети.</span><span class="sxs-lookup"><span data-stu-id="c684e-109">Network address translation (NAT) enables clients or servers on a private network (for example, the 192.168.0.0 range) to communicate with systems on remote networks over the public Internet networks.</span></span> <span data-ttu-id="c684e-110">NAT работает с использованием единого общего IP-адреса во внешнем интерфейсе и связывания внутренних IP-адресов с одним общедоступным IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="c684e-110">NAT works by using a single public IP address on an external interface and associating internal IP addresses with the one public IP address.</span></span> <span data-ttu-id="c684e-111">В сопоставлении NAT внутренний адрес сопоставляется с внешним общедоступным IP-адресом.</span><span class="sxs-lookup"><span data-stu-id="c684e-111">NAT mapping maps an internal address to the external public IP address.</span></span> <span data-ttu-id="c684e-112">Удаленная система видит только общедоступный адрес источника.</span><span class="sxs-lookup"><span data-stu-id="c684e-112">The remote system sees only the public address of the source.</span></span> <span data-ttu-id="c684e-113">Удаленная система реагирует на источник, а источник — на карту NAT, чтобы определить, на какой внутренний IP-адрес должен быть возвращен ответ.</span><span class="sxs-lookup"><span data-stu-id="c684e-113">The remote system responds to the source, and the source refers to the NAT map to determine what internal IP address the response should be returned to.</span></span>

<span data-ttu-id="c684e-p104">Поддержку внешнего доступа пользователей можно настроить при развертывании начальной топологии или позднее. Дополнительные сведения о добавлении пограничных серверов к существующей топологии см. в разделе [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) документации по развертыванию пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="c684e-p104">You can add support for external user access when you deploy your initial topology or afterward. For details about adding Edge Servers to an existing topology, see [Define Your Edge Topology](https://technet.microsoft.com/library/787b23f1-8fa0-4c37-abf2-c516c5dd66f0.aspx) in the Edge Server Deployment documentation.</span></span>


