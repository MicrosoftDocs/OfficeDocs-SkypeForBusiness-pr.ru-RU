---
title: Расширитель настроек службы сервера-посредника
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/26/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
description: 'Для сервера-посредника можно указать следующие сведения:'
ms.openlocfilehash: 9a6da594452b4675b3eed1ca734fa3b54c9117b9
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215150"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="641dc-103">Расширитель настроек службы сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="641dc-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="641dc-104">Для **сервера-посредника** можно указать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="641dc-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="641dc-105">Если вы размещаете сервер-посредник в интерфейсном пуле или на сервере Standard Edition, установите флажок совмещенный **сервер-посредник**.</span><span class="sxs-lookup"><span data-stu-id="641dc-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="641dc-106">Если не выбрано совместное размещение сервера-посредника, в этом разделе нет настраиваемых параметров.</span><span class="sxs-lookup"><span data-stu-id="641dc-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="641dc-107">Если вы включили совмещение сервера-посредника, необходимо определить диапазон портов прослушивания на сервере для протокола TLS.</span><span class="sxs-lookup"><span data-stu-id="641dc-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="641dc-108">По умолчанию используется порт 5067.</span><span class="sxs-lookup"><span data-stu-id="641dc-108">By default, this port is 5067.</span></span> <span data-ttu-id="641dc-109">Если включить параметр **Включить порт TCP**, необходимо определить порт TCP для совмещенного сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="641dc-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="641dc-110">Это необязательный параметр, поэтому необходимо указать требования к шлюзу или требованиям PSTN, чтобы определить, требуется ли это.</span><span class="sxs-lookup"><span data-stu-id="641dc-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="641dc-111">По умолчанию значением порта TCP является 5068.</span><span class="sxs-lookup"><span data-stu-id="641dc-111">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="641dc-112">Следует определить шлюзы ТСОП, которые сопоставлены с совмещенным сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="641dc-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="641dc-113">Если шлюзы уже заданы, их можно будет сопоставить с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="641dc-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="641dc-114">При наличии нескольких шлюзов, связанных с сервером-посредником, первый связанный шлюз будет шлюзом по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="641dc-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="641dc-115">Если вам нужно выбрать другой шлюз в качестве шлюза по умолчанию, выберите шлюз, который необходимо установить по умолчанию, и щелкните **по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="641dc-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="641dc-116">Чтобы отменить выбор шлюза по умолчанию, нажмите **отменить по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="641dc-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="641dc-117">Сведения об определении и настройке параметров для пула переднего плана Enterprise Edition или сервера Standard Edition приведены в статье [Определение и Настройка топологии](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) и [развертывание серверов-посредников и определение одноранговых узлов](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span><span class="sxs-lookup"><span data-stu-id="641dc-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


