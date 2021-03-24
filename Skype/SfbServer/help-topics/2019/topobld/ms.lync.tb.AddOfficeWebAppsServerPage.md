---
title: Добавление сервера Office Web Apps
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddOfficeWebAppsServerPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8825dfb1-4b3d-4e01-ba4a-2bd800c6de3b
ROBOTS: NOINDEX, NOFOLLOW
description: Мастер Define New Office Web Apps Server определяет новый сервер Office Web Apps Server в развертывании. Следует указать следующие сведения.
ms.openlocfilehash: 84ebc3b3ca7a413d81b4a36e62cc33a4f3fd91f0
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095783"
---
# <a name="add-office-web-apps-server"></a><span data-ttu-id="d017c-104">Добавление сервера Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="d017c-104">Add Office Web Apps Server</span></span>

<span data-ttu-id="d017c-105">Мастер **Define New Office Web Apps Server** определяет новый сервер Office Web Apps Server в развертывании.</span><span class="sxs-lookup"><span data-stu-id="d017c-105">The **Define New Office Web Apps Server** wizard defines a new Office Web Apps Server in your deployment.</span></span> <span data-ttu-id="d017c-106">Следует указать следующие сведения.</span><span class="sxs-lookup"><span data-stu-id="d017c-106">You fill in the following information:</span></span>

 <span data-ttu-id="d017c-107">**Office Web Apps Server FQDN:** Введите полностью квалифицированное доменное имя сервера, на который будет работать сервер Office Web Apps Server.</span><span class="sxs-lookup"><span data-stu-id="d017c-107">**Office Web Apps Server FQDN**: Type the fully qualified domain name of the server that will host the Office Web Apps Server</span></span>

 <span data-ttu-id="d017c-108">**URL-адрес** обнаружения сервера веб-приложений Office: Введите полный единообразный локатор ресурсов (URL-адрес) Сервера веб-приложений Office</span><span class="sxs-lookup"><span data-stu-id="d017c-108">**Office Web Apps Server discovery URL**: Type the full uniform resource locator (URL) of the Office Web Apps Server</span></span>

> [!TIP]
> <span data-ttu-id="d017c-109">По умолчанию URL-адрес **обнаружения Office Web Apps Server** создает URL-адрес на основе FQDN сервера веб-приложений Office в формате: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span><span class="sxs-lookup"><span data-stu-id="d017c-109">The default behavior of the **Office Web Apps Server discovery URL** is to create the URL based on the FQDN of the Office Web Apps Server in the format: `https://<FQDN of the Office Web Apps Server/hosting/discovery` .</span></span> <span data-ttu-id="d017c-110">В большинстве случаев нет необходимости изменять формат по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="d017c-110">In most cases you will not need to change the default format.</span></span> <span data-ttu-id="d017c-111">Возможно, потребуется изменить формат по умолчанию в том случае, если URL-адрес сервера веб-приложений Office и URL-адреса обнаружения Office Web Apps Server должны быть другими.</span><span class="sxs-lookup"><span data-stu-id="d017c-111">You may need to change the default format in the event that the Office Web Apps Server and the Office Web Apps Server discovery URL must be different.</span></span> <span data-ttu-id="d017c-112">Например, сервер Office Web Apps расположен в сети периметра и будет иметь другой URL-адрес в зависимости от расположения.</span><span class="sxs-lookup"><span data-stu-id="d017c-112">For example, your Office Web Apps Server is placed in the perimeter network and will have a different URL based on the location.</span></span>

 <span data-ttu-id="d017c-113">**Сервер Office Web Apps** развертывается во внешней сети (то есть периметре или Интернете). Выберите поле для проверки, если сервер Office Web Apps Расположен за пределами внутреннего брандмауэра, например сети периметра, внешней сети или другой сетевой зоны, которая не является той же, что и внутренняя сеть.</span><span class="sxs-lookup"><span data-stu-id="d017c-113">**Office Web Apps Server is deployed in an external network (that is, perimeter/Internet)**: Select the check box if your Office Web Apps Server is placed outside of your internal firewall, such as the perimeter network, external network, or other network zone that is not the same as your internal network.</span></span>

## <a name="see-also"></a><span data-ttu-id="d017c-114">См. также</span><span class="sxs-lookup"><span data-stu-id="d017c-114">See also</span></span>

[<span data-ttu-id="d017c-115">Компоненты и топологии для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="d017c-115">Components and Topologies for Conferencing</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)