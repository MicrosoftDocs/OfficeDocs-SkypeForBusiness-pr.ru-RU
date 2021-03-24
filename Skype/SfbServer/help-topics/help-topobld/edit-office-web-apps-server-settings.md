---
title: Изменение параметров сервера Office Web Apps
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/19/2016
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.OfficeWebAppsServerSettingsExpander
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7a4b91ff-ca11-4dde-852d-ec51d143968a
description: Вы редактируете свойства настроенного Сервера веб-приложений Office. Для редактирования доступны следующие свойства.
ms.openlocfilehash: e9f4a188c5cb58be685db4ea44157f2897ebe5ba
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095543"
---
# <a name="edit-office-web-apps-server-settings"></a><span data-ttu-id="d3ef1-104">Изменение параметров сервера Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="d3ef1-104">Edit Office Web Apps Server Settings</span></span>

<span data-ttu-id="d3ef1-105">Вы редактируете свойства настроенного Сервера веб-приложений Office.</span><span class="sxs-lookup"><span data-stu-id="d3ef1-105">You edit the properties of the configured Office Web Apps Server.</span></span> <span data-ttu-id="d3ef1-106">Для редактирования доступны следующие свойства.</span><span class="sxs-lookup"><span data-stu-id="d3ef1-106">The following properties are available to edit:</span></span>

 <span data-ttu-id="d3ef1-107">**Office Web Apps Server FQDN.** Это свойство определяет полностью квалифицированное доменное имя Сервера веб-приложений Office и должно соответствовать записи системы доменных имен (DNS) хоста A или AAAA (если используется IPv6).</span><span class="sxs-lookup"><span data-stu-id="d3ef1-107">**Office Web Apps Server FQDN**: This property defines the fully qualified domain name of the Office Web Apps Server and should match a domain name system (DNS) host A or AAAA (if IPv6 is being used) record.</span></span>

 <span data-ttu-id="d3ef1-108">URL-адрес обнаружения Office Web **Apps Server.** Единый локатор ресурсов (URL-адрес) для клиентского доступа к серверу Office Web Apps, возможно, потребуется изменить этот адрес по умолчанию, если сервер находится в другой сетевой зоне, кроме внутренней сети для развертывания.</span><span class="sxs-lookup"><span data-stu-id="d3ef1-108">**Office Web Apps Server discovery URL**: The uniform resource locator (URL) for client access to the Office Web Apps Server, you may need to edit this address from its default if the server is placed in another network zone other than the internal network for your deployment.</span></span>

<span data-ttu-id="d3ef1-109">Установите флажок **Сервер Office Web Apps развернут во внешней сети**, если этот сервер развернут в сети периметра или в другой сетевой зоне за пределами внутреннего брандмауэра, разделяющего сеть периметра, сети без доверия и Интернет от внутреннего развертывания.</span><span class="sxs-lookup"><span data-stu-id="d3ef1-109">Select the check box **Office Web Apps Server is deployed in an external network** if this server is deployed in your perimeter network or other network zone that is outside of your internal firewall separating the perimeter network, less trusted networks, and the Internet from your internal deployment.</span></span>

![Расширение параметров веб-приложений Office](../../media/OfficeWebApps_Settings_Expander.jpg)

## <a name="see-also"></a><span data-ttu-id="d3ef1-111">См. также</span><span class="sxs-lookup"><span data-stu-id="d3ef1-111">See also</span></span>

[<span data-ttu-id="d3ef1-112">Компоненты и топологии для конференц-связи</span><span class="sxs-lookup"><span data-stu-id="d3ef1-112">Components and Topologies for Conferencing</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-components-and-topologies-for-conferencing)