---
title: Расширитель общих настроек сервера-посредника для Lync Server 2010
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: Вы редактируете свойства серверов-посредников в этом диалоговом диалоговом ок. По левой стороне содержится набор быстрых ссылок на общие параметры, параметры узла следующего перехода и параметры шлюза в ТСОП. В каждом разделе содержатся приведенные ниже параметры.
ms.openlocfilehash: 6c8c238ce7d89db53f3b92a0f513c080976a3bab
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114195"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="d96b0-105">Расширитель общих параметров сервера-посредника для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="d96b0-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="d96b0-106">Вы редактируете свойства серверов-посредников в этом диалоговом диалоговом ок.</span><span class="sxs-lookup"><span data-stu-id="d96b0-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="d96b0-107">По левой стороне содержится набор быстрых ссылок на общие параметры, параметры узла следующего перехода и параметры шлюза в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="d96b0-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="d96b0-108">В каждом разделе содержатся приведенные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="d96b0-108">In each section are the following settings:</span></span>

 <span data-ttu-id="d96b0-109">**Общие:**</span><span class="sxs-lookup"><span data-stu-id="d96b0-109">**General**:</span></span>

- <span data-ttu-id="d96b0-110">**FQDN.** Вы редактируете полностью квалифицированное доменное имя сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="d96b0-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="d96b0-111">**Ассоциации.** Выберите поле "Дополнительный край" (для компонентов **мультимедиа)** и выберите поле Edge Server или Edge для сервера-посредника для использования в качестве средства для внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="d96b0-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="d96b0-112">**Узел следующего перехода**.</span><span class="sxs-lookup"><span data-stu-id="d96b0-112">**Next hop**:</span></span>

- <span data-ttu-id="d96b0-113">**Следующий выбор** хмеля. Выберите из списка пул переднего или переднего конечных серверов для использования в качестве пути к использованию сервера-посредника для связи с развертыванием.</span><span class="sxs-lookup"><span data-stu-id="d96b0-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="d96b0-114">**Шлюз ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="d96b0-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="d96b0-115">**Шлюз ТСОП сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="d96b0-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="d96b0-116">**Порты прослушивания.** Определите порты, на которые будет прослушиваться сервер-посредник.</span><span class="sxs-lookup"><span data-stu-id="d96b0-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="d96b0-117">Можно определить порт для **безопасности TLS** или транспортного слоя, **TCP** или протокола управления транспортом.</span><span class="sxs-lookup"><span data-stu-id="d96b0-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="d96b0-118">Чтобы вход в порт для TCP был доступен, необходимо выбрать контрольный ящик для **порта Включить TCP.**</span><span class="sxs-lookup"><span data-stu-id="d96b0-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d96b0-119">Обратитесь к документации и параметрам конфигурации своего шлюза ТСОП, чтобы определить, требуется ли включить и задать значения портов для TLS, для TCP или для обоих этих протоколов.</span><span class="sxs-lookup"><span data-stu-id="d96b0-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="d96b0-120">TLS — это более безопасный протокол, использующий сертификаты для шифрования трафика между сервером-посредником и шлюзом PSTN.</span><span class="sxs-lookup"><span data-stu-id="d96b0-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="d96b0-121">TLS поддерживают не все шлюзы ТСОП.</span><span class="sxs-lookup"><span data-stu-id="d96b0-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="d96b0-122">Отображается список магистралей и шлюзов SIP, определенных и настроенных в развертывании.</span><span class="sxs-lookup"><span data-stu-id="d96b0-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="d96b0-123">Если записи отсутствуют, магистрали SIP или шлюзы в ТСОП в данном развертывании отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="d96b0-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="d96b0-124">Вы определяете и настраивает магистрали и шлюзы в **разделе Общие компоненты** в Topology Builder.</span><span class="sxs-lookup"><span data-stu-id="d96b0-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="d96b0-125">См. также</span><span class="sxs-lookup"><span data-stu-id="d96b0-125">See also</span></span>

[<span data-ttu-id="d96b0-126">Обзор распределения каналов SIP</span><span class="sxs-lookup"><span data-stu-id="d96b0-126">Overview of SIP Trunking</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-sip-trunking)

[<span data-ttu-id="d96b0-127">Параметры развертывания шлюза ТСОП</span><span class="sxs-lookup"><span data-stu-id="d96b0-127">PSTN Gateway Deployment Options</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-pstn-gateway-deployment-options)