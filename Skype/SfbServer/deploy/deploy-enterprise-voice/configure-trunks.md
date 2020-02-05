---
title: Настройка каналов связи в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: 'Сводка: сведения о настройке магистрали между сервером-посредником и одноранговыми приложениями для корпоративной голосовой связи в Skype для бизнеса Server.'
ms.openlocfilehash: eb2cf3042fe4e0d1a7c840fb31c583b18289bb7b
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41768072"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="2c5bb-103">Настройка каналов связи в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="2c5bb-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="2c5bb-104">**Сводка:** Сведения о том, как настроить магистраль между сервером-посредником и одноранговыми приложениями для корпоративной голосовой связи в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="2c5bb-105">В рамках развертывания Enterprise Voice вы можете настроить магистраль между сервером-посредником и одним или несколькими из указанных ниже одноранговых сетей для предоставления подключения по коммутируемой телефонной сети (PSTN) для корпоративных клиентов и мобильных устройств в Организации.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="2c5bb-106">Подключение магистрали SIP к поставщику услуг Интернет-телефонии</span><span class="sxs-lookup"><span data-stu-id="2c5bb-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="2c5bb-107">Шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="2c5bb-107">PSTN gateway</span></span>
    
- <span data-ttu-id="2c5bb-108">УАТС</span><span class="sxs-lookup"><span data-stu-id="2c5bb-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="2c5bb-109">Дополнительные сведения можно найти [в разделе Планирование подключений PSTN в Skype для бизнеса Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="2c5bb-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="2c5bb-110">Функции Skype для бизнеса Server поддерживают несколько ассоциаций между шлюзами и серверами исправлений.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="2c5bb-111">Эти связи выполняются путем определения канала, который является логической связью между пулом серверов «исправление» и шлюзом коммутируемой телефонной сети (КТСОП), контроллером границ сеансов (SBC) или IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="2c5bb-112">С помощью построителя топологии свяжите шлюзы с серверами-посредниками (то есть магистральами).</span><span class="sxs-lookup"><span data-stu-id="2c5bb-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="2c5bb-113">Чтобы назначить или удалить магистраль в Skype для бизнеса Server, необходимо сначала определить магистраль в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="2c5bb-114">Магистраль состоит из следующей ассоциации: полное доменное имя (FQDN) сервера исходящих сообщений, а также имя шлюза и порт для прослушивания шлюза.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="2c5bb-115">Чтобы настроить несколько каналов связи, вы можете создать несколько ассоциаций между одним и тем же шлюзом и сервером обновлений.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="2c5bb-116">Это обеспечивает дополнительную устойчивость к корпоративной инфраструктуре голосовой связи, которая особенно полезна в сценариях взаимодействия между частными филиалами (АТС).</span><span class="sxs-lookup"><span data-stu-id="2c5bb-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="2c5bb-117">When a trunk is defined, it must be associated to a route.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="2c5bb-118">Чтобы связать магистраль с маршрутом, вы определяете простое имя для магистрали в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="2c5bb-119">Это простое имя используется в качестве наименования канала на панели управления "Skype для бизнеса" на сервере, где магистральные магистрали могут быть связаны с маршрутами.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="2c5bb-120">Простое имя канала используется как имя шлюза в командной консоли управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="2c5bb-121">Администратор должен выбрать магистраль по умолчанию, связанный с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="2c5bb-122">В построителе топологии щелкните правой кнопкой мыши соответствующий сервер-посредник и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="2c5bb-123">Укажите шлюз по умолчанию для сервера обновлений.</span><span class="sxs-lookup"><span data-stu-id="2c5bb-123">Specify the default gateway for the Mediation Server.</span></span> 
  

