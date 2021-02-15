---
title: Настройка глобальных параметров обхода сервера-посредника в Skype для бизнеса Server для использования сведений о сайте и регионе
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
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Настройте обход сервера-посредника для использования только для определенных сайтов и регионов в Skype для бизнеса Server Корпоративная голосовая связь.
ms.openlocfilehash: 58fd4fca90029a8a5f4cd82c6a9616ae66e69cd0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830589"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a><span data-ttu-id="fabcf-103">Настройка глобальных параметров обхода сервера-посредника в Skype для бизнеса Server для использования сведений о сайте и регионе</span><span class="sxs-lookup"><span data-stu-id="fabcf-103">Configure media bypass global settings in Skype for Business Server to use site and region information</span></span>
 
<span data-ttu-id="fabcf-104">Настройте обход сервера-посредника для использования только для определенных сайтов и регионов в Skype для бизнеса Server Корпоративная голосовая связь.</span><span class="sxs-lookup"><span data-stu-id="fabcf-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="fabcf-105">Если вы используете действия, которые необходимо предпринять в этом разделе, чтобы настроить глобальные параметры обхода мультимедиа, предположим, что у вас нет хорошего подключения между всеми конечными точками Skype для бизнеса и любым одноранговым устройством, для которого вы настроили обход мультимедиа в магистрали.</span><span class="sxs-lookup"><span data-stu-id="fabcf-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fabcf-p101">Информация об областях сети и сетевых узлах совместно используется компонентами расширенной корпоративной голосовой связи с обходом сервера посредника и контроля допуска звонков (когда оба этих компоненты включены). Таким образом, если контроль допуска звонков уже настроен, не нужно использовать следующую процедуру для изменения информации о сетевых узлах и областях сети специально для обхода сервера-посредника. Выполните описанные в этой процедуре действия, если области сети и сетевые узлы для контроля допуска звонков еще не настроены и нужно изменить параметры обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="fabcf-p101">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="fabcf-109">Для правильной работы обхода мультимедиа необходимо обеспечить согласованность между сайтом, определенным в построителье топологий, и при настройке областей сети и сетевых узлов.</span><span class="sxs-lookup"><span data-stu-id="fabcf-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="fabcf-110">Например, если у вас есть сайт филиала, определенный в построителе топологий как имеющий только развернутый шлюз STN, то этот сайт филиала должен быть настроен с помощью политики Корпоративная голосовая связь, которая позволяет пользователям сайта филиала маршрутировать свои вызовы STN через шлюз STN на сайте филиала.</span><span class="sxs-lookup"><span data-stu-id="fabcf-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="fabcf-111">Настройка сведений о сайте и области для обхода сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="fabcf-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="fabcf-112">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="fabcf-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="fabcf-113">В левой панели навигации щелкните элемент **Параметры сети**.</span><span class="sxs-lookup"><span data-stu-id="fabcf-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="fabcf-114">Дважды щелкните конфигурацию **Глобальная** в таблице.</span><span class="sxs-lookup"><span data-stu-id="fabcf-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="fabcf-115">На странице **Изменение глобальных параметров** установите флажок **Включить обход сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="fabcf-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="fabcf-116">Щелкните элемент **Использовать конфигурацию узлов и областей**.</span><span class="sxs-lookup"><span data-stu-id="fabcf-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="fabcf-117">При необходимости установите флажок **Включить обход сервера-посредника для несопоставленных сайтов**.</span><span class="sxs-lookup"><span data-stu-id="fabcf-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fabcf-p103">Установите этот флажок только в том случае, если есть один или несколько крупных сайтов, сопоставленных с одной областью, для которых отсутствуют ограничения по пропускной способности (например, крупный центральный сайт), но также имеется несколько сайтов филиалов, сопоставленных с той же областью, для которых ограничения по пропускной способности присутствуют. Когда разрешается обход для несопоставленных сайтов, конфигурация упрощается, так как указываются только подсети, сопоставленные с сайтами филиалов, а указывать все подсети, сопоставленные со всеми сайтами, не требуется. Рекомендуется не устанавливать этот флажок, когда включен контроль допуска звонков.</span><span class="sxs-lookup"><span data-stu-id="fabcf-p103">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="fabcf-121">Щелкните элемент **Зафиксировать**.</span><span class="sxs-lookup"><span data-stu-id="fabcf-121">Click **Commit**.</span></span>
    
<span data-ttu-id="fabcf-122">Затем добавьте подсети к сетевому сайту, как описано в описании связи подсети [с сетевым сайтом.](deploy-network.md#BKMK_AssociateSubnets)</span><span class="sxs-lookup"><span data-stu-id="fabcf-122">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets).</span></span> <span data-ttu-id="fabcf-123">После сопоставления всех подсетей с сетевыми узлами развертывание обхода сервера-посредника будет завершено.</span><span class="sxs-lookup"><span data-stu-id="fabcf-123">After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="fabcf-124">Если вы еще не создали области сети и сетевые узлы, вам необходимо создать их, прежде чем вы сможете приступить к развертыванию обхода сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="fabcf-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="fabcf-125">Дополнительные сведения см. в сведениях о развертывании областей сети, сайтов и [подсетей в Skype для бизнеса.](deploy-network.md)</span><span class="sxs-lookup"><span data-stu-id="fabcf-125">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fabcf-126">См. также</span><span class="sxs-lookup"><span data-stu-id="fabcf-126">See also</span></span>

[<span data-ttu-id="fabcf-127">Связывать подсеть с сетевым сайтом</span><span class="sxs-lookup"><span data-stu-id="fabcf-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

