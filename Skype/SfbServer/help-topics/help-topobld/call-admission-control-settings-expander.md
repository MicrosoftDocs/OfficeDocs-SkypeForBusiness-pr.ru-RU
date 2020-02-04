---
title: Расширитель параметров контроля допуска звонков
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности. После настройки сети на использование контроля доступа звонков, следует включить контроль доступа звонков для применения заданных ограничений.
ms.openlocfilehash: 345668c61697dfa90e9e511d98ac82e6468440cc
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684862"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="ca4f9-104">Расширитель параметров контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="ca4f9-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="ca4f9-p102">Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности. После настройки сети на использование контроля доступа звонков, следует включить контроль доступа звонков для применения заданных ограничений.</span><span class="sxs-lookup"><span data-stu-id="ca4f9-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ca4f9-107">Контроль доступа звонков можно также включить на панели управления или с помощью командлетов командной консоли.</span><span class="sxs-lookup"><span data-stu-id="ca4f9-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="ca4f9-108">В разделе **Параметры контроля допуска звонков** диалогового окна **Изменение свойств** для данного сайта можно изменить следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="ca4f9-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="ca4f9-109">**Включить управление допуском звонков** Выберите этот параметр, чтобы включить CAC.</span><span class="sxs-lookup"><span data-stu-id="ca4f9-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="ca4f9-110">При его снятии контроль допуска звонков отключается для всей сети.</span><span class="sxs-lookup"><span data-stu-id="ca4f9-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="ca4f9-111">Для включения контроля допуска звонков необходимо соответствующим образом настроить сеть.</span><span class="sxs-lookup"><span data-stu-id="ca4f9-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="ca4f9-112">Подробнее смотрите в разделе [Развертывание элемента управления допуском звонков в Skype для бизнеса Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="ca4f9-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="ca4f9-113">**Пул переднего плана, на котором будет выполняться управление допуском звонков** Если включена служба CAC, вы можете изменить пул, на котором он выполняется.</span><span class="sxs-lookup"><span data-stu-id="ca4f9-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="ca4f9-114">Выберите пул в раскрывающемся списке.</span><span class="sxs-lookup"><span data-stu-id="ca4f9-114">Select the pool from the drop-down list.</span></span>
    

