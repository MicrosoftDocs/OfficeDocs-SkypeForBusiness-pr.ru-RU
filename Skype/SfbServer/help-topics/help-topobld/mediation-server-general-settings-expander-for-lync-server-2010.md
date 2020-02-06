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
- NOCSH
ms.custom:
- ms.lync.tb.MediationServerGeneralSettingsExpander2010
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 48e434c1-0c3c-4502-9441-c0a3c340f51f
description: 'В этом диалоговом окне вы изменяете свойства серверов обновлений. В левой части экрана представлен набор быстрых ссылок, в котором вы можете перейти к параметрам для параметров "Общие параметры", "Параметры следующего прыжка" и "шлюз PSTN". В каждом разделе находятся следующие параметры:'
ms.openlocfilehash: 3f7dad61778f54fee7a9be984191bc21f5029502
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41819621"
---
# <a name="mediation-server-general-settings-expander-for-lync-server-2010"></a><span data-ttu-id="2b19f-105">Расширитель общих настроек сервера-посредника для Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2b19f-105">Mediation Server General Settings Expander for Lync Server 2010</span></span>

<span data-ttu-id="2b19f-106">В этом диалоговом окне вы изменяете свойства серверов обновлений.</span><span class="sxs-lookup"><span data-stu-id="2b19f-106">You edit the properties of the Mediation Servers in this dialog.</span></span> <span data-ttu-id="2b19f-107">В левой части экрана представлен набор быстрых ссылок, в котором вы можете перейти к параметрам для параметров "Общие параметры", "Параметры следующего прыжка" и "шлюз PSTN".</span><span class="sxs-lookup"><span data-stu-id="2b19f-107">Along the left side is a set of quick links to take you to settings for General settings, Next hop settings, and PSTN gateway settings.</span></span> <span data-ttu-id="2b19f-108">В каждом разделе находятся следующие параметры:</span><span class="sxs-lookup"><span data-stu-id="2b19f-108">In each section are the following settings:</span></span>

 <span data-ttu-id="2b19f-109">**Общие положения**.</span><span class="sxs-lookup"><span data-stu-id="2b19f-109">**General**:</span></span>

- <span data-ttu-id="2b19f-110">**Полное доменное**имя: изменение полного доменного имени сервера обновлений</span><span class="sxs-lookup"><span data-stu-id="2b19f-110">**FQDN**: You edit the fully qualified domain name of the Mediation Server</span></span>

- <span data-ttu-id="2b19f-111">**Ассоциации**: установите флажок **сопоставление краевого пула (для компонентов мультимедиа)** и выберите граничный сервер или пул Edge для сервера-посредника, который будет использоваться в качестве пути мультимедиа для внешнего доступа.</span><span class="sxs-lookup"><span data-stu-id="2b19f-111">**Associations**: Select the **Associate Edge pool (for media components)** check box and select an Edge Server or Edge pool for the Mediation Server to use as the media path for external access.</span></span>

  <span data-ttu-id="2b19f-112">**Следующий прыжок**:</span><span class="sxs-lookup"><span data-stu-id="2b19f-112">**Next hop**:</span></span>

- <span data-ttu-id="2b19f-113">**Выбор следующего прыжка**: выберите из списка сервер переднего плана или пул переднего плана, который будет использоваться в качестве пути для сервера-посредника, который будет использоваться для связи с развертыванием.</span><span class="sxs-lookup"><span data-stu-id="2b19f-113">**Next hop selection**: Select from a list the Front End Server or Front End pool to use as the path for the Mediation Server to use for communicating with your deployment.</span></span>

  <span data-ttu-id="2b19f-114">**Шлюз PSTN**:</span><span class="sxs-lookup"><span data-stu-id="2b19f-114">**PSTN gateway**:</span></span>

  <span data-ttu-id="2b19f-115">**Шлюз PSTN сервера исправлений**:</span><span class="sxs-lookup"><span data-stu-id="2b19f-115">**Mediation Server PSTN gateway**:</span></span>

- <span data-ttu-id="2b19f-116">**Порты для прослушивания**: определяет порты, которые сервер обновлений будет прослушивать.</span><span class="sxs-lookup"><span data-stu-id="2b19f-116">**Listening ports**: Define the ports that the Mediation Server will listen on.</span></span> <span data-ttu-id="2b19f-117">Вы можете определить порт для **TLS** или безопасности транспортного уровня, **TCP**или протокола управления транспортировкой.</span><span class="sxs-lookup"><span data-stu-id="2b19f-117">You can define a port for **TLS** or transport layer security, or **TCP**, or transport control protocol.</span></span> <span data-ttu-id="2b19f-118">Чтобы запись порта TCP была доступна, необходимо установить флажок **включить TCP порт**.</span><span class="sxs-lookup"><span data-stu-id="2b19f-118">For the port entry for TCP to be available, you must select the check box for **Enable TCP port**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="2b19f-119">Обратитесь к документации и параметрам конфигурации для шлюза КОММУТИРУЕМой телефонной сети, чтобы определить, нужно ли включать и определять значения портов (TLS, TCP или и то, и другое).</span><span class="sxs-lookup"><span data-stu-id="2b19f-119">Refer to the documentation and configuration settings for your public switched telephone network (PSTN) gateway to determine if you need to enable and define port values TLS, TCP or both.</span></span> <span data-ttu-id="2b19f-120">TLS — это более безопасный протокол, использующий сертификаты для шифрования трафика между сервером-посредником и шлюзом PSTN.</span><span class="sxs-lookup"><span data-stu-id="2b19f-120">TLS is a more secure protocol, using certificates to encrypt the traffic between the Mediation Server and the PSTN gateway.</span></span> <span data-ttu-id="2b19f-121">Не все шлюзы PSTN поддерживают TLS.</span><span class="sxs-lookup"><span data-stu-id="2b19f-121">Not all PSTN gateways support TLS.</span></span>

- <span data-ttu-id="2b19f-122">Список магистральных каналов SIP и шлюзов, определенных и настроенных для вашего развертывания, перечислены в списке.</span><span class="sxs-lookup"><span data-stu-id="2b19f-122">A listing of SIP trunks and the gateways that are defined and configured for your deployment is listed.</span></span> <span data-ttu-id="2b19f-123">Если записей нет, магистральных каналов SIP и шлюзов PSTN, настроенных для развертывания, не существует.</span><span class="sxs-lookup"><span data-stu-id="2b19f-123">If no entries are present, there are no SIP trunks or PSTN gateways configured for your deployment.</span></span> <span data-ttu-id="2b19f-124">Вы определяете и настраиваете магистральные и шлюзы в **общих компонентах** в построителе топологии.</span><span class="sxs-lookup"><span data-stu-id="2b19f-124">You define and configure trunks and gateways under **Shared Components** in Topology Builder.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b19f-125">См. также</span><span class="sxs-lookup"><span data-stu-id="2b19f-125">See also</span></span>

[<span data-ttu-id="2b19f-126">Общие сведения о магистральных данных SIP</span><span class="sxs-lookup"><span data-stu-id="2b19f-126">Overview of SIP Trunking</span></span>](https://technet.microsoft.com/library/204f2c21-436f-4b2d-93ea-d6db98fa2952.aspx)

[<span data-ttu-id="2b19f-127">Параметры развертывания шлюза PSTN</span><span class="sxs-lookup"><span data-stu-id="2b19f-127">PSTN Gateway Deployment Options</span></span>](https://technet.microsoft.com/library/d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a.aspx)
