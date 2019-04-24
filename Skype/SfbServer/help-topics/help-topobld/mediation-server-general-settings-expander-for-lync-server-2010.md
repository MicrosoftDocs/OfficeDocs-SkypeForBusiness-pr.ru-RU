---
title: Расширитель общих настроек сервера-посредника для Lync Server 2010
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'Изменение свойств серверов-посредников в этом диалоговом окне. В левой представляют собой набор быстрые ссылки для параметров общих параметров, настройки следующего перехода и настройки шлюза ТСОП. В каждом разделе приведены следующие параметры:'
ms.openlocfilehash: a5af8e844c82d1af194e0c59fde67725c019ec99
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32200090"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="8ed07-105">Расширитель общих настроек сервера-посредника для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="8ed07-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="8ed07-106">Изменение свойств серверов-посредников в этом диалоговом окне.</span><span class="sxs-lookup"><span data-stu-id="8ed07-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="8ed07-107">В левой представляют собой набор быстрые ссылки для параметров общих параметров, настройки следующего перехода и настройки шлюза ТСОП.</span><span class="sxs-lookup"><span data-stu-id="8ed07-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="8ed07-108">В каждом разделе приведены следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="8ed07-108">In each section are the following settings:</span></span>

 <span data-ttu-id="8ed07-109">**Общие**:</span><span class="sxs-lookup"><span data-stu-id="8ed07-109">**General**:</span></span>

- <span data-ttu-id="8ed07-110">**Полное доменное имя**: изменение полное доменное имя сервера-посредника</span><span class="sxs-lookup"><span data-stu-id="8ed07-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="8ed07-111">**Связи**: установите флажок **сопоставить пограничный пул (для компонентов мультимедиа)** и выберите пограничный сервер или пограничный пул для сервера-посредника для использования в качестве пути к мультимедиа для внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="8ed07-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="8ed07-112">**Узел следующего перехода**:</span><span class="sxs-lookup"><span data-stu-id="8ed07-112">**Next hop**:</span></span>

- <span data-ttu-id="8ed07-113">**Выбор узла следующего перехода**: выберите из списка пул переднего плана или сервера переднего плана для использования в качестве пути для сервера-посредника для обмена данными с выполнением развертывания.</span><span class="sxs-lookup"><span data-stu-id="8ed07-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="8ed07-114">**Шлюз ТСОП**.</span><span class="sxs-lookup"><span data-stu-id="8ed07-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="8ed07-115">**Шлюз ТСОП сервера посредника**.</span><span class="sxs-lookup"><span data-stu-id="8ed07-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="8ed07-116">**Порты прослушивания**: определение портов прослушивания сервера-посредника на.</span><span class="sxs-lookup"><span data-stu-id="8ed07-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="8ed07-117">Вы можете определить порт для **TLS** или транспортного уровня безопасности или **TCP**или транспорта протокола управления.</span><span class="sxs-lookup"><span data-stu-id="8ed07-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="8ed07-118">Для запись порта TCP, чтобы оно было доступно необходимо установите флажок для **включения TCP-порт**.</span><span class="sxs-lookup"><span data-stu-id="8ed07-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8ed07-119">Обратитесь к документации и параметров конфигурации для шлюза телефонной сети (общего пользования PSTN) для определения, если необходимо включить и определите значения портов TLS, TCP или оба.</span><span class="sxs-lookup"><span data-stu-id="8ed07-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="8ed07-120">Протокол TLS является более безопасной протокола, с помощью сертификатов для шифрования трафика между сервером-посредником и шлюзом ТСОП.</span><span class="sxs-lookup"><span data-stu-id="8ed07-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="8ed07-121">Не все шлюзы ТСОП поддерживает TLS.</span><span class="sxs-lookup"><span data-stu-id="8ed07-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="8ed07-122">Отображается список элементов магистралях SIP и шлюзов, которые определены и настроены для развертывания.</span><span class="sxs-lookup"><span data-stu-id="8ed07-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="8ed07-123">Если нет записей, не существует магистралях SIP или шлюзы ТСОП, настроены для развертывания.</span><span class="sxs-lookup"><span data-stu-id="8ed07-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="8ed07-124">Определение и настройка магистрали и шлюзов в разделе **Общие компоненты** в построителе топологий.</span><span class="sxs-lookup"><span data-stu-id="8ed07-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="8ed07-125">См. также</span><span class="sxs-lookup"><span data-stu-id="8ed07-125">See also</span></span>

[<span data-ttu-id="8ed07-126">Обзор распределения каналов SIP</span><span class="sxs-lookup"><span data-stu-id="8ed07-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="8ed07-127">Параметры развертывания шлюза ТСОП</span><span class="sxs-lookup"><span data-stu-id="8ed07-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
