---
title: Определение новой линии связи
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Определите новый сеанс initiation protocol (SIP) магистрали содержат следующие сведения:'
ms.openlocfilehash: 6f7dd7d8ab3aaa86eef78a5973194012e2e3b32c
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/20/2018
ms.locfileid: "19978057"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="26cf2-103">Определение новой линии связи</span><span class="sxs-lookup"><span data-stu-id="26cf2-103">Define a New Trunk</span></span>
 
<span data-ttu-id="26cf2-104">Определите новый сеанс initiation protocol (SIP) магистрали содержат следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="26cf2-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>
  
- <span data-ttu-id="26cf2-105">**Имя линии связи**: уникальным именем в топологии, идентифицирующее этот магистрали</span><span class="sxs-lookup"><span data-stu-id="26cf2-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>
    
- <span data-ttu-id="26cf2-106">**Связанный шлюз ТСОП**: выберите развертывания и настройки шлюза ТСОП в вашем развертывании из списка</span><span class="sxs-lookup"><span data-stu-id="26cf2-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>
    
- <span data-ttu-id="26cf2-107">**Порт прослушивания для шлюза IP/ТСОП**: порт, который прослушивает шлюз ТСОП или IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="26cf2-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="26cf2-108">Должно отличаться от всех других магистрали портов, прослушиваемых настроенных в развертывании</span><span class="sxs-lookup"><span data-stu-id="26cf2-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>
    
- <span data-ttu-id="26cf2-109">**Транспортный протокол SIP**: выберите в списке TCP или TLS</span><span class="sxs-lookup"><span data-stu-id="26cf2-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>
    
- <span data-ttu-id="26cf2-110">**Связанный сервер-посредник**: выберите из списка, который будет развернута и настроена в развертывании сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="26cf2-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>
    
- <span data-ttu-id="26cf2-111">**Порт связанного сервера-посредника**: укажите номер порта TCP или TLS значение порта сервера-посредника, которую будет использовать этот канала SIP.</span><span class="sxs-lookup"><span data-stu-id="26cf2-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span> 
    
## <a name="see-also"></a><span data-ttu-id="26cf2-112">См. также</span><span class="sxs-lookup"><span data-stu-id="26cf2-112">See also</span></span>

[<span data-ttu-id="26cf2-113">Магистраль m: n в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="26cf2-113">M:N trunk in Skype for Business Server</span></span>](../../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="26cf2-114">Как реализовать распределения каналов SIP?</span><span class="sxs-lookup"><span data-stu-id="26cf2-114">How do I implement SIP trunking?</span></span>](http://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)