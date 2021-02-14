---
title: Добавление сервера Office Web Apps
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: Мастер определения нового сервера Office Web Apps определяет новый сервер Office Web Apps в развертывании. Следует указать следующие сведения.
ms.openlocfilehash: a0d0543576b75e0572abf3fd043a73369d2af136
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828599"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="65546-104">Добавление сервера Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="65546-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="65546-105">Мастер **определения нового сервера Office Web Apps** определяет новый сервер Office Web Apps в развертывании.</span><span class="sxs-lookup"><span data-stu-id="65546-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="65546-106">Следует указать следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="65546-106">You fill in the following information:</span></span>

 <span data-ttu-id="65546-107">**Полное доменное имя** сервера Office Web Apps: введите полное доменное имя сервера, на который будет работать сервер Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="65546-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="65546-108">**URL-адрес обнаружения Сервера Office Web Apps:** введите полный URL-адрес сервера Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="65546-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="65546-109">По умолчанию URL-адрес обнаружения **Сервера Office Web Apps** создается на основе FQDN сервера Office Web Apps в формате: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span><span class="sxs-lookup"><span data-stu-id="65546-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="65546-110">В большинстве случаев нет необходимости изменять формат по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="65546-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="65546-111">Вам может потребоваться изменить формат по умолчанию, если сервер Office Web Apps и URL-адрес обнаружения Сервера Office Web Apps должны быть другими.</span><span class="sxs-lookup"><span data-stu-id="65546-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="65546-112">Например, сервер Office Web Apps помещается в сеть периметра и будет иметь другой URL-адрес в зависимости от расположения.</span><span class="sxs-lookup"><span data-stu-id="65546-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="65546-113">**Сервер Office Web Apps** развертывается во внешней сети (то есть в периметре или Интернете). Если сервер Office Web Apps расположен за пределами внутреннего брандмауэра, например сети периметра, внешней сети или другой зоны сети, которая не является той же, что и внутренняя сеть.</span><span class="sxs-lookup"><span data-stu-id="65546-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="65546-114">См. также</span><span class="sxs-lookup"><span data-stu-id="65546-114">See also</span></span>

[<span data-ttu-id="65546-115">Компоненты и топологии для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="65546-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
