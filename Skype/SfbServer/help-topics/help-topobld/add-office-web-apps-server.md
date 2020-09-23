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
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
description: Мастер определения нового сервера Office Web Apps определяет новый сервер Office Web Apps в развертывании. Следует указать следующие сведения.
ms.openlocfilehash: 9e1726ea4b536e46fdbca5ec3eddce25358cbbbb
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/23/2020
ms.locfileid: "48218730"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="cfca7-104">Добавление сервера Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="cfca7-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="cfca7-105">Мастер **определения нового сервера Office Web Apps** определяет новый сервер Office Web Apps в развертывании.</span><span class="sxs-lookup"><span data-stu-id="cfca7-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="cfca7-106">Следует указать следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="cfca7-106">You fill in the following information:</span></span>

 <span data-ttu-id="cfca7-107">ПОЛНОЕ доменное имя **сервера Office Web Apps**: введите полное доменное имя сервера, на котором будет размещаться сервер Office Web Apps.</span><span class="sxs-lookup"><span data-stu-id="cfca7-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="cfca7-108">**URL-адрес обнаружения сервера Office Web Apps**: введите полный URL-адрес сервера Office Web Apps (URL-адрес)</span><span class="sxs-lookup"><span data-stu-id="cfca7-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="cfca7-109">По умолчанию URL- **адрес обнаружения сервера Office Web Apps** используется для создания URL-адреса на основе полного доменного имени сервера Office Web Apps в формате: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span><span class="sxs-lookup"><span data-stu-id="cfca7-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="cfca7-110">В большинстве случаев нет необходимости изменять формат по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="cfca7-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="cfca7-111">Возможно, потребуется изменить формат по умолчанию в случае, если сервер Office Web Apps и URL-адрес обнаружения сервера Office Web Apps должны различаться.</span><span class="sxs-lookup"><span data-stu-id="cfca7-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="cfca7-112">Например, сервер Office Web Apps размещается в сети периметра и будет иметь другой URL-адрес на основе расположения.</span><span class="sxs-lookup"><span data-stu-id="cfca7-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="cfca7-113">**Сервер Office Web Apps развернут во внешней сети (периметр/Интернет)**: Установите этот флажок, если сервер Office Web Apps размещен за пределами внутреннего брандмауэра, такого как демилитаризованная зона, внешняя сеть или другая зона сети, не совпадающую с внутренней сетью.</span><span class="sxs-lookup"><span data-stu-id="cfca7-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="cfca7-114">См. также</span><span class="sxs-lookup"><span data-stu-id="cfca7-114">See also</span></span>

[<span data-ttu-id="cfca7-115">Компоненты и топологии для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="cfca7-115">Components and Topologies for Conferencing</span></span>](https://technet.microsoft.com/library/eb83052a-3360-4ba1-a6a0-6ee419942809.aspx)
