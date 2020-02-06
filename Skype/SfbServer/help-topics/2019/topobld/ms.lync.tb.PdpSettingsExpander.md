---
title: Расширитель параметров контроля допуска звонков
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
ROBOTS: NOINDEX, NOFOLLOW
description: Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности. После настройки сети на использование контроля доступа звонков, следует включить контроль доступа звонков для применения заданных ограничений.
ms.openlocfilehash: cde55ba3cf6edb61e8a37f581341b7e5f6c11f45
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41797260"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="56262-104">Расширитель параметров контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="56262-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="56262-p102">Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности. После настройки сети на использование контроля доступа звонков, следует включить контроль доступа звонков для применения заданных ограничений.</span><span class="sxs-lookup"><span data-stu-id="56262-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="56262-107">Контроль доступа звонков можно также включить на панели управления или с помощью командлетов командной консоли.</span><span class="sxs-lookup"><span data-stu-id="56262-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="56262-108">В разделе **Параметры контроля допуска звонков** диалогового окна **Изменение свойств** для данного сайта можно изменить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="56262-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="56262-109">**Включить управление допуском звонков** Выберите этот параметр, чтобы включить CAC.</span><span class="sxs-lookup"><span data-stu-id="56262-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="56262-110">При его снятии контроль допуска звонков отключается для всей сети.</span><span class="sxs-lookup"><span data-stu-id="56262-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="56262-111">Для включения контроля допуска звонков необходимо соответствующим образом настроить сеть.</span><span class="sxs-lookup"><span data-stu-id="56262-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="56262-112">Подробности можно найти [в разделе Развертывание элемента управления допуском звонков в Skype для бизнеса Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="56262-112">For details, see [Deploy call admission control in Skype for Business Server](../../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="56262-113">**Пул переднего плана, на котором будет выполняться управление допуском звонков** Если включена служба CAC, вы можете изменить пул, на котором он выполняется.</span><span class="sxs-lookup"><span data-stu-id="56262-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="56262-114">Выберите пул в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="56262-114">Select the pool from the drop-down list.</span></span>
    

