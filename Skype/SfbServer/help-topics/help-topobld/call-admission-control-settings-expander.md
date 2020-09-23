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
- CSH
ms.custom:
- ms.lync.tb.PdpSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: dc94f75e-9abe-4e02-b835-3c845b317d65
description: Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности. После настройки сети на использование контроля доступа звонков, следует включить контроль доступа звонков для применения заданных ограничений.
ms.openlocfilehash: 4df5a9f5be761e1e039a259d0abf4a38d51170df
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218790"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="cbaeb-104">Расширитель параметров контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="cbaeb-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="cbaeb-p102">Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности. После настройки сети на использование контроля доступа звонков, следует включить контроль доступа звонков для применения заданных ограничений.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="cbaeb-107">Для включения контроля допуска звонков также можно использовать панель управления или командлеты командной консоли.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="cbaeb-108">В разделе **Параметры контроля допуска звонков** диалогового окна **Изменение свойств** для вашего сайта можно изменить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="cbaeb-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="cbaeb-109">**Включение контроля допуска звонков** Выберите этот параметр, чтобы включить службу контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="cbaeb-110">Снимите этот флажок, чтобы отключить CAC для всей сети.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="cbaeb-111">Чтобы включить службу контроля допуска звонков, необходимо настроить сеть для CAC.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="cbaeb-112">Дополнительную информацию можно узнать в статье Deployment [контроля допуска звонков в Skype для бизнеса Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) в документации по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="cbaeb-113">**Интерфейсный пул для запуска контроля допуска звонков** Если включена служба контроля допуска звонков, вы можете изменить пул, который его выполняет.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="cbaeb-114">Выберите пул из раскрывающегося списка.</span><span class="sxs-lookup"><span data-stu-id="cbaeb-114">Select the pool from the drop-down list.</span></span>
    

