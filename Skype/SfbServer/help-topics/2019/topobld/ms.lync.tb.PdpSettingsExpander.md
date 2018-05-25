---
title: Расширитель параметров контроля допуска звонков
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/25/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности. После настройки сети на использование контроля доступа звонков, следует включить контроль доступа звонков для применения заданных ограничений.
ms.openlocfilehash: 9c3645b259949e208bd8bf6d0bc9d240ec5fe2e2
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2018
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="76c45-104">Расширитель параметров контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="76c45-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="76c45-p102">Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности. После настройки сети на использование контроля доступа звонков, следует включить контроль доступа звонков для применения заданных ограничений.</span><span class="sxs-lookup"><span data-stu-id="76c45-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="76c45-107">Контроль доступа звонков можно также включить на панели управления или с помощью командлетов командной консоли.</span><span class="sxs-lookup"><span data-stu-id="76c45-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="76c45-108">В разделе **Параметры контроля допуска звонков** диалогового окна **Изменение свойств** для данного сайта можно изменить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="76c45-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="76c45-109">**Включение службы контроля допуска звонков** Выберите этот параметр, чтобы включить службу Контроля.</span><span class="sxs-lookup"><span data-stu-id="76c45-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="76c45-110">При его снятии контроль допуска звонков отключается для всей сети.</span><span class="sxs-lookup"><span data-stu-id="76c45-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="76c45-111">Для включения контроля допуска звонков необходимо соответствующим образом настроить сеть.</span><span class="sxs-lookup"><span data-stu-id="76c45-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="76c45-112">Дополнительные сведения см в документации по развертыванию [развертывания контроля допуска в Скайп для Business Server 2015 звонков](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) .</span><span class="sxs-lookup"><span data-stu-id="76c45-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="76c45-113">**Пул переднего плана для запуска контроля допуска звонков** Если этот параметр включен контроль допуска звонков, можно изменить пула, в котором оно выполняется.</span><span class="sxs-lookup"><span data-stu-id="76c45-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="76c45-114">Выберите пул в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="76c45-114">Select the pool from the drop-down list.</span></span>
    

