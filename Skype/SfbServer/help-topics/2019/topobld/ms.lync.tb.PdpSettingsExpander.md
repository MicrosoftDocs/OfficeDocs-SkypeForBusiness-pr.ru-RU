---
title: Расширитель параметров контроля допуска звонков
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
ROBOTS: NOINDEX, NOFOLLOW
description: Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности. После настройки сети на использование контроля доступа звонков, следует включить контроль доступа звонков для применения заданных ограничений.
ms.openlocfilehash: 9453b29fd8ce52444c265e926663b400b4736c5b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32201666"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="d95fc-104">Расширитель параметров контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="d95fc-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="d95fc-p102">Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности. После настройки сети на использование контроля доступа звонков, следует включить контроль доступа звонков для применения заданных ограничений.</span><span class="sxs-lookup"><span data-stu-id="d95fc-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="d95fc-107">Контроль доступа звонков можно также включить на панели управления или с помощью командлетов командной консоли.</span><span class="sxs-lookup"><span data-stu-id="d95fc-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="d95fc-108">В разделе **Параметры контроля допуска звонков** диалогового окна **Изменение свойств** для данного сайта можно изменить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="d95fc-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="d95fc-109">**Включение службы контроля допуска звонков** Выберите этот параметр, чтобы включить службу Контроля.</span><span class="sxs-lookup"><span data-stu-id="d95fc-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="d95fc-110">При его снятии контроль допуска звонков отключается для всей сети.</span><span class="sxs-lookup"><span data-stu-id="d95fc-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="d95fc-111">Для включения контроля допуска звонков необходимо соответствующим образом настроить сеть.</span><span class="sxs-lookup"><span data-stu-id="d95fc-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="d95fc-112">Дополнительные сведения см в документации по развертыванию [развертывания контроля допуска в Скайп для Business Server звонков](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) .</span><span class="sxs-lookup"><span data-stu-id="d95fc-112">For details, see [Deploy call admission control in Skype for Business Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="d95fc-113">**Пул переднего плана для запуска контроля допуска звонков** Если этот параметр включен контроль допуска звонков, можно изменить пула, в котором оно выполняется.</span><span class="sxs-lookup"><span data-stu-id="d95fc-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="d95fc-114">Выберите пул в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="d95fc-114">Select the pool from the drop-down list.</span></span>
    

