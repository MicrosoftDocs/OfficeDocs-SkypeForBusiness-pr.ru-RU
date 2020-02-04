---
title: Добавление сервера Office Web Apps
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: 'Мастер определения нового сервера Office Web Apps определяет новый сервер Office Web Apps в развертывании. You fill in the following information:'
ms.openlocfilehash: 2af737d2579fb4d89c6670e016ff89a8d24f3743
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/03/2020
ms.locfileid: "41685092"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="400cb-104">Добавление сервера Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="400cb-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="400cb-105">Мастер **определения нового сервера Office Web Apps** определяет новый сервер Office Web Apps в развертывании.</span><span class="sxs-lookup"><span data-stu-id="400cb-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="400cb-106">You fill in the following information:</span><span class="sxs-lookup"><span data-stu-id="400cb-106">You fill in the following information:</span></span>

 <span data-ttu-id="400cb-107">**Доменное имя сервера Office Web Apps**: введите полное доменное имя сервера, на котором будет размещен сервер Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="400cb-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="400cb-108">**URL-адрес обнаружения сервера Office Web Apps**: введите полный URL-адрес сервера Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="400cb-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="400cb-109">По умолчанию URL- **адрес обнаружения сервера Office Web Apps** — создание URL-адреса на основе полного доменного имени сервера Office Web Apps в формате: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span><span class="sxs-lookup"><span data-stu-id="400cb-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="400cb-110">In most cases you will not need to change the default format.</span><span class="sxs-lookup"><span data-stu-id="400cb-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="400cb-111">Возможно, потребуется изменить формат по умолчанию в случае, если URL-адрес сервера Office Web Apps и веб-сайта Office Web Apps не должен отличаться.</span><span class="sxs-lookup"><span data-stu-id="400cb-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="400cb-112">Например, сервер Office Web Apps размещается в демилитаризованной зоне, и его URL-адрес будет отличаться в зависимости от расположения.</span><span class="sxs-lookup"><span data-stu-id="400cb-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="400cb-113">**Сервер Office Web Apps развернут во внешней сети (то есть в сети периметра/Интернет)**: установите флажок, если сервер Office Web Apps размещается за пределами вашего внутреннего брандмауэра, например с демилитаризованной зоной, внешней сетью или другой сетевой зоной, не совпадающей с внутренней сетью.</span><span class="sxs-lookup"><span data-stu-id="400cb-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="400cb-114">См. также</span><span class="sxs-lookup"><span data-stu-id="400cb-114">See also</span></span>

[<span data-ttu-id="400cb-115">Components and Topologies for Conferencing</span><span class="sxs-lookup"><span data-stu-id="400cb-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
