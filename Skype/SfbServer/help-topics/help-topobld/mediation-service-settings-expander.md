---
title: Расширитель параметров службы сервера-посредника
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
ms.openlocfilehash: 60312afc4ab487be474eeef6a8432e3522058275
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104425"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="0320d-103">Расширитель параметров службы сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="0320d-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="0320d-104">Для **сервера-посредника** можно указать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="0320d-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="0320d-105">Если вы коллокируете сервер-посредник на переднем конце пула или на сервере Standard Edition, выберите поле с включенным сервером-посредником **collocated.**</span><span class="sxs-lookup"><span data-stu-id="0320d-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="0320d-106">Если вы решите не коллокировать сервер-посредник, в этом разделе нет вызывающих параметров.</span><span class="sxs-lookup"><span data-stu-id="0320d-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="0320d-107">Если вы включили коллокацию сервера-посредника, необходимо определить диапазон порта прослушивания на сервере безопасности транспортного слоя (TLS).</span><span class="sxs-lookup"><span data-stu-id="0320d-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="0320d-108">По умолчанию используется порт 5067.</span><span class="sxs-lookup"><span data-stu-id="0320d-108">By default, this port is 5067.</span></span> <span data-ttu-id="0320d-109">Если включить параметр **Включить порт TCP**, необходимо определить порт TCP для совмещенного сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="0320d-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="0320d-110">Это необязательный параметр, и вы должны ссылаться на требования шлюза или общедоступных переключеных телефонных сетей (PSTN), чтобы определить, нужно ли это.</span><span class="sxs-lookup"><span data-stu-id="0320d-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="0320d-111">По умолчанию значением порта TCP является 5068.</span><span class="sxs-lookup"><span data-stu-id="0320d-111">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="0320d-112">Следует определить шлюзы ТСОП, которые сопоставлены с совмещенным сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="0320d-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="0320d-113">Если шлюзы уже заданы, их можно будет сопоставить с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="0320d-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="0320d-114">При наличии нескольких шлюзов, связанных с сервером-посредником, первый связанный шлюз будет шлюзом по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0320d-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="0320d-115">Если вам нужно выбрать другой шлюз в качестве шлюза по умолчанию, выберите шлюз, который необходимо сделать по умолчанию, и нажмите **кнопку Make Default**.</span><span class="sxs-lookup"><span data-stu-id="0320d-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="0320d-116">Чтобы отойдите от шлюза по умолчанию, нажмите **кнопку Unmake Default**.</span><span class="sxs-lookup"><span data-stu-id="0320d-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="0320d-117">Дополнительные сведения об определении и настройке параметров для переднего end-пула enterprise Edition или сервера Standard Edition см. в материале Определение и настройка топологии и развертывания серверов-посредников и определение одноранговых [серверов.](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers) [](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology)</span><span class="sxs-lookup"><span data-stu-id="0320d-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](/previous-versions/office/lync-server-2013/lync-server-2013-defining-and-configuring-the-topology) and [Deploying Mediation Servers and Defining Peers](/previous-versions/office/lync-server-2013/lync-server-2013-deploying-mediation-servers-and-defining-peers).</span></span>