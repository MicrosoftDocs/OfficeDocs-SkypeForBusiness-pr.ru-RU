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
ms.openlocfilehash: ee6cb916388dbfc0109185a0280da052980f8ccd
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/03/2020
ms.locfileid: "43137759"
---
<a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="ab805-103">Устранение проблем связи с клиентом Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ab805-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>
==============================================================

<span data-ttu-id="ab805-104">Большинство проблем с клиентом Microsoft Teams вызваны подключением к брандмауэру или прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="ab805-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="ab805-105">Проверив, открыты ли нужные порты, URL- и IP-адреса брандмауэра или прокси-севера, вы минимизируете вероятность неполадок.</span><span class="sxs-lookup"><span data-stu-id="ab805-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="ab805-106">Конкретную информацию об URL-адресах и IP-адресах, необходимых для Microsoft Teams, см. в статье о поддержке [URL-адресов и IP-адресов Office 365](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2).</span><span class="sxs-lookup"><span data-stu-id="ab805-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="ab805-107">В описанных ниже сценариях требуется открыть определенные URL-адреса и порты в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="ab805-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

-   <span data-ttu-id="ab805-108">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="ab805-108">Authentication</span></span>

-   <span data-ttu-id="ab805-109">Взаимодействие с клиентом Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ab805-109">Microsoft Teams Client Connectivity</span></span>

-   <span data-ttu-id="ab805-110">Совместная работа</span><span class="sxs-lookup"><span data-stu-id="ab805-110">Collaboration</span></span>

-   <span data-ttu-id="ab805-111">Мультимедиа</span><span class="sxs-lookup"><span data-stu-id="ab805-111">Media</span></span>

-   <span data-ttu-id="ab805-112">Общие службы</span><span class="sxs-lookup"><span data-stu-id="ab805-112">Shared Services</span></span>

-   <span data-ttu-id="ab805-113">Интеграция со сторонними решениями</span><span class="sxs-lookup"><span data-stu-id="ab805-113">Third Party Integration</span></span>

-   <span data-ttu-id="ab805-114">Взаимодействие со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ab805-114">Skype for Business Interoperability</span></span>

-   <span data-ttu-id="ab805-115">Взаимодействие с клиентом Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="ab805-115">Skype for Business Client Interoperability</span></span>
