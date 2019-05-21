---
title: Включение качества обслуживания для устройств без Windows
ms.reviewer: ''
ms:assetid: 26f793df-aef8-4028-9e3b-6c2c37ea61b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204750(v=OCS.15)
ms:contentKeyID: 48183661
mtps_version: v=OCS.15
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Сведения о том, как включить QoS для устройств, используемых в вашей организации, которые используют операционную систему, отличную от Windows.
ms.openlocfilehash: adb879d2319c5eeeb84578907ce57a3a408d9a13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34279412"
---
# <a name="enabling-qos-in-skype-for-business-server-for-devices-that-are-not-based-on-windows"></a><span data-ttu-id="17edf-103">Включение QoS в Skype для бизнеса Server для устройств, не основанных на Windows</span><span class="sxs-lookup"><span data-stu-id="17edf-103">Enabling QoS in Skype for Business Server for devices that are not based on Windows</span></span>


<span data-ttu-id="17edf-104">При установке Skype для бизнеса Server качество обслуживания (QoS) не будет разрешено для устройств, которые используются в вашей организации, использующих операционную систему, отличную от Windows.</span><span class="sxs-lookup"><span data-stu-id="17edf-104">When you install Skype for Business Server, Quality of Service (QoS) will not be enabled for any devices used in your organization that use an operating system other than Windows.</span></span> <span data-ttu-id="17edf-105">Вы можете проверить это, выполнив указанную ниже команду в командной консоли Skype для бизнеса Серверманажемент:</span><span class="sxs-lookup"><span data-stu-id="17edf-105">You can verify this by running the following command from within the Skype for Business ServerManagement Shell:</span></span>

    Get-CsMediaConfiguration

<span data-ttu-id="17edf-106">Если вы не внесли никаких изменений в параметры конфигурации мультимедиа, вы должны получить информацию, подобную следующей:</span><span class="sxs-lookup"><span data-stu-id="17edf-106">Assuming you have not made any changes to your media configuration settings, you should get back information similar to this:</span></span>

    Identity                          : Global
    EnableQoS                         : False
    EncryptionLevel                   : RequireEncryption
    EnableSiren                       : False
    MaxVideoRateAllowed               : VGA600K
    EnableG722StereoCodec             : True
    EnableH264Codec                   : True
    EnableAdaptiveBandwidthEstimation : True

<span data-ttu-id="17edf-107">Если для свойства Енаблекос задано значение false (как в предыдущем выводе), это означает, что качество обслуживания не разрешено для компьютеров и устройств, использующих операционную систему, отличную от Windows.</span><span class="sxs-lookup"><span data-stu-id="17edf-107">If the EnableQoS property is set to False (as in the preceding output) that means that Quality of Service is not enabled for computers and devices that use an operating system other than Windows.</span></span>

<span data-ttu-id="17edf-108">Чтобы включить качество обслуживания в глобальной области, выполните в командной консоли Skype для Business Server следующую команду:</span><span class="sxs-lookup"><span data-stu-id="17edf-108">To enable Quality of Service at the global scope, run the following command from within the Skype for Business Server Management Shell:</span></span>

    Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="17edf-109">Предыдущая команда включает QoS в глобальной области; Однако важно отметить, что параметры конфигурации мультимедиа также можно применить к области сайта.</span><span class="sxs-lookup"><span data-stu-id="17edf-109">The preceding command enables QoS at the global scope; however, it's important to note that media configuration settings can also be applied to the site scope.</span></span> <span data-ttu-id="17edf-110">Если необходимо включить качество обслуживания для сайта, необходимо включить удостоверение параметров конфигурации при вызове Set-Ксмедиаконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="17edf-110">If you need to enable Quality of Service for a site, you must include the Identity of the configuration settings when calling Set-CsMediaConfiguration.</span></span> <span data-ttu-id="17edf-111">Например, эта команда включает QoS для сайта Redmond.</span><span class="sxs-lookup"><span data-stu-id="17edf-111">For example, this command enables QoS for the Redmond site:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $True



> [!NOTE]  
> <span data-ttu-id="17edf-112">Нужно ли включить качество обслуживания в области сайта?</span><span class="sxs-lookup"><span data-stu-id="17edf-112">Do you need to enable QoS at the site scope?</span></span> <span data-ttu-id="17edf-113">Смотря как.</span><span class="sxs-lookup"><span data-stu-id="17edf-113">That depends.</span></span> <span data-ttu-id="17edf-114">Параметры, назначенные области сайта, имеют приоритет над параметрами, назначенными глобальной области.</span><span class="sxs-lookup"><span data-stu-id="17edf-114">Settings assigned to the site scope take precedence over settings assigned to the global scope.</span></span> <span data-ttu-id="17edf-115">Предположим, что в глобальной области включена служба QoS, но она отключена в области сайта (для сайта Redmond).</span><span class="sxs-lookup"><span data-stu-id="17edf-115">Suppose you have QoS enabled at the global scope but disabled at the site scope (for the Redmond site).</span></span> <span data-ttu-id="17edf-116">В этом случае качество обслуживания для сайта Redmond будет отключено. Это связано с тем, что параметры сайта имеют приоритет.</span><span class="sxs-lookup"><span data-stu-id="17edf-116">In that case, Quality of Service would be disabled for the Redmond site; that's because the site settings take precedence.</span></span> <span data-ttu-id="17edf-117">Чтобы включить качество обслуживания для сайта Redmond, необходимо сделать это с помощью параметров конфигурации мультимедиа, примененных к этому сайту.</span><span class="sxs-lookup"><span data-stu-id="17edf-117">To enable QoS for the Redmond site, you would have to do so using the media configuration settings applied to that site.</span></span>


<span data-ttu-id="17edf-118">Если вы хотите одновременно включить QoS для всех параметров конфигурации мультимедиа (вне зависимости от области), выполните эту команду в командной консоли управления Лскипе для Business Server.</span><span class="sxs-lookup"><span data-stu-id="17edf-118">If you want to simultaneously enable QoS for all your media configuration settings (regardless of scope), run this command from within the LSkype for Business Server Management Shell:</span></span>

    Get-CsMediaConfiguration | Set-CsMediaConfiguration -EnableQoS $True

<span data-ttu-id="17edf-119">Вы можете отключить QoS для устройств, использующих операционную систему, отличную от Windows, установив для свойства Енаблекос значение false.</span><span class="sxs-lookup"><span data-stu-id="17edf-119">You can disable QoS for devices that use an operating system other than Windows by setting the value of the EnableQoS property to False.</span></span> <span data-ttu-id="17edf-120">Например:</span><span class="sxs-lookup"><span data-stu-id="17edf-120">For example:</span></span>

    Set-CsMediaConfiguration -Identity site:Redmond -EnableQoS $False

<span data-ttu-id="17edf-121">Это позволяет реализовать качество обслуживания для некоторых частей сети (например, на сайте Redmond), не отключая качество обслуживания для других частей сети.</span><span class="sxs-lookup"><span data-stu-id="17edf-121">This gives you the ability to implement QoS on some portions of your network (for example, on the Redmond site) while leaving Quality of Service disabled on other portions of your network.</span></span>

<span data-ttu-id="17edf-122">Вы можете включать и отключать QoS только с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="17edf-122">QoS can only be enabled and disabled by using Windows PowerShell.</span></span> <span data-ttu-id="17edf-123">Эти параметры недоступны на панели управления сервера Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="17edf-123">These options are not available in the Skype for Business Server Control Panel.</span></span>


