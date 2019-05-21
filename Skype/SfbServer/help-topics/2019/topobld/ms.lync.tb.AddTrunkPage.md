---
title: Определение новой линии связи
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
ROBOTS: NOINDEX, NOFOLLOW
description: 'Вы определяете новую магистральный протокол SIP, предоставляя следующие сведения:'
ms.openlocfilehash: c6586f9da069c3a3fc149b086562592db113b31e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34282482"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="aeeb9-103">Определение новой линии связи</span><span class="sxs-lookup"><span data-stu-id="aeeb9-103">Define a New Trunk</span></span>

<span data-ttu-id="aeeb9-104">Вы определяете новую магистральный протокол SIP, предоставляя следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="aeeb9-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="aeeb9-105">**Имя канала**связи: уникальное имя в топологии, которое будет определять эту магистраль.</span><span class="sxs-lookup"><span data-stu-id="aeeb9-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="aeeb9-106">**Связанный шлюз PSTN**: Выберите развернутый и сконфигурированный шлюз PSTN в развертывании из списка.</span><span class="sxs-lookup"><span data-stu-id="aeeb9-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="aeeb9-107">**Порт для прослушивания шлюза IP/КТСОП**: порт, прослушиваемый IP-УАТС или PSTN-шлюзом.</span><span class="sxs-lookup"><span data-stu-id="aeeb9-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="aeeb9-108">Должны быть уникальными на всех остальных портах, настроенных в развертывании</span><span class="sxs-lookup"><span data-stu-id="aeeb9-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="aeeb9-109">**Транспортный протокол SIP**: выберите из списка один из протоколов TCP или TLS.</span><span class="sxs-lookup"><span data-stu-id="aeeb9-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="aeeb9-110">**Сервер связанных исправлений**: выберите из списка сервер-посредник, развернутый и настроенный в развертывании</span><span class="sxs-lookup"><span data-stu-id="aeeb9-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="aeeb9-111">**Порт сервера связанных исправлений**: установите для порта значение, равное значению порта TCP или TLS сервера, который будет использоваться этой магистральной службой SIP.</span><span class="sxs-lookup"><span data-stu-id="aeeb9-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="aeeb9-112">См. также</span><span class="sxs-lookup"><span data-stu-id="aeeb9-112">See also</span></span>

[<span data-ttu-id="aeeb9-113">М:Н магистраль в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="aeeb9-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="aeeb9-114">Как реализовать магистральные линии SIP?</span><span class="sxs-lookup"><span data-stu-id="aeeb9-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
