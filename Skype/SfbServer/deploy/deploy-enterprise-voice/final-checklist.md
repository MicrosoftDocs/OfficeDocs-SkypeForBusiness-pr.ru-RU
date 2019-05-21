---
title: Конечный контрольный список развертывания управления допуском звонков для Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Последний контрольный список для развертывания управления допуском звонков (CAC) в Skype для бизнеса Server Enterprise.
ms.openlocfilehash: fab6472d931d0475a3e3b0a0f413fce7775d7a15
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281595"
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server"></a><span data-ttu-id="fb305-103">Развертывание элемента управления допуском звонков: последний контрольный список для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="fb305-103">Call admission control deployment: final checklist for Skype for Business Server</span></span>
 
<span data-ttu-id="fb305-104">Последний контрольный список для развертывания управления допуском звонков (CAC) в Skype для бизнеса Server Enterprise.</span><span class="sxs-lookup"><span data-stu-id="fb305-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="fb305-105">Используйте следующий контрольный список, чтобы убедиться в выполнении всех необходимых задач конфигурации для развертывания контроля допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="fb305-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="fb305-106">Если один или несколько пограничных серверов развертываются, то каждый IP-адрес внешнего интерфейса должен быть добавлен в список подсетей в параметрах сетевой конфигурации с битовой маской 32.</span><span class="sxs-lookup"><span data-stu-id="fb305-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="fb305-107">Следует также связать эту подсеть (IP-адрес) с идентификатором сетевого сайта для географического расположения, где развернута пограничная служба A/V.</span><span class="sxs-lookup"><span data-stu-id="fb305-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fb305-108">Пограничные серверы не обязаны реализовывать CAC.</span><span class="sxs-lookup"><span data-stu-id="fb305-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="fb305-109">Убедитесь, что включена активация CAC, как указано в подокне [Управление допуском звонков в Skype для бизнеса Server](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="fb305-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="fb305-110">Убедитесь в том, что контроль допуска звонков включен на всех центральных сайтах.</span><span class="sxs-lookup"><span data-stu-id="fb305-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="fb305-111">Это можно сделать с помощью построителя топологии.</span><span class="sxs-lookup"><span data-stu-id="fb305-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="fb305-112">Если при публикации создается предупреждение, *не* пропускайте его.</span><span class="sxs-lookup"><span data-stu-id="fb305-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="fb305-113">Убедитесь в том, что параметры всех подсетей, управляемых в корпоративной сети, соответствуют конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="fb305-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="fb305-114">Кроме того, важно, чтобы каждая подсеть была связана с сетевым сайтом, как описано в разделах [Развертывание сетевых регионов, сайтов и подсетей в Skype для бизнеса](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="fb305-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span>
    
- <span data-ttu-id="fb305-115">Убедитесь, что подсеть или IP-адреса всех серверов переднего плана, устройств для обеспечения связи в филиалах, серверов аудио- и видеоконференций (если они размещаются в отдельном пуле) и серверов-посредников настроены в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="fb305-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

