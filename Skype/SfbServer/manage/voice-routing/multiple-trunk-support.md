---
title: Поддержка нескольких магистральных магистральных магистрали в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Функциональность Skype для бизнеса Server поддерживает несколько ассоциаций между шлюзами и серверами-посредниками. Эти связи определяются путем определения магистрали, которая является логической связью между пулом серверов-посредников и шлюзом STN, пограничным контроллером сеансов (SBC) или IP-PBX. Используйте построитель топологий для связываия шлюзов с серверами-посредниками (то есть магистрали).
ms.openlocfilehash: 0f4c8d2ee16c900ef666c12230964a9abb8f5a48
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826229"
---
# <a name="multiple-trunk-support-in-skype-for-business-server"></a><span data-ttu-id="94d06-105">Поддержка нескольких магистральных магистральных магистрали в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="94d06-105">Multiple trunk support in Skype for Business Server</span></span>

<span data-ttu-id="94d06-106">Функциональность Skype для бизнеса Server поддерживает несколько ассоциаций между шлюзами и серверами-посредниками.</span><span class="sxs-lookup"><span data-stu-id="94d06-106">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="94d06-107">Эти связи определяются путем определения магистрали, которая является логической связью между пулом серверов-посредников и шлюзом STN, пограничным контроллером сеансов (SBC) или IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="94d06-107">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="94d06-108">Используйте построитель топологий для связываия шлюзов с серверами-посредниками (то есть магистрали).</span><span class="sxs-lookup"><span data-stu-id="94d06-108">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>

- <span data-ttu-id="94d06-109">Чтобы назначить или удалить магистраль в Skype для бизнеса Server, необходимо сначала определить магистраль в построите топологий.</span><span class="sxs-lookup"><span data-stu-id="94d06-109">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="94d06-110">Магистраль состоит из следующей связи: полное доменное имя сервера-посредника, прослушивает порт сервера-посредника, полное доменное имя шлюза и прослушивает порт шлюза.</span><span class="sxs-lookup"><span data-stu-id="94d06-110">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
- <span data-ttu-id="94d06-111">Чтобы настроить несколько магистральных магистральных магистрали, можно создать несколько ассоциаций между шлюзом и сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="94d06-111">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="94d06-112">Это обеспечивает дополнительную устойчивость инфраструктуры Корпоративная голосовая связь, что особенно полезно в сценариях межсервального обмена УАОП.</span><span class="sxs-lookup"><span data-stu-id="94d06-112">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 

<span data-ttu-id="94d06-113">После определения магистрали ее необходимо связать с маршрутом.</span><span class="sxs-lookup"><span data-stu-id="94d06-113">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="94d06-114">Чтобы связать магистраль с маршрутом, необходимо определить простое имя магистрали в построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="94d06-114">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="94d06-115">Это простое имя используется в качестве имени магистрали в панели управления Skype для бизнеса Server, где магистрали могут быть связаны с маршрутами.</span><span class="sxs-lookup"><span data-stu-id="94d06-115">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="94d06-116">Простое имя магистрали используется в качестве имени шлюза в оболочке управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="94d06-116">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span>

`New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}`

<span data-ttu-id="94d06-117">Администратор должен выбрать магистраль по умолчанию, связанную с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="94d06-117">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="94d06-118">В построитель топологий щелкните правой кнопкой мыши связанный сервер-посредник и выберите **"Свойства".**</span><span class="sxs-lookup"><span data-stu-id="94d06-118">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="94d06-119">Укажите шлюз по умолчанию для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="94d06-119">Specify the default gateway for the Mediation Server.</span></span> 

<span data-ttu-id="94d06-120">На следующей схеме показано несколько магистральных магистрали, определенных для каждого сервера-посредника и шлюза.</span><span class="sxs-lookup"><span data-stu-id="94d06-120">The following diagram illustrates the multiple trunks that are defined for each Mediation Server and gateway.</span></span> 

![Несколько назначений магистрали](../../media/multiple-trunk-assignments.jpg)
