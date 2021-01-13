---
title: Определение новой линии связи
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
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: Вы можете определить новый канал связи по протоколу SIP, указав следующие сведения.
ms.openlocfilehash: bbed07920bdeddb78217e435e8813c89231cdcc9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833049"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="56af4-103">Определение новой линии связи</span><span class="sxs-lookup"><span data-stu-id="56af4-103">Define a New Trunk</span></span>

<span data-ttu-id="56af4-104">Вы можете определить новый канал связи по протоколу SIP, указав следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="56af4-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="56af4-105">**Имя канала связи**. Уникальное имя в топологии, используемое для идентификации данного канала связи.</span><span class="sxs-lookup"><span data-stu-id="56af4-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="56af4-106">**Связанный шлюз ТСОП**. Выберите развернутый и настроенный шлюз ТСОП в списке.</span><span class="sxs-lookup"><span data-stu-id="56af4-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="56af4-p101">**Порт прослушивания для шлюза IP/ТСОП**. Порт, который будет прослушиваться шлюзом IP-УАТС или ТСОП. Должен отличаться от всех остальных портов прослушивания каналов связи, настроенных в данном развертывании.</span><span class="sxs-lookup"><span data-stu-id="56af4-p101">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on. Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="56af4-109">**Транспортный протокол SIP**. Выберите в списке TCP или TLS.</span><span class="sxs-lookup"><span data-stu-id="56af4-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="56af4-110">**Связанный сервер-посредник**: выберите в списке сервер-посредник, развернутый и настроенный в развертывании</span><span class="sxs-lookup"><span data-stu-id="56af4-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="56af4-111">**Связанный порт сервера-посредника:** установите значение порта, равное порту TCP или TLS сервера-посредника, который будет использовать эта магистраль SIP</span><span class="sxs-lookup"><span data-stu-id="56af4-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="56af4-112">См. также</span><span class="sxs-lookup"><span data-stu-id="56af4-112">See also</span></span>

[<span data-ttu-id="56af4-113">Магистраль M:N в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="56af4-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="56af4-114">Как реализовать магистрали SIP?</span><span class="sxs-lookup"><span data-stu-id="56af4-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
