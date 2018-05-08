---
title: Вызова окончательный контрольный список развертывания контроля допуска для Скайп Business Server 2015
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
description: Последний контрольный список для развертывания вызова допуска элемента управления (CAC) в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: beec5c03f47d8f06ec862c3e9a3609fba7b66f2c
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="call-admission-control-deployment-final-checklist-for-skype-for-business-server-2015"></a><span data-ttu-id="23c1a-103">Контрольный список развертывания контроля допуска звонков для Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="23c1a-103">Call admission control deployment: final checklist for Skype for Business Server 2015</span></span>
 
<span data-ttu-id="23c1a-104">Последний контрольный список для развертывания вызова допуска элемента управления (CAC) в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="23c1a-104">Final checklist for deploying Call Admission Control (CAC) in Skype for Business Server Enterprise Voice.</span></span> 
  
<span data-ttu-id="23c1a-105">Используйте следующий контрольный список, чтобы убедиться в выполнении всех необходимых задач конфигурации для развертывания контроля допуска звонков (CAC).</span><span class="sxs-lookup"><span data-stu-id="23c1a-105">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy Call Admission Control (CAC).</span></span>
  
- <span data-ttu-id="23c1a-106">Если один или несколько пограничные серверы развернуты, каждого IP-адреса внешнего интерфейса необходимо добавить в список подсети в параметрах конфигурации сети с Битовая маска 32.</span><span class="sxs-lookup"><span data-stu-id="23c1a-106">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="23c1a-107">Следует также связать эту подсеть (IP-адрес) с идентификатором сетевого сайта для географического расположения, где развернута пограничная служба A/V.</span><span class="sxs-lookup"><span data-stu-id="23c1a-107">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="23c1a-108">Пограничные серверы не требуются для развертывания контроля допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="23c1a-108">Edge Servers are not required to implement CAC.</span></span> 
  
- <span data-ttu-id="23c1a-109">Убедитесь в том, что включен контроль допуска звонков, как указано в [Включить контроль допуска звонков в Скайп для Business Server 2015](enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="23c1a-109">Make sure that CAC is enabled, as specified in [Enable call admission control in Skype for Business Server 2015](enable-call-admission-control.md).</span></span>
    
- <span data-ttu-id="23c1a-110">Убедитесь в том, что контроль допуска звонков включен на всех центральных сайтах.</span><span class="sxs-lookup"><span data-stu-id="23c1a-110">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="23c1a-111">Это можно сделать через построитель топологий.</span><span class="sxs-lookup"><span data-stu-id="23c1a-111">This can be done through the Topology Builder.</span></span> <span data-ttu-id="23c1a-112">Если при публикации создается предупреждение, *не* пропустить его.</span><span class="sxs-lookup"><span data-stu-id="23c1a-112">If a warning is generated when you publish,  *do not*  ignore it.</span></span>
    
- <span data-ttu-id="23c1a-113">Убедитесь в том, что параметры всех подсетей, управляемых в корпоративной сети, соответствуют конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="23c1a-113">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="23c1a-114">Также важно, что каждую подсеть быть связаны с сетевым узлом, как описано в [области сети, сайты и подсети в Скайп для бизнеса 2015 развернуть](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="23c1a-114">It is also essential that every subnet be associated to a network site, as explained in [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span>
    
- <span data-ttu-id="23c1a-115">Убедитесь, что подсеть или IP-адреса всех серверов переднего плана, устройств для обеспечения связи в филиалах, серверов аудио- и видеоконференций (если они размещаются в отдельном пуле) и серверов-посредников настроены в параметрах конфигурации сети.</span><span class="sxs-lookup"><span data-stu-id="23c1a-115">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>
    

