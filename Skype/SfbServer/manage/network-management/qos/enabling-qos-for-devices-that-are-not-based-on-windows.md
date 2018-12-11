---
title: Включение качества обслуживания для устройств, не входящий в систему Windows
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Узнайте, как включить качество обслуживания для устройств, используемых в вашей организации, использующие операционной системы, отличных от Windows.
ms.openlocfilehash: 0dc870080b3cfcd5f73eaf6e45aee841b9c8b488
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222774"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="c9fec-103">Включение качества обслуживания в Скайп для Business Server для устройств, не входящий в систему Windows</span><span class="sxs-lookup"><span data-stu-id="c9fec-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="c9fec-104">При установке Скайп для Business Server качества обслуживания (QoS) не быть включен для любого устройств, используемых в вашей организации, использующие операционной системы, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="c9fec-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="c9fec-105">Вы можете проверить, выполнив следующую команду в Скайп оболочки ServerManagement бизнеса:</span><span class="sxs-lookup"><span data-stu-id="c9fec-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="c9fec-106">Если предположить, что вы не вносили изменений в параметры конфигурации мультимедиа, вы должны получить сведения, похожие на следующие:</span><span class="sxs-lookup"><span data-stu-id="c9fec-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="c9fec-107">Если свойство EnableQoS установлено значение False (как и в предыдущем вывод), это означает, что не включено качества обслуживания для компьютеров и устройств, использующих операционной системы, отличных от Windows.</span><span class="sxs-lookup"><span data-stu-id="c9fec-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="c9fec-108">Чтобы включить качество обслуживания на глобальном уровне, выполните следующую команду в Скайп для консоли Business Server:</span><span class="sxs-lookup"><span data-stu-id="c9fec-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="c9fec-109">Приведенная выше команда включает качества обслуживания на глобальном уровне; Тем не менее важно Обратите внимание на то, что параметры конфигурации мультимедиа можно также применяются на уровне сайта.</span><span class="sxs-lookup"><span data-stu-id="c9fec-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="c9fec-110">Если требуется включить качество обслуживания для сайта, необходимо включить Identity параметров конфигурации при вызове Set-CsMediaConfiguration.</span><span class="sxs-lookup"><span data-stu-id="c9fec-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="c9fec-111">Например эта команда включает качества обслуживания для сайта Redmond:</span><span class="sxs-lookup"><span data-stu-id="c9fec-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="c9fec-112">Необходимо включить качество обслуживания на уровне сайта?</span><span class="sxs-lookup"><span data-stu-id="c9fec-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="c9fec-113">Смотря как.</span><span class="sxs-lookup"><span data-stu-id="c9fec-113">That depends.</span></span> <span data-ttu-id="c9fec-114">Параметры, назначенные на уровне сайта имеют приоритет перед параметрами назначен на глобальном уровне.</span><span class="sxs-lookup"><span data-stu-id="c9fec-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="c9fec-115">Предположим, что у вас есть QoS включен на глобальном уровне, но отключен на уровне сайта (для сайта Redmond).</span><span class="sxs-lookup"><span data-stu-id="c9fec-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="c9fec-116">В этом случае будут отключены качества обслуживания для сайта Redmond; Вот так, как параметры сайта, имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="c9fec-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="c9fec-117">Включение качества обслуживания для сайта Redmond, будет иметь для этого с помощью параметров конфигурации мультимедиа применяется для этого сайта.</span><span class="sxs-lookup"><span data-stu-id="c9fec-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="c9fec-118">Если вы хотите включить качество обслуживания одновременно для всех мультимедиа параметров конфигурации (вне зависимости от области действия), выполните следующую команду из внутри LSkype для консоли Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9fec-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="c9fec-119">Можно отключить качества обслуживания для устройств, использующих операционной системы, отличных от Windows, задав значение свойства EnableQoS значение False.</span><span class="sxs-lookup"><span data-stu-id="c9fec-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="c9fec-120">Например:</span><span class="sxs-lookup"><span data-stu-id="c9fec-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="c9fec-121">Это дает возможность реализации качества обслуживания на некоторые части сети (например, на сайте Redmond) при этом качества обслуживания на других частей сети отключена.</span><span class="sxs-lookup"><span data-stu-id="c9fec-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="c9fec-122">Только QoS могут включаться и отключаться с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c9fec-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="c9fec-123">Эти параметры недоступны в Скайп для панели управления Business Server.</span><span class="sxs-lookup"><span data-stu-id="c9fec-123">These options are not available in the Skype for Business Server Control Panel.</span></span>


