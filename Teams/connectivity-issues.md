---
title: Устранение проблем с подключением в клиенте Teams
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
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
ms.openlocfilehash: 52097d78a3eae14bcaba98fb1613092af97d302e
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581140"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="b2922-103">Устранение проблем связи с клиентом Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b2922-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="b2922-104">Большинство проблем с клиентом Microsoft Teams вызваны подключением к брандмауэру или прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="b2922-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="b2922-105">Проверив, открыты ли нужные порты, URL- и IP-адреса брандмауэра или прокси-севера, вы минимизируете вероятность неполадок.</span><span class="sxs-lookup"><span data-stu-id="b2922-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="b2922-106">Дополнительные сведения о URL-адресах и IP-адресах, необходимых для Microsoft Teams, см. в статье поддержки URL-адресов и IP-адресов [Microsoft 365 и Office 365.](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)</span><span class="sxs-lookup"><span data-stu-id="b2922-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="b2922-107">В описанных ниже сценариях требуется открыть определенные URL-адреса и порты в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="b2922-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="b2922-108">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="b2922-108">Authentication</span></span>

-   <span data-ttu-id="b2922-109">Взаимодействие с клиентом Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b2922-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="b2922-110">Совместная работа</span><span class="sxs-lookup"><span data-stu-id="b2922-110">Collaboration</span></span>

-   <span data-ttu-id="b2922-111">Мультимедиа</span><span class="sxs-lookup"><span data-stu-id="b2922-111">Media</span></span>

-   <span data-ttu-id="b2922-112">Общие службы</span><span class="sxs-lookup"><span data-stu-id="b2922-112">Shared Services</span></span>

-   <span data-ttu-id="b2922-113">Интеграция со сторонними решениями</span><span class="sxs-lookup"><span data-stu-id="b2922-113">Third Party Integration</span></span>

-   <span data-ttu-id="b2922-114">Взаимодействие со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b2922-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="b2922-115">Взаимодействие с клиентом Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="b2922-115">Skype for Business Client Interoperability</span></span>


## <a name="related-topics"></a><span data-ttu-id="b2922-116">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b2922-116">Related topics</span></span>

[<span data-ttu-id="b2922-117">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="b2922-117">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)