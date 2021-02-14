---
title: Включение качества обслуживания для устройств без Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Узнайте, как включить QoS для устройств, используемых в организации, которые используют операционную систему, кроме Windows.
ms.openlocfilehash: c22f9c98c796ee11d06e3d58a02a36befef4539e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814179"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="24cc5-103">Включение QoS в Skype для бизнеса Server для устройств, не основанных на Windows</span><span class="sxs-lookup"><span data-stu-id="24cc5-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="24cc5-104">При установке Skype для бизнеса Server качество обслуживания (QoS) не будет включено для устройств, используемых в организации, которые используют операционную систему, кроме Windows.</span><span class="sxs-lookup"><span data-stu-id="24cc5-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="24cc5-105">Для этого в командной оболочке Skype для бизнеса ServerManagement можно использовать следующую команду:</span><span class="sxs-lookup"><span data-stu-id="24cc5-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="24cc5-106">Если вы не влияли на параметры конфигурации мультимедиа, необходимо получить сведения, аналогичные этим:</span><span class="sxs-lookup"><span data-stu-id="24cc5-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="24cc5-107">Если для свойства EnableQoS задается false (как в предыдущем выходе), это означает, что качество обслуживания не включено для компьютеров и устройств, которые используют операционную систему, не включаемую в Windows.</span><span class="sxs-lookup"><span data-stu-id="24cc5-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="24cc5-108">Чтобы включить качество обслуживания на глобальном уровне, в командной оболочке Skype для бизнеса Server запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="24cc5-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="24cc5-109">При предыдущей команде QoS включается в глобальной области; однако важно отметить, что параметры конфигурации мультимедиа также могут применяться к области сайта.</span><span class="sxs-lookup"><span data-stu-id="24cc5-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="24cc5-110">Если необходимо включить качество обслуживания для сайта, при вызове set-CsMediaConfiguration необходимо включить удостоверение параметров конфигурации.</span><span class="sxs-lookup"><span data-stu-id="24cc5-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="24cc5-111">Например, эта команда включает QoS для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="24cc5-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="24cc5-112">Требуется ли включить QoS на уровне сайта?</span><span class="sxs-lookup"><span data-stu-id="24cc5-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="24cc5-113">Смотря как.</span><span class="sxs-lookup"><span data-stu-id="24cc5-113">That depends.</span></span> <span data-ttu-id="24cc5-114">Параметры, присвоенные области сайта, имеют приоритет над настройками, присвоенным глобальной области.</span><span class="sxs-lookup"><span data-stu-id="24cc5-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="24cc5-115">Предположим, что qoS включен на глобальном уровне, но отключен на уровне сайта (для сайта Redmond).</span><span class="sxs-lookup"><span data-stu-id="24cc5-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="24cc5-116">В этом случае качество обслуживания для сайта Redmond будет отключено; это потому, что приоритет имеют параметры сайта.</span><span class="sxs-lookup"><span data-stu-id="24cc5-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="24cc5-117">Чтобы включить QoS для сайта Redmond, необходимо использовать параметры конфигурации мультимедиа, применяемые к этому сайту.</span><span class="sxs-lookup"><span data-stu-id="24cc5-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="24cc5-118">Чтобы одновременно включить QoS для всех параметров конфигурации мультимедиа (независимо от области действия), запустите эту команду в командной оболочке LSkype для бизнеса Server:</span><span class="sxs-lookup"><span data-stu-id="24cc5-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="24cc5-119">Вы можете отключить QoS для устройств, которые используют операционную систему, не включаемую в Windows, установив для свойства EnableQoS значение False.</span><span class="sxs-lookup"><span data-stu-id="24cc5-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="24cc5-120">Пример:</span><span class="sxs-lookup"><span data-stu-id="24cc5-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="24cc5-121">Таким образом вы можете включить качество обслуживания для отдельных частей сети (например, узла Redmond), не включая его для других частей.</span><span class="sxs-lookup"><span data-stu-id="24cc5-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="24cc5-122">QoS можно включить и отключить только с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24cc5-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="24cc5-123">Эти параметры недоступны в панели управления Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="24cc5-123">These options are not available in the Skype for Business Server Control Panel.</span></span>

> [!NOTE]
> <span data-ttu-id="24cc5-124">Клиенты Skype для бизнеса для iOS версии 6.17 и более поздних версий теперь поддерживают QoS.</span><span class="sxs-lookup"><span data-stu-id="24cc5-124">Skype for Business clients for iOS Version 6.17 and later now support QoS.</span></span>  <span data-ttu-id="24cc5-125">Эта возможность QoS применима только к клиентам Skype для бизнеса и устройствам IP-телефонов, которые зарегистрированы непосредственно на внутреннем сервере Skype для бизнеса или сервере пула Lync в управляемых сетях.</span><span class="sxs-lookup"><span data-stu-id="24cc5-125">This QoS capability is only applicable to Skype for Business clients and IP phone devices which are registered directly to an internal Skype for Business or Lync pool Server on managed networks.</span></span> <span data-ttu-id="24cc5-126">QoS не применимо к трафику, маршрутуемого через Интернет.</span><span class="sxs-lookup"><span data-stu-id="24cc5-126">QoS is not applicable for traffic routed over the Internet.</span></span>



