---
title: Определение новой линии связи
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Вы определяете новую магистральный протокол SIP, предоставляя следующие сведения:'
ms.openlocfilehash: e6036942423e7d4f88050fead56e2a1336530cab
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41689048"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="e3a0d-103">Определение новой линии связи</span><span class="sxs-lookup"><span data-stu-id="e3a0d-103">Define a New Trunk</span></span>

<span data-ttu-id="e3a0d-104">Вы определяете новую магистральный протокол SIP, предоставляя следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="e3a0d-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="e3a0d-105">**Имя канала**связи: уникальное имя в топологии, которое будет определять эту магистраль.</span><span class="sxs-lookup"><span data-stu-id="e3a0d-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="e3a0d-106">**Связанный шлюз PSTN**: Выберите развернутый и сконфигурированный шлюз PSTN в развертывании из списка.</span><span class="sxs-lookup"><span data-stu-id="e3a0d-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="e3a0d-107">**Порт для прослушивания шлюза IP/КТСОП**: порт, прослушиваемый IP-УАТС или PSTN-шлюзом.</span><span class="sxs-lookup"><span data-stu-id="e3a0d-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="e3a0d-108">Должны быть уникальными на всех остальных портах, настроенных в развертывании</span><span class="sxs-lookup"><span data-stu-id="e3a0d-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="e3a0d-109">**Транспортный протокол SIP**: выберите из списка один из протоколов TCP или TLS.</span><span class="sxs-lookup"><span data-stu-id="e3a0d-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="e3a0d-110">**Сервер связанных исправлений**: выберите из списка сервер-посредник, развернутый и настроенный в развертывании</span><span class="sxs-lookup"><span data-stu-id="e3a0d-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="e3a0d-111">**Порт сервера связанных исправлений**: установите для порта значение, равное значению порта TCP или TLS сервера, который будет использоваться этой магистральной службой SIP.</span><span class="sxs-lookup"><span data-stu-id="e3a0d-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="e3a0d-112">См. также</span><span class="sxs-lookup"><span data-stu-id="e3a0d-112">See also</span></span>

[<span data-ttu-id="e3a0d-113">М:Н магистраль в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e3a0d-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="e3a0d-114">Как реализовать магистральные линии SIP?</span><span class="sxs-lookup"><span data-stu-id="e3a0d-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
