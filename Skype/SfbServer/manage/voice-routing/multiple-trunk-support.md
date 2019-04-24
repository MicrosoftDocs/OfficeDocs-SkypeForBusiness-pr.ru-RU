---
title: Поддержка нескольких каналов в Скайп для Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Скайп для функции Business Server поддерживает несколько связей между шлюзы и серверы-посредники. Такие связи вносимые определение линии связи, который является логической связи между пула серверов-посредников и шлюза телефонной сети (общего пользования PSTN), пограничный контроллер сеансов (SBC) или IP-УАТС. Используйте построитель топологий для сопоставления шлюзы с серверов-посредников (то есть, магистральных линий связи).
ms.openlocfilehash: 5d093bee56597474f0cefcf1053536774f2eb795
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32214646"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="7c680-105">Поддержка нескольких каналов в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="7c680-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="7c680-106">Скайп для функции Business Server поддерживает несколько связей между шлюзы и серверы-посредники.</span><span class="sxs-lookup"><span data-stu-id="7c680-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="7c680-107">Такие связи вносимые определение линии связи, который является логической связи между пула серверов-посредников и шлюза телефонной сети (общего пользования PSTN), пограничный контроллер сеансов (SBC) или IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="7c680-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="7c680-108">Используйте построитель топологий для сопоставления шлюзы с серверов-посредников (то есть, магистральных линий связи).</span><span class="sxs-lookup"><span data-stu-id="7c680-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="7c680-109">Назначение или удаление магистрали в Скайп для Business Server, необходимо сначала определить магистрали в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="7c680-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="7c680-110">Магистраль состоит из следующих связь: сервер-посредник полное доменное имя (FQDN), порт прослушивания сервера-посредника, шлюз полное доменное имя и порт прослушивания шлюза.</span><span class="sxs-lookup"><span data-stu-id="7c680-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="7c680-111">Чтобы настроить несколько магистралей, можно создать несколько связей между же шлюза и сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="7c680-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="7c680-112">Это обеспечивает улучшения устойчивости инфраструктурой корпоративной голосовой связи, который особенно полезен в сценариях interoperational относиться УАТС.</span><span class="sxs-lookup"><span data-stu-id="7c680-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="7c680-113">When a trunk is defined, it must be associated to a route.</span><span class="sxs-lookup"><span data-stu-id="7c680-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="7c680-114">Чтобы связать магистралей с маршрутом, определение простое имя для магистрали в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="7c680-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="7c680-115">Это простое имя используется как имя линии связи в Скайп для панели управления Business Server, где можно сопоставить с маршрутов магистральных линий связи.</span><span class="sxs-lookup"><span data-stu-id="7c680-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="7c680-116">Имя канала связи простых используется как имя шлюза из Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="7c680-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="7c680-117">Администратор должен выбрать линии связи по умолчанию, связанные с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="7c680-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="7c680-118">В построителе топологии щелкните правой кнопкой мыши связанный сервер-посредник и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="7c680-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="7c680-119">Укажите шлюз по умолчанию для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="7c680-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="7c680-120">На следующем рисунке показано несколько магистралей, определенных для каждого сервера-посредника и шлюза.</span><span class="sxs-lookup"><span data-stu-id="7c680-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![Несколько назначений магистрали](../../media/multiple-trunk-assignments.jpg)
