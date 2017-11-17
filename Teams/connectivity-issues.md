---
title: "Устранение проблем связи с клиентом Microsoft Teams | Служба поддержки Майкрософт"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Сведения о поиске и устранении проблем связи с клиентом Microsoft Teams, которые чаще всего вызваны подключением к брандмауэру или прокси-серверу."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: fdba24620fca80b12b4e86780b19203436e7c9f4
ms.sourcegitcommit: 2e557e90b4e30fe99ff9df3897b8e54f38ea2f2e
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/22/2017
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="1dd99-103">Устранение проблем связи с клиентом Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1dd99-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="1dd99-104">Большинство проблем с клиентом Microsoft Teams вызваны подключением к брандмауэру или прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="1dd99-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="1dd99-105">Проверив, открыты ли нужные порты, URL- и IP-адреса брандмауэра или прокси-севера, вы минимизируете вероятность неполадок.</span><span class="sxs-lookup"><span data-stu-id="1dd99-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="1dd99-106">Сведения о конкретных URL- и IP-адресах для Microsoft Teams см. в [соответствующей статье](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US#bkmk_teams).</span><span class="sxs-lookup"><span data-stu-id="1dd99-106">For specific information on URLs and IPs required for Microsoft Teams, please reference the [Office 365 URLs and IP Address](https://support.office.com/en-us/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2?ui=en-US&rs=en-US&ad=US#bkmk_teams) support article.</span></span> <span data-ttu-id="1dd99-107">В описанных ниже сценариях требуется открыть определенные URL-адреса и порты в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="1dd99-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="1dd99-108">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="1dd99-108">Authentication</span></span>

-   <span data-ttu-id="1dd99-109">Взаимодействие с клиентом Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1dd99-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="1dd99-110">Совместная работа</span><span class="sxs-lookup"><span data-stu-id="1dd99-110">collaboration</span></span>

-   <span data-ttu-id="1dd99-111">Мультимедиа</span><span class="sxs-lookup"><span data-stu-id="1dd99-111">Media</span></span>

-   <span data-ttu-id="1dd99-112">Общие службы</span><span class="sxs-lookup"><span data-stu-id="1dd99-112">Shared Services</span></span>

-   <span data-ttu-id="1dd99-113">Интеграция со сторонними решениями</span><span class="sxs-lookup"><span data-stu-id="1dd99-113">Third Party Integration</span></span>

-   <span data-ttu-id="1dd99-114">Взаимодействие со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1dd99-114">Skype for Business</span></span>

-   <span data-ttu-id="1dd99-115">Взаимодействие с клиентом Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="1dd99-115">Skype for Business Client Interoperability</span></span>
