---
title: Определение корневой магистральной линии для нового шлюза IP или ТСОП
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddPstnGatewayTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22203d9a-4612-45c7-9375-69ae9964ce1e
ROBOTS: NOINDEX, NOFOLLOW
description: 'Корневую магистраль для IP-телефонии или ТСОП можно определить, настроив следующие параметры:'
ms.openlocfilehash: 183787e78fee0fa827bd3cc554fb7d43188014d2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51116417"
---
# <a name="define-the-root-trunk-for-a-new-ip-or-pstn-gateway"></a><span data-ttu-id="ab59b-103">Определение корневой магистральной линии для нового шлюза IP или ТСОП</span><span class="sxs-lookup"><span data-stu-id="ab59b-103">Define the Root Trunk for a New IP or PSTN Gateway</span></span>

<span data-ttu-id="ab59b-104">Корневую магистраль для IP-телефонии или ТСОП можно определить, настроив следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="ab59b-104">You define the root trunk for the IP or public switched telephone network (PSTN) by configuring the following:</span></span>

- <span data-ttu-id="ab59b-105">**Имя линии связи** — определяет полное доменное имя, связанное с магистралью;</span><span class="sxs-lookup"><span data-stu-id="ab59b-105">**Trunk name**: define the fully qualified domain name associated with the trunk</span></span>

- <span data-ttu-id="ab59b-106">**Порт прослушивания для IP-адреса/шлюза ТСОП** — определяет порт, по которому выполняется прослушивание для данной магистрали</span><span class="sxs-lookup"><span data-stu-id="ab59b-106">**Listening port for IP/PSTN gateway**: define the port that this trunk will listen on</span></span>

- <span data-ttu-id="ab59b-107">**Транспортный протокол SIP** — выберите в списке **TCP** или **TLS** в зависимости от потребностей магистрали</span><span class="sxs-lookup"><span data-stu-id="ab59b-107">**SIP Transport Protocol**: select from the list either **TCP** or **TLS**, based on the trunk requirements</span></span>

- <span data-ttu-id="ab59b-108">**Связанный сервер-посредник:** выберите из списка доступных серверов-посредников в развертывании</span><span class="sxs-lookup"><span data-stu-id="ab59b-108">**Associated Mediation Server**: select from the list of available Mediation Servers in your deployment</span></span>

- <span data-ttu-id="ab59b-109">**Связанный порт сервера-посредника:** определите порт, на который прослушивается выбранный сервер-посредник</span><span class="sxs-lookup"><span data-stu-id="ab59b-109">**Associated Mediation Server port**: define the port that the selected Mediation Server is listening on</span></span>

## <a name="see-also"></a><span data-ttu-id="ab59b-110">См. также</span><span class="sxs-lookup"><span data-stu-id="ab59b-110">See also</span></span>

[<span data-ttu-id="ab59b-111">Настройка магистрали с обходом мультимедиа в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ab59b-111">Configure a trunk with media bypass in Skype for Business Server</span></span>](../../../deploy/deploy-enterprise-voice/configure-trunk-with-media-bypass.md)

[<span data-ttu-id="ab59b-112">Настройка магистрали без обхода мультимедиа в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="ab59b-112">Configure a trunk without media bypass in Skype for Business Server</span></span>](../../../deploy/deploy-enterprise-voice/configure-trunk-without-media-bypass.md)

[<span data-ttu-id="ab59b-113">Поддержка распределения каналов SIP</span><span class="sxs-lookup"><span data-stu-id="ab59b-113">SIP Trunking Support</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-sip-trunking-support)