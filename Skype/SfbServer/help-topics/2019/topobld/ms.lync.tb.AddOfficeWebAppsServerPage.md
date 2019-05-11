---
title: Добавление сервера Office Web Apps
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: 'Мастер определения нового сервера Office Web Apps определяется новый сервер Office Web Apps в вашем развертывании. You fill in the following information:'
ms.openlocfilehash: 90e138771e0f4a7524d6c277e9b317778af5ff21
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33886875"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="17b41-104">Добавление сервера Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="17b41-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="17b41-105">Мастер **Определения нового сервера Office Web Apps** определяется новый сервер Office Web Apps в вашем развертывании.</span><span class="sxs-lookup"><span data-stu-id="17b41-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="17b41-106">You fill in the following information:</span><span class="sxs-lookup"><span data-stu-id="17b41-106">You fill in the following information:</span></span>

 <span data-ttu-id="17b41-107">**Office Web Apps Server полное доменное имя**: Введите полное доменное имя сервера, на котором будет размещен сервер Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="17b41-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="17b41-108">**URL-адрес обнаружения сервера Office Web Apps**: Введите полный URL-адреса сервера Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="17b41-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="17b41-109">— Это поведение по умолчанию **URL-адрес обнаружения сервера Office Web Apps** для создания URL-адрес, основан на полное доменное имя сервера Office Web Apps в формате: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span><span class="sxs-lookup"><span data-stu-id="17b41-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="17b41-110">In most cases you will not need to change the default format.</span><span class="sxs-lookup"><span data-stu-id="17b41-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="17b41-111">Может потребоваться изменить формат по умолчанию, в случае, если сервер Office Web Apps и URL-адрес обнаружения сервера Office Web Apps должны быть разными.</span><span class="sxs-lookup"><span data-stu-id="17b41-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="17b41-112">К примеру сервера Office Web Apps размещается в демилитаризованной зоне и будет иметь другой URL-адрес на основе местоположения.</span><span class="sxs-lookup"><span data-stu-id="17b41-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="17b41-113">**Сервер Office Web Apps развернут во внешней сети (то есть в периметре/Интернете)**: установите флажок, если сервер Office Web Apps размещен за пределами внутреннего брандмауэра, например, в сети периметра, внешней сети или другие зоны сети Это не совпадает с вашей внутренней сети.</span><span class="sxs-lookup"><span data-stu-id="17b41-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="17b41-114">См. также</span><span class="sxs-lookup"><span data-stu-id="17b41-114">See also</span></span>

[<span data-ttu-id="17b41-115">Components and Topologies for Conferencing</span><span class="sxs-lookup"><span data-stu-id="17b41-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
