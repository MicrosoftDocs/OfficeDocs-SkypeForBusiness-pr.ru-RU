---
title: Устранение проблем связи с клиентом Microsoft Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
description: Сведения о поиске и устранении проблем связи с клиентом Microsoft Teams, которые чаще всего вызваны подключением к брандмауэру или прокси-серверу.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 79718ebc58205cd63ab291f0985e4dd7e452be3e
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36236553"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="cc4cf-103">Устранение проблем связи с клиентом Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc4cf-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="cc4cf-104">Большинство проблем с клиентом Microsoft Teams вызваны подключением к брандмауэру или прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="cc4cf-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="cc4cf-105">Проверив, открыты ли нужные порты, URL- и IP-адреса брандмауэра или прокси-севера, вы минимизируете вероятность неполадок.</span><span class="sxs-lookup"><span data-stu-id="cc4cf-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="cc4cf-106">Для получения подробных сведений о URL-адресах и адресах, необходимых для Microsoft Teams, ознакомьтесь со статьей [Office 365 URL-адреса и IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) (поддержка).</span><span class="sxs-lookup"><span data-stu-id="cc4cf-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="cc4cf-107">В описанных ниже сценариях требуется открыть определенные URL-адреса и порты в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="cc4cf-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="cc4cf-108">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="cc4cf-108">Authentication</span></span>

-   <span data-ttu-id="cc4cf-109">Взаимодействие с клиентом Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cc4cf-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="cc4cf-110">Совместная работа</span><span class="sxs-lookup"><span data-stu-id="cc4cf-110">Collaboration</span></span>

-   <span data-ttu-id="cc4cf-111">Мультимедиа</span><span class="sxs-lookup"><span data-stu-id="cc4cf-111">Media</span></span>

-   <span data-ttu-id="cc4cf-112">Общие службы</span><span class="sxs-lookup"><span data-stu-id="cc4cf-112">Shared Services</span></span>

-   <span data-ttu-id="cc4cf-113">Интеграция со сторонними решениями</span><span class="sxs-lookup"><span data-stu-id="cc4cf-113">Third Party Integration</span></span>

-   <span data-ttu-id="cc4cf-114">Взаимодействие со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cc4cf-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="cc4cf-115">Взаимодействие с клиентом Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="cc4cf-115">Skype for Business Client Interoperability</span></span>
