---
title: Расширитель настроек службы сервера-посредника
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Для сервера-посредника необходимо указать следующее:'
ms.openlocfilehash: b1d7f088165c1287599d19e103b3a418d5f4a5f8
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2018
ms.locfileid: "19997089"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="e2daa-103">Расширитель настроек службы сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="e2daa-103">Mediation Service Settings Expander</span></span>
 
<span data-ttu-id="e2daa-104">В разделе **Сервер-посредник** можно задать следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="e2daa-104">For **Mediation Server**, you can specify the following:</span></span>
  
<span data-ttu-id="e2daa-105">Если collocating сервера-посредника на пул переднего плана или сервера Standard Edition, установите флажок, **включено, совмещенного сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="e2daa-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="e2daa-106">Если не выбрано совместно сервера-посредника, отсутствуют определяемые параметры в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e2daa-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span> 
  
<span data-ttu-id="e2daa-107">Если вы включили выровненное размещение сервера-посредника, необходимо определить диапазон портов прослушивания на сервере для безопасности TLS (Transport Layer).</span><span class="sxs-lookup"><span data-stu-id="e2daa-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="e2daa-108">По умолчанию используется порт 5067.</span><span class="sxs-lookup"><span data-stu-id="e2daa-108">By default, this port is 5067.</span></span> <span data-ttu-id="e2daa-109">Если выбран режим **Включить порт TCP**, необходимо задать порт TCP для совмещенного сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="e2daa-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="e2daa-110">Это необязательный параметр, который задается в зависимости от требований для шлюза или ТСОП.</span><span class="sxs-lookup"><span data-stu-id="e2daa-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="e2daa-111">Значение порта TCP по умолчанию: 5068.</span><span class="sxs-lookup"><span data-stu-id="e2daa-111">By default, the TCP port value is 5068.</span></span>
  
<span data-ttu-id="e2daa-112">Определите шлюзы ТСОП, связанных с совмещенным расположением сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="e2daa-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="e2daa-113">Если уже определенного шлюзы, они будут доступны для связи с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="e2daa-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span> 
  
<span data-ttu-id="e2daa-114">При наличии более одного шлюза, связанного с сервером-посредником первый связанный шлюз будет шлюз по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="e2daa-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="e2daa-115">Если требуется применять по умолчанию другой шлюз, выберите его и щелкните **По умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="e2daa-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="e2daa-116">Для отмены применения шлюза по умолчанию щелкните **Отменить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="e2daa-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>
  
<span data-ttu-id="e2daa-117">Для получения дополнительных сведений об определении и настройке параметров для пула переднего плана Enterprise Edition или сервера Standard Edition просмотрите [Определение и Настройка топологии](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) и [развертывание серверов-посредников и определение одноранговых узлов](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="e2daa-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](http://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](http://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>
  

