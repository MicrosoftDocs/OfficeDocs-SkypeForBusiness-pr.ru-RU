---
title: Окончательный контрольный список развертывания контроля допуска звонков для Skype для бизнеса Server
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
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Окончательный контрольный список для развертывания контроля допуска звонков (CAC) в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: d3a6484e35225627c8f22002823eff7fd5939694
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830839"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="f6785-103">Развертывание контроля допуска звонков: окончательный контрольный список для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="f6785-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="f6785-104">Окончательный контрольный список для развертывания контроля допуска звонков (CAC) в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="f6785-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="f6785-105">Используйте следующий контрольный список, чтобы убедиться, что вы выполнили все необходимые задачи настройки для развертывания контроля допуска вызовов (CAC).</span><span class="sxs-lookup"><span data-stu-id="f6785-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="f6785-p101">Если развернут один или несколько пограничных серверов, IP-адреса внешних интерфейсов необходимо добавить в список подсетей в параметрах конфигурации с битовой маской 32. Кроме того, необходимо связать эту подсеть (IP-адрес) с ИД сетевого узла для географического расположения, где развернута пограничная служба A/V.</span><span class="sxs-lookup"><span data-stu-id="f6785-p101">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32. You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f6785-108">Для реализации cac не требуются edge servers.</span><span class="sxs-lookup"><span data-stu-id="f6785-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="f6785-109">Убедитесь, что контроль допуска звонков включен, как указано в области "Включить контроль [допуска звонков" в Skype для бизнеса Server.](enable-call-admission-control.md)</span><span class="sxs-lookup"><span data-stu-id="f6785-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="f6785-110">Убедитесь, что контроль допуска звонков включен на всех центральных сайтах.</span><span class="sxs-lookup"><span data-stu-id="f6785-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="f6785-111">Это можно сделать с помощью построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="f6785-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="f6785-112">Если при публикации создается предупреждение,  *не игнорируйте*  его.</span><span class="sxs-lookup"><span data-stu-id="f6785-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="f6785-113">Убедитесь, что все подсети, управляемые в корпоративной сети, настроены в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="f6785-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="f6785-114">Кроме того, важно, чтобы каждая подсеть была связана с сетевым сайтом, как поясняется в развертывании областей сети, сайтов и подсетей [в Skype для бизнеса.](deploy-network.md)</span><span class="sxs-lookup"><span data-stu-id="f6785-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="f6785-115">Убедитесь, что подсеть или IP-адреса всех серверов переднего плана, устройств для обеспечения связи в филиалах, серверов аудио- и видеоконференций (если они размещаются в отдельном пуле) и серверов-посредников настроены в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="f6785-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

