---
title: Настройка магистральных магистральных звонков в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Сводка. Узнайте, как настроить магистраль между сервером-посредником и одноранговых Корпоративная голосовая связь в Skype для бизнеса Server.
ms.openlocfilehash: f2e9f3a5e9fa9d89ef9db63aa82b6a3ce3a86c6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824959"
---
# <a name="configure-trunks-in-skype-for-business-server"></a><span data-ttu-id="671da-103">Настройка магистральных магистральных звонков в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="671da-103">Configure trunks in Skype for Business Server</span></span>
 
<span data-ttu-id="671da-104">**Сводка:** Узнайте, как настроить магистраль между сервером-посредником и одноранговой Корпоративная голосовая связь в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="671da-104">**Summary:** Learn how to configure a trunk between a Mediation Server and peers for Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="671da-105">В рамках развертывания Корпоративная голосовая связь можно настроить магистраль между сервером-посредником и одним или более из следующих одноранговых серверов, чтобы обеспечить подключение к STN для клиентов Корпоративная голосовая связь и устройств в организации:</span><span class="sxs-lookup"><span data-stu-id="671da-105">As part of Enterprise Voice deployment, you can configure a trunk between a Mediation Server and one or more of the following peers to provide public switched telephone network (PSTN) connectivity for Enterprise Voice clients and devices in your organization:</span></span>
  
- <span data-ttu-id="671da-106">Подключение магистрали SIP к поставщику услуг Интернет-телефонии</span><span class="sxs-lookup"><span data-stu-id="671da-106">SIP trunk connection to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="671da-107">Шлюз ТСОП</span><span class="sxs-lookup"><span data-stu-id="671da-107">PSTN gateway</span></span>
    
- <span data-ttu-id="671da-108">УАТС</span><span class="sxs-lookup"><span data-stu-id="671da-108">Private branch exchange (PBX)</span></span>
    
<span data-ttu-id="671da-109">Дополнительные сведения [см. в сведениях о планировании подключения к STN в Skype для бизнеса Server.](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md)</span><span class="sxs-lookup"><span data-stu-id="671da-109">For more details, see [Plan for PSTN connectivity in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/pstn-connectivity-0.md).</span></span>
  
<span data-ttu-id="671da-110">Функциональность Skype для бизнеса Server поддерживает несколько ассоциаций между шлюзами и серверами-посредниками.</span><span class="sxs-lookup"><span data-stu-id="671da-110">Skype for Business Server functionality supports multiple associations between gateways and Mediation Servers.</span></span> <span data-ttu-id="671da-111">Эти связи определяются путем определения магистрали, которая является логической связью между пулом серверов-посредников и шлюзом STN, пограничным контроллером сеансов (SBC) или IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="671da-111">These associations are made by defining a trunk, which is a logical association between a Mediation Server pool and a public switched telephone network (PSTN) gateway, Session Border Controller (SBC), or IP-PBX.</span></span> <span data-ttu-id="671da-112">Используйте построитель топологий для связываия шлюзов с серверами-посредниками (магистрали).</span><span class="sxs-lookup"><span data-stu-id="671da-112">Use the Topology Builder to associate gateways with Mediation Servers (that is, trunks).</span></span>
  
- <span data-ttu-id="671da-113">Чтобы назначить или удалить магистраль в Skype для бизнеса Server, необходимо сначала определить магистраль в построите топологий.</span><span class="sxs-lookup"><span data-stu-id="671da-113">To assign or remove a trunk in Skype for Business Server, you must first define a trunk in Topology Builder.</span></span> <span data-ttu-id="671da-114">Магистраль состоит из следующей связи: полное доменное имя сервера-посредника, прослушивает порт сервера-посредника, полное доменное имя шлюза и прослушивает порт шлюза.</span><span class="sxs-lookup"><span data-stu-id="671da-114">A trunk consists of the following association: Mediation Server fully qualified domain name (FQDN), the Mediation Server listening port, the gateway FQDN, and the gateway listening port.</span></span>
    
- <span data-ttu-id="671da-115">Чтобы настроить несколько магистральных магистрали, можно создать несколько ассоциаций между шлюзом и сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="671da-115">To configure multiple trunks, you can create multiple associations between the same gateway and the Mediation Server.</span></span> <span data-ttu-id="671da-116">Это обеспечивает дополнительную устойчивость инфраструктуры Корпоративная голосовая связь, что особенно полезно в сценариях межсервального обмена УАО.</span><span class="sxs-lookup"><span data-stu-id="671da-116">This provides additional resiliency to the Enterprise Voice infrastructure, which is especially useful in private branch exchange (PBX) interoperational scenarios.</span></span> 
    
<span data-ttu-id="671da-117">После определения магистрали ее необходимо связать с маршрутом.</span><span class="sxs-lookup"><span data-stu-id="671da-117">When a trunk is defined, it must be associated to a route.</span></span> <span data-ttu-id="671da-118">Чтобы связать магистраль с маршрутом, необходимо определить простое имя магистрали в построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="671da-118">To associate a trunk to a route, you define a simple name for the trunk in Topology Builder.</span></span> <span data-ttu-id="671da-119">Это простое имя используется в качестве имени магистрали в панели управления Skype для бизнеса Server, где магистрали могут быть связаны с маршрутами.</span><span class="sxs-lookup"><span data-stu-id="671da-119">This simple name is used as the trunk name in the Skype for Business Server Control Panel, where trunks can be associated with routes.</span></span> <span data-ttu-id="671da-120">Простое имя магистрали используется в качестве имени шлюза в оболочке управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="671da-120">The simple trunk name is used as the gateway name from the Skype for Business Server Management Shell.</span></span> 
  
```powershell
New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}
```

<span data-ttu-id="671da-121">Администратор должен выбрать магистраль по умолчанию, связанную с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="671da-121">The administrator must select a default trunk associated with a Mediation Server.</span></span> <span data-ttu-id="671da-122">В построитель топологий щелкните правой кнопкой мыши связанный сервер-посредник и выберите **"Свойства".**</span><span class="sxs-lookup"><span data-stu-id="671da-122">From the Topology Builder, right-click the associated Mediation Server, and then click **Properties**.</span></span> <span data-ttu-id="671da-123">Укажите шлюз по умолчанию для сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="671da-123">Specify the default gateway for the Mediation Server.</span></span> 
  

