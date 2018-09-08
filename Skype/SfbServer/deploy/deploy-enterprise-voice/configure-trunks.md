---
title: Настройка магистрали в Скайп для Business Server
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
description: ': Сводка Настройка линии связи между сервером-посредником и коллег для корпоративной голосовой связи в Скайп для Business Server.'
ms.openlocfilehash: 02ace749e62b7e6edd3f514fa81b55eb30c87094
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23887978"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="9634d-103">Настройка магистрали в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="9634d-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="9634d-104">**Сводка:** Сведения о настройке линии связи между сервером-посредником и коллег для корпоративной голосовой связи в Скайп для Business Server.</span><span class="sxs-lookup"><span data-stu-id="9634d-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="9634d-105">В процессе развертывания корпоративной голосовой связи можно настроить линии связи между сервером-посредником и один или несколько следующих партнеров для предоставления телефонной сети (общего пользования PSTN) для корпоративной голосовой связи клиентов и устройств в вашей организации:</span><span class="sxs-lookup"><span data-stu-id="9634d-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="9634d-106">Подключение магистрали SIP к поставщику услуг Интернет-телефонии</span><span class="sxs-lookup"><span data-stu-id="9634d-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="9634d-107">Шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="9634d-107">PSTN gateway</span></span>
    
- <span data-ttu-id="9634d-108">УАТС</span><span class="sxs-lookup"><span data-stu-id="9634d-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="9634d-109">Для получения дополнительных сведений см. [Планирование подключения к ТСОП в Скайп для Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span><span class="sxs-lookup"><span data-stu-id="9634d-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="9634d-110">Скайп для функции Business Server поддерживает несколько связей между шлюзы и серверы-посредники.</span><span class="sxs-lookup"><span data-stu-id="9634d-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="9634d-111">Такие связи вносимые определение линии связи, который является логической связи между пула серверов-посредников и шлюза телефонной сети (общего пользования PSTN), пограничный контроллер сеансов (SBC) или IP-УАТС.</span><span class="sxs-lookup"><span data-stu-id="9634d-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="9634d-112">Используйте построитель топологий для сопоставления шлюзы с серверов-посредников (то есть, магистральных линий связи).</span><span class="sxs-lookup"><span data-stu-id="9634d-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="9634d-113">Назначение или удаление магистрали в Скайп для Business Server, необходимо сначала определить магистрали в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="9634d-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="9634d-114">Магистраль состоит из следующих связь: сервер-посредник полное доменное имя (FQDN), порт прослушивания сервера-посредника, шлюз полное доменное имя и порт прослушивания шлюза.</span><span class="sxs-lookup"><span data-stu-id="9634d-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="9634d-115">Чтобы настроить несколько магистралей, можно создать несколько связей между же шлюза и сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="9634d-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="9634d-116">Это обеспечивает улучшения устойчивости инфраструктурой корпоративной голосовой связи, который особенно полезен в сценариях interoperational относиться УАТС.</span><span class="sxs-lookup"><span data-stu-id="9634d-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="9634d-117">При определении магистрали, должен быть связан с маршрутом.</span><span class="sxs-lookup"><span data-stu-id="9634d-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="9634d-118">Чтобы связать магистралей с маршрутом, определение простое имя для магистрали в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="9634d-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="9634d-119">Это простое имя используется как имя линии связи в Скайп для панели управления Business Server, где можно сопоставить с маршрутов магистральных линий связи.</span><span class="sxs-lookup"><span data-stu-id="9634d-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="9634d-120">Имя канала связи простых используется как имя шлюза из Скайп для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="9634d-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="9634d-121">Администратор должен выбрать линии связи по умолчанию, связанные с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="9634d-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="9634d-122">В построителе топологии щелкните правой кнопкой мыши связанный сервер-посредник и выберите пункт **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="9634d-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="9634d-123">Укажите шлюз по умолчанию для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="9634d-123">Specify the default gateway for the Mediation Server.</span></span> 
  

