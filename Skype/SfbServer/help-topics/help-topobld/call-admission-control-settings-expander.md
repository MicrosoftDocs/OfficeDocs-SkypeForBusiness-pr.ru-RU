---
title: Расширитель параметров контроля допуска звонков
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 1278cb19e4c8df047d97e5f391ca940255f094cc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833119"
---
# <a name="call-admission-control-settings-expander"></a><span data-ttu-id="c05cd-104">Расширитель параметров контроля допуска звонков</span><span class="sxs-lookup"><span data-stu-id="c05cd-104">Call Admission Control Settings Expander</span></span>
 
<span data-ttu-id="c05cd-p102">Контроль доступа звонков — это сеть регионов, сайтов и подсетей, которые позволяют вам налагать ограничения на передачу звука и видео в зависимости от доступной пропускной способности. После настройки сети на использование контроля доступа звонков, следует включить контроль доступа звонков для применения заданных ограничений.</span><span class="sxs-lookup"><span data-stu-id="c05cd-p102">Call admission control (CAC) is a network of regions, sites, and subnets that enable you to place restrictions on audio and video transmissions based on available bandwidth. After you configure the network for CAC, you must enable CAC in order for the bandwidth limitations to be enforced.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c05cd-107">Вы также можете включить контроль контроля пользования (CAC) с помощью панели управления или с помощью cmdlets оболочки управления.</span><span class="sxs-lookup"><span data-stu-id="c05cd-107">You can also use control panel or the management shell cmdlets to enable CAC.</span></span> 
  
<span data-ttu-id="c05cd-108">В разделе **Параметры контроля допуска звонков** диалогового окна **Изменение свойств** для вашего сайта можно изменить следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="c05cd-108">In the **Call Admission Control Setting** section of the **Edit Properties** dialog box for your site, you can change the following settings:</span></span>
  
- <span data-ttu-id="c05cd-109">**Включить контроль допуска вызовов** Выберите этот параметр, чтобы включить CAC.</span><span class="sxs-lookup"><span data-stu-id="c05cd-109">**Enable Call Admission Control** Select this setting to enable CAC.</span></span> <span data-ttu-id="c05cd-110">Отключите cac для всей сети.</span><span class="sxs-lookup"><span data-stu-id="c05cd-110">Clear this setting to disable CAC for your entire network.</span></span> <span data-ttu-id="c05cd-111">Чтобы включить CAC, необходимо настроить сеть для CAC.</span><span class="sxs-lookup"><span data-stu-id="c05cd-111">To enable CAC, you must have configured your network for CAC.</span></span> <span data-ttu-id="c05cd-112">Дополнительные сведения см. в документации по развертыванию системы контроля допуска звонков в Skype для бизнеса [Server 2015.](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md)</span><span class="sxs-lookup"><span data-stu-id="c05cd-112">For details, see [Deploy call admission control in Skype for Business Server 2015](../../deploy/deploy-enterprise-voice/deploy-call-admission-control.md) in the Deployment documentation.</span></span>
    
- <span data-ttu-id="c05cd-113">**Пул переднего входа для запуска контроля допуска вызовов** Если вы включили CAC, вы можете изменить пул, который его запускает.</span><span class="sxs-lookup"><span data-stu-id="c05cd-113">**Front End pool to run Call Admission Control** If you enabled CAC, you can change the pool that runs it.</span></span> <span data-ttu-id="c05cd-114">Выберите пул в выпадаемом списке.</span><span class="sxs-lookup"><span data-stu-id="c05cd-114">Select the pool from the drop-down list.</span></span>
    

