---
title: Расширитель параметров службы сервера-посредника
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.FeMediationServiceSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 142c1acd-cdaa-4922-8379-aa1bdf56a964
ROBOTS: NOINDEX, NOFOLLOW
description: 'Для сервера-посредника можно указать следующие сведения:'
ms.openlocfilehash: b3b22cfbe4b85a237dfffbce1c22da3abde75f57
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49819509"
---
# <a name="mediation-service-settings-expander"></a><span data-ttu-id="00239-103">Расширитель параметров службы сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="00239-103">Mediation Service Settings Expander</span></span>

<span data-ttu-id="00239-104">Для **сервера-посредника** можно указать следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="00239-104">For **Mediation Server**, you can specify the following:</span></span>

<span data-ttu-id="00239-105">При размещении сервера-посредника в пуле переднего сервера или на сервере Standard Edition выберите включенный совмедом **сервер-посредник.**</span><span class="sxs-lookup"><span data-stu-id="00239-105">If you are collocating the Mediation Server onto the Front End pool or the Standard Edition server, select the check box **Collocated Mediation Server enabled**.</span></span> <span data-ttu-id="00239-106">Если вы решили не выполнить выполнив это, в этом разделе не будет настраиваемых</span><span class="sxs-lookup"><span data-stu-id="00239-106">If you choose not to collocate the Mediation Server, there are no definable settings in this section.</span></span>

<span data-ttu-id="00239-107">Если вы включили выполняйте выполнимые действия сервера-посредника, необходимо определить диапазон портов прослушивания на сервере для TLS.</span><span class="sxs-lookup"><span data-stu-id="00239-107">If you have enabled the collocation of the Mediation Server, you need to define the listening port range on the server for Transport Layer Security (TLS).</span></span> <span data-ttu-id="00239-108">По умолчанию используется порт 5067.</span><span class="sxs-lookup"><span data-stu-id="00239-108">By default, this port is 5067.</span></span> <span data-ttu-id="00239-109">Если включить параметр **Включить порт TCP**, необходимо определить порт TCP для совмещенного сервера-посредника.</span><span class="sxs-lookup"><span data-stu-id="00239-109">If you select **Enable TCP port**, you must define a Transmission Control Protocol (TCP) port for the collocated Mediation Server.</span></span> <span data-ttu-id="00239-110">Это необязательный параметр, и вам следует сослаться на требования шлюза или телефонной сети общего параметров (PSTN), чтобы определить, нужно ли это.</span><span class="sxs-lookup"><span data-stu-id="00239-110">This is an optional setting, and you should refer to the requirements of your gateway or public switched telephone network (PSTN) requirements to determine if you need this.</span></span> <span data-ttu-id="00239-111">По умолчанию значением порта TCP является 5068.</span><span class="sxs-lookup"><span data-stu-id="00239-111">By default, the TCP port value is 5068.</span></span>

<span data-ttu-id="00239-112">Следует определить шлюзы ТСОП, которые сопоставлены с совмещенным сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="00239-112">You define PSTN gateways that are associated with the collocated Mediation Server.</span></span> <span data-ttu-id="00239-113">Если шлюзы уже заданы, их можно будет сопоставить с сервером-посредником.</span><span class="sxs-lookup"><span data-stu-id="00239-113">If you have already defined gateways, they will be available to associate with the Mediation Server.</span></span>

<span data-ttu-id="00239-114">При наличии нескольких шлюзов, связанных с сервером-посредником, первый связанный шлюз будет шлюзом по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="00239-114">If you have more than one gateway associated with a Mediation Server, the first gateway associated will be the default gateway.</span></span> <span data-ttu-id="00239-115">Если вам нужно выбрать другой шлюз в качестве шлюза по умолчанию, выберите шлюз, который вы хотите сделать шлюзом по умолчанию, и нажмите кнопку **"По умолчанию".**</span><span class="sxs-lookup"><span data-stu-id="00239-115">If you need to choose another gateway as the default gateway, select the gateway that you want to make the default, and click **Make Default**.</span></span> <span data-ttu-id="00239-116">Чтобы отоиметь шлюз по умолчанию, щелкните **"Отклоните значение по умолчанию".**</span><span class="sxs-lookup"><span data-stu-id="00239-116">To unselect the gateway as the default, click **Unmake Default**.</span></span>

<span data-ttu-id="00239-117">Дополнительные сведения об определении и настройке параметров для пула переднего сервера Enterprise Edition или сервера Standard Edition см. в определении и настройке топологии и развертывания серверов-посредников и определения одноранговых [элементов.](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx) [](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx)</span><span class="sxs-lookup"><span data-stu-id="00239-117">For details about defining and configuring the settings for the Enterprise Edition Front End pool or Standard Edition server, see [Defining and Configuring the Topology](https://technet.microsoft.com/library/51d1601e-4f83-48d4-ad08-3b4d5e2003aa.aspx) and [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx).</span></span>


