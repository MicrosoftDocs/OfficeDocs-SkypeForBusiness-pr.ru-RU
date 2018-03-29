---
title: Настройка глобальных параметров обхода мультимедиа в Скайп для 2015 Business Server для использования сведений об узлах и областях
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Настройка сервера-посредника для использования только для определенных узлов и областей в Скайп Business Server корпоративной голосовой связи.
ms.openlocfilehash: cebfa9d416fe3e68cd5615ae11616707ba1f60a8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-2015-to-use-site-and-region-information"></a><span data-ttu-id="cff80-103">Настройка глобальных параметров обхода мультимедиа в Скайп для 2015 Business Server для использования сведений об узлах и областях</span><span class="sxs-lookup"><span data-stu-id="cff80-103">Configure media bypass global settings in Skype for Business Server 2015 to use site and region information</span></span>
 
<span data-ttu-id="cff80-104">Настройка сервера-посредника для использования только для определенных узлов и областей в Скайп Business Server корпоративной голосовой связи.</span><span class="sxs-lookup"><span data-stu-id="cff80-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="cff80-105">Если вы используете пропускать действия, описанные в этом разделе, чтобы настроить глобальные параметры для мультимедиа, предполагается, что у вас нет хорошее подключение между все Скайп для конечных точек бизнеса и любой узел, для которого вы настроили обход сервера-посредника на подключении магистрали.</span><span class="sxs-lookup"><span data-stu-id="cff80-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cff80-p101">Информация об областях сети и сетевых узлах совместно используется компонентами расширенной корпоративной голосовой связи с обходом сервера посредника и контроля допуска звонков (когда оба этих компоненты включены). Таким образом, если контроль допуска звонков уже настроен, не нужно использовать следующую процедуру для изменения информации о сетевых узлах и областях сети специально для обхода сервера-посредника. Выполните описанные в этой процедуре действия, если области сети и сетевые узлы для контроля допуска звонков еще не настроены и нужно изменить параметры обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="cff80-p101">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="cff80-109">Для сервера-посредника для работы должным образом должен быть согласованность между сайтом, определенных в построителе топологий и как оно указано при настройке областей сети и сетевые узлы.</span><span class="sxs-lookup"><span data-stu-id="cff80-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="cff80-110">Например при наличии сайте филиала, который определен в построителе топологий как имеющий развернуть шлюз ТСОП, а затем этого сайта филиала должны быть настроены политики к корпоративной голосовой связи, которая позволяет пользователям сайта филиала их звонков ТСОП, направляться через PSTN шлюз на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="cff80-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="cff80-111">Настройка сведений о сайте и области для обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="cff80-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="cff80-112">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="cff80-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="cff80-113">В левой области навигации щелкните элемент **Конфигурация сети**.</span><span class="sxs-lookup"><span data-stu-id="cff80-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="cff80-114">Дважды щелкните конфигурацию **Глобальная** в таблице.</span><span class="sxs-lookup"><span data-stu-id="cff80-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="cff80-115">На странице **Изменение глобального параметра** установите флажок **Включить обход сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="cff80-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="cff80-116">Щелкните элемент **Использовать конфигурацию узлов и областей**.</span><span class="sxs-lookup"><span data-stu-id="cff80-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="cff80-117">При необходимости установите флажок **Включить обход сервера-посредника для несопоставленных сайтов**.</span><span class="sxs-lookup"><span data-stu-id="cff80-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cff80-p103">Установите этот флажок только в том случае, если есть один или несколько крупных сайтов, сопоставленных с одной областью, для которых отсутствуют ограничения по пропускной способности (например, крупный центральный сайт), но также имеется несколько сайтов филиалов, сопоставленных с той же областью, для которых ограничения по пропускной способности присутствуют. Когда разрешается обход для несопоставленных сайтов, конфигурация упрощается, так как указываются только подсети, сопоставленные с сайтами филиалов, а указывать все подсети, сопоставленные со всеми сайтами, не требуется. Рекомендуется не устанавливать этот флажок, когда включен контроль допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="cff80-p103">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="cff80-121">Нажмите **Исполнить**.</span><span class="sxs-lookup"><span data-stu-id="cff80-121">Click **Commit**.</span></span>
    
<span data-ttu-id="cff80-p104">Затем добавьте подсети в сетевой узел, как описано в статье [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). После сопоставления всех подсетей с сетевыми узлами развертывание обхода сервера-посредника будет завершено.</span><span class="sxs-lookup"><span data-stu-id="cff80-p104">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets). After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="cff80-124">Если вы еще не создали области сети и сетевые узлы, вам необходимо создать их, прежде чем вы сможете приступить к развертыванию обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="cff80-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="cff80-125">Дополнительные сведения см [областей сети развернуть, сайты и подсети в Скайп для бизнеса 2015](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="cff80-125">For details, see [Deploy network regions, sites and subnets in Skype for Business 2015](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="cff80-126">См. также</span><span class="sxs-lookup"><span data-stu-id="cff80-126">See also</span></span>

#### 

[<span data-ttu-id="cff80-127">Associate a subnet with a network site</span><span class="sxs-lookup"><span data-stu-id="cff80-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

