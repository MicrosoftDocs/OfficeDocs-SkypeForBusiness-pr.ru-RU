---
title: Поддержка нескольких каналов в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Функции Skype для бизнеса Server поддерживают несколько ассоциаций между шлюзами и серверами исправлений. Эти связи выполняются путем определения канала, который является логической связью между пулом серверов «исправление» и шлюзом коммутируемой телефонной сети (КТСОП), контроллером границ сеансов (SBC) или IP-УАТС. С помощью построителя топологии свяжите шлюзы с серверами-посредниками (то есть магистральами).
ms.openlocfilehash: a6a0134ee04d939a10aaf9e36c81124d085af5aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34274914"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="92ce8-105">Поддержка нескольких каналов в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="92ce8-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="92ce8-106">Функции Skype для бизнеса Server поддерживают несколько ассоциаций между шлюзами и серверами исправлений.</span><span class="sxs-lookup"><span data-stu-id="92ce8-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="92ce8-107">Эти связи выполняются путем определения канала, который является логической связью между пулом серверов «исправление» и шлюзом коммутируемой телефонной сети (КТСОП), контроллером границ сеансов (SBC) или IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="92ce8-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="92ce8-108">С помощью построителя топологии свяжите шлюзы с серверами-посредниками (то есть магистральами).</span><span class="sxs-lookup"><span data-stu-id="92ce8-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="92ce8-109">Чтобы назначить или удалить магистраль в Skype для бизнеса Server, необходимо сначала определить магистраль в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="92ce8-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="92ce8-110">Магистраль состоит из следующей ассоциации: полное доменное имя (FQDN) сервера исходящих сообщений, а также имя шлюза и порт для прослушивания шлюза.</span><span class="sxs-lookup"><span data-stu-id="92ce8-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="92ce8-111">Чтобы настроить несколько каналов связи, вы можете создать несколько ассоциаций между одним и тем же шлюзом и сервером обновлений.</span><span class="sxs-lookup"><span data-stu-id="92ce8-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="92ce8-112">Это обеспечивает дополнительную устойчивость к корпоративной инфраструктуре голосовой связи, которая особенно полезна в сценариях взаимодействия между частными филиалами (АТС).</span><span class="sxs-lookup"><span data-stu-id="92ce8-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="92ce8-113">When a trunk is defined, it must be associated to a route.</span><span class="sxs-lookup"><span data-stu-id="92ce8-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="92ce8-114">Чтобы связать магистраль с маршрутом, вы определяете простое имя для магистрали в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="92ce8-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="92ce8-115">Это простое имя используется в качестве наименования канала на панели управления "Skype для бизнеса" на сервере, где магистральные магистрали могут быть связаны с маршрутами.</span><span class="sxs-lookup"><span data-stu-id="92ce8-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="92ce8-116">Простое имя канала используется как имя шлюза в командной консоли управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="92ce8-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="92ce8-117">Администратор должен выбрать магистраль по умолчанию, связанный с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="92ce8-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="92ce8-118">В построителе топологии щелкните правой кнопкой мыши соответствующий сервер-посредник и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="92ce8-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="92ce8-119">Укажите шлюз по умолчанию для сервера обновлений.</span><span class="sxs-lookup"><span data-stu-id="92ce8-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="92ce8-120">На следующей схеме показаны несколько магистральных каналов, определенных для каждого сервера и шлюза.</span><span class="sxs-lookup"><span data-stu-id="92ce8-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![Несколько назначений для магистрали](../../media/multiple-trunk-assignments.jpg)
