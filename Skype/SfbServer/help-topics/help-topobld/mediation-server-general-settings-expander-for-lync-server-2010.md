---
title: Расширитель общих настроек сервера-посредника для Lync Server 2010
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: В этом диалоговом окне вы изменяете свойства серверов-посредников. По левой стороне содержится набор быстрых ссылок на общие параметры, параметры узла следующего перехода и параметры шлюза в ТСОП. В каждом разделе содержатся приведенные ниже параметры.
ms.openlocfilehash: 19687f8d6a97a9174782c094f80c5b52d6973caf
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48215160"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="36389-105">Расширитель общих настроек сервера-посредника для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="36389-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="36389-106">В этом диалоговом окне вы изменяете свойства серверов-посредников.</span><span class="sxs-lookup"><span data-stu-id="36389-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="36389-107">По левой стороне содержится набор быстрых ссылок на общие параметры, параметры узла следующего перехода и параметры шлюза в ТСОП.</span><span class="sxs-lookup"><span data-stu-id="36389-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="36389-108">В каждом разделе содержатся приведенные ниже параметры.</span><span class="sxs-lookup"><span data-stu-id="36389-108">In each section are the following settings:</span></span>

 <span data-ttu-id="36389-109">**Общие**сведения:</span><span class="sxs-lookup"><span data-stu-id="36389-109">**General**:</span></span>

- <span data-ttu-id="36389-110">**Полное доменное**имя: вы редактируете полное доменное имя сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="36389-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="36389-111">**Связи**: установите флажок **сопоставить пограничный пул (для компонентов мультимедиа)** и выберите Пограничный сервер или пограничный пул, который будет использоваться сервером-посредником в качестве пути к носителю для внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="36389-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="36389-112">**Узел следующего перехода**.</span><span class="sxs-lookup"><span data-stu-id="36389-112">**Next hop**:</span></span>

- <span data-ttu-id="36389-113">**Выбор следующего прыжка**: выберите из списка сервер переднего плана или интерфейсный пул, который будет использоваться в качестве пути к серверу-посреднику для связи с развертыванием.</span><span class="sxs-lookup"><span data-stu-id="36389-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="36389-114">**Шлюз ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="36389-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="36389-115">**Шлюз ТСОП сервера-посредника**.</span><span class="sxs-lookup"><span data-stu-id="36389-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="36389-116">**Порты прослушивания**: Определите порты, которые сервер-посредник должен прослушать.</span><span class="sxs-lookup"><span data-stu-id="36389-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="36389-117">Можно определить порт для протокола TLS или протокола **TLS** **или протокола**управления транспортом.</span><span class="sxs-lookup"><span data-stu-id="36389-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="36389-118">Чтобы запись порта TCP была доступна, необходимо установить флажок **включить порт TCP**.</span><span class="sxs-lookup"><span data-stu-id="36389-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="36389-119">Обратитесь к документации и параметрам конфигурации своего шлюза ТСОП, чтобы определить, требуется ли включить и задать значения портов для TLS, для TCP или для обоих этих протоколов.</span><span class="sxs-lookup"><span data-stu-id="36389-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="36389-120">TLS — это более безопасный протокол, использующий сертификаты для шифрования трафика между сервером-посредником и шлюзом PSTN.</span><span class="sxs-lookup"><span data-stu-id="36389-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="36389-121">TLS поддерживают не все шлюзы ТСОП.</span><span class="sxs-lookup"><span data-stu-id="36389-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="36389-122">Отображается список магистралей и шлюзов SIP, определенных и настроенных в развертывании.</span><span class="sxs-lookup"><span data-stu-id="36389-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="36389-123">Если записи отсутствуют, магистрали SIP или шлюзы в ТСОП в данном развертывании отсутствуют.</span><span class="sxs-lookup"><span data-stu-id="36389-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="36389-124">Вы определяете и настраиваете магистральы и шлюзы в разделе **Общие компоненты** в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="36389-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="36389-125">См. также</span><span class="sxs-lookup"><span data-stu-id="36389-125">See also</span></span>

[<span data-ttu-id="36389-126">Обзор распределения каналов SIP</span><span class="sxs-lookup"><span data-stu-id="36389-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="36389-127">Параметры развертывания шлюза ТСОП</span><span class="sxs-lookup"><span data-stu-id="36389-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
