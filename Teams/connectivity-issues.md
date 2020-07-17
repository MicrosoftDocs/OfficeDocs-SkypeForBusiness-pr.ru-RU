---
title: Устранение проблем с подключением в клиенте Teams
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: troubleshooting
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
search.appverid: MET150
f1.keywords:
- NOCSH
description: Сведения о поиске и устранении проблем связи с клиентом Microsoft Teams, которые чаще всего вызваны подключением к брандмауэру или прокси-серверу.
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 116ce1afef08a6f1639ed011b799f9ca43ea57f5
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085235"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="2e904-103">Устранение проблем связи с клиентом Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2e904-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="2e904-104">Большинство проблем с клиентом Microsoft Teams вызваны подключением к брандмауэру или прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="2e904-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="2e904-105">Проверив, открыты ли нужные порты, URL- и IP-адреса брандмауэра или прокси-севера, вы минимизируете вероятность неполадок.</span><span class="sxs-lookup"><span data-stu-id="2e904-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="2e904-106">Для получения подробных сведений о URL-адресах и адресах, необходимых для Microsoft Teams, ознакомьтесь со статьей [microsoft 365 и Office 365 URL-адреса и поддержка IP-адресов](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) .</span><span class="sxs-lookup"><span data-stu-id="2e904-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="2e904-107">В описанных ниже сценариях требуется открыть определенные URL-адреса и порты в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="2e904-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="2e904-108">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="2e904-108">Authentication</span></span>

-   <span data-ttu-id="2e904-109">Взаимодействие с клиентом Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2e904-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="2e904-110">Совместная работа</span><span class="sxs-lookup"><span data-stu-id="2e904-110">Collaboration</span></span>

-   <span data-ttu-id="2e904-111">Мультимедиа</span><span class="sxs-lookup"><span data-stu-id="2e904-111">Media</span></span>

-   <span data-ttu-id="2e904-112">Общие службы</span><span class="sxs-lookup"><span data-stu-id="2e904-112">Shared Services</span></span>

-   <span data-ttu-id="2e904-113">Интеграция со сторонними решениями</span><span class="sxs-lookup"><span data-stu-id="2e904-113">Third Party Integration</span></span>

-   <span data-ttu-id="2e904-114">Взаимодействие со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2e904-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="2e904-115">Взаимодействие с клиентом Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="2e904-115">Skype for Business Client Interoperability</span></span>


## <a name="related-topics"></a><span data-ttu-id="2e904-116">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="2e904-116">Related topics</span></span>

[<span data-ttu-id="2e904-117">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="2e904-117">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)