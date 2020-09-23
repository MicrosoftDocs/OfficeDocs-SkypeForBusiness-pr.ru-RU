---
title: Определение корневой магистральной линии для нового шлюза IP или ТСОП
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
- ms.lync.tb.AddPstnGatewayTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22203d9a-4612-45c7-9375-69ae9964ce1e
description: 'Корневую магистраль для IP-телефонии или ТСОП можно определить, настроив следующие параметры:'
ms.openlocfilehash: 3789024ce5099645eca7c14576b586bc1c349683
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219080"
---
# <a name="define-the-root-trunk-for-a-new-ip-or-pstn-gateway"></a><span data-ttu-id="f7a80-103">Определение корневой магистральной линии для нового шлюза IP или ТСОП</span><span class="sxs-lookup"><span data-stu-id="f7a80-103">Define the Root Trunk for a New IP or PSTN Gateway</span></span>

<span data-ttu-id="f7a80-104">Корневую магистраль для IP-телефонии или ТСОП можно определить, настроив следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="f7a80-104">You define the root trunk for the IP or public switched telephone network (PSTN) by configuring the following:</span></span>

- <span data-ttu-id="f7a80-105">**Имя линии связи** — определяет полное доменное имя, связанное с магистралью;</span><span class="sxs-lookup"><span data-stu-id="f7a80-105">**Trunk name**: define the fully qualified domain name associated with the trunk</span></span>

- <span data-ttu-id="f7a80-106">**Порт прослушивания для IP-адреса/шлюза ТСОП** — определяет порт, по которому выполняется прослушивание для данной магистрали</span><span class="sxs-lookup"><span data-stu-id="f7a80-106">**Listening port for IP/PSTN gateway**: define the port that this trunk will listen on</span></span>

- <span data-ttu-id="f7a80-107">**Транспортный протокол SIP** — выберите в списке **TCP** или **TLS** в зависимости от потребностей магистрали</span><span class="sxs-lookup"><span data-stu-id="f7a80-107">**SIP Transport Protocol**: select from the list either **TCP** or **TLS**, based on the trunk requirements</span></span>

- <span data-ttu-id="f7a80-108">**Связанный сервер-посредник**: выберите из списка доступных серверов-посредников в развертывании.</span><span class="sxs-lookup"><span data-stu-id="f7a80-108">**Associated Mediation Server**: select from the list of available Mediation Servers in your deployment</span></span>

- <span data-ttu-id="f7a80-109">**Связанный порт сервера-посредника**: определение порта, прослушиваемого выбранным сервером-посредником</span><span class="sxs-lookup"><span data-stu-id="f7a80-109">**Associated Mediation Server port**: define the port that the selected Mediation Server is listening on</span></span>

## <a name="see-also"></a><span data-ttu-id="f7a80-110">См. также</span><span class="sxs-lookup"><span data-stu-id="f7a80-110">See also</span></span>

[<span data-ttu-id="f7a80-111">Настройка магистрали с обходом сервера-посредника в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="f7a80-111">Configure a trunk with media bypass in Skype for Business Server 2015</span></span>](../../deploy/deploy-enterprise-voice/configure-trunk-with-media-bypass.md)

[<span data-ttu-id="f7a80-112">Настройка магистрали без обхода сервера-посредника в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="f7a80-112">Configure a trunk without media bypass in Skype for Business Server 2015</span></span>](../../deploy/deploy-enterprise-voice/configure-trunk-without-media-bypass.md)

[<span data-ttu-id="f7a80-113">Поддержка распределения каналов SIP</span><span class="sxs-lookup"><span data-stu-id="f7a80-113">SIP Trunking Support</span></span>](https://technet.microsoft.com/library/e3042831-e8d8-4ea2-baa2-1a697401ffa0.aspx)
