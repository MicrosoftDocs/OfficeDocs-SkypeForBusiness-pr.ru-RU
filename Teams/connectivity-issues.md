---
title: "Устранение проблем связи с клиентом Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения о поиске и устранении проблем связи с клиентом Microsoft Teams, которые чаще всего вызваны подключением к брандмауэру или прокси-серверу."
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1e1c194978d0a265eb964e3bcf288275492a6c1d
ms.sourcegitcommit: 85105cb4e42ae8eb6e7e76eaf6d4dd5b9568cf41
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/19/2018
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="ad203-103">Устранение проблем связи с клиентом Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ad203-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="ad203-104">Большинство проблем с клиентом Microsoft Teams вызваны подключением к брандмауэру или прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="ad203-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="ad203-105">Проверив, открыты ли нужные порты, URL- и IP-адреса брандмауэра или прокси-севера, вы минимизируете вероятность неполадок.</span><span class="sxs-lookup"><span data-stu-id="ad203-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="ad203-106">Сведения о конкретных URL- и IP-адресах для Microsoft Teams см. в [соответствующей статье](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US#bkmk_teams).</span><span class="sxs-lookup"><span data-stu-id="ad203-106">For specific information on URLs and IPs required for Microsoft Teams, please reference the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US#bkmk_teams) support article.</span></span> <span data-ttu-id="ad203-107">В описанных ниже сценариях требуется открыть определенные URL-адреса и порты в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="ad203-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="ad203-108">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="ad203-108">Authentication</span></span>

-   <span data-ttu-id="ad203-109">Взаимодействие с клиентом Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ad203-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="ad203-110">Совместная работа</span><span class="sxs-lookup"><span data-stu-id="ad203-110">Collaboration</span></span>

-   <span data-ttu-id="ad203-111">Мультимедиа</span><span class="sxs-lookup"><span data-stu-id="ad203-111">Media</span></span>

-   <span data-ttu-id="ad203-112">Общие службы</span><span class="sxs-lookup"><span data-stu-id="ad203-112">Shared Services</span></span>

-   <span data-ttu-id="ad203-113">Интеграция со сторонними решениями</span><span class="sxs-lookup"><span data-stu-id="ad203-113">Third Party Integration</span></span>

-   <span data-ttu-id="ad203-114">Взаимодействие со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ad203-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="ad203-115">Взаимодействие с клиентом Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ad203-115">Skype for Business Client Interoperability</span></span>
