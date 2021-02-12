---
title: URL-адреса и диапазоны IP-адресов Microsoft 365 и Office 365
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Узнайте, как правильно настроить URL-адреса и диапазоны IP-адресов Microsoft 365 или Office 365, а также обойти прокси-сервер, если это возможно, для подключений к службе Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.network.ports
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1ad3ffdfd47b67ce21fb7f47a911afa67159f3e7
ms.sourcegitcommit: 3a577c07b4f399c81d8650a2bba8cfc00b695b49
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2020
ms.locfileid: "48650822"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="b9337-103">URL-адреса и диапазоны IP-адресов Microsoft 365 и Office 365</span><span class="sxs-lookup"><span data-stu-id="b9337-103">Microsoft 365 and Office 365 URLs and IP address ranges</span></span>
=======================================================

<span data-ttu-id="b9337-104">Перейдите на URL-адреса и диапазоны IP-адресов [Microsoft 365 и Office 365,](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) чтобы получить подробный и новый список URL-адресов, IP-адресов, портов и протоколов, которые необходимо правильно настроить для Teams.</span><span class="sxs-lookup"><span data-stu-id="b9337-104">Go to [Microsoft 365 and Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="b9337-105">Корпорация Майкрософт непрерывно совершенствует службы Microsoft 365 и Office 365 и добавляет новые функции, поэтому со временем требуемые порты, URL- и IP-адреса могут меняться.</span><span class="sxs-lookup"><span data-stu-id="b9337-105">Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="b9337-106">Мы рекомендуем вам [подписаться через RSS](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams), чтобы получать уведомления при изменении или обновлении этой информации.</span><span class="sxs-lookup"><span data-stu-id="b9337-106">We recommend that you [subscribe via RSS](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="b9337-107">Интерфейс звонков и собраний в Teams основан на облачной инфраструктуре следующего поколения, которая также применяется в Skype и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b9337-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="b9337-108">К таким технологическим нововведениям относятся облачные службы для обработки мультимедиа и сигнализации на основе Azure, видеокодек H.264, аудиокодек SILK и Opus, устойчивость сети, телеметрия и диагностика качества связи.</span><span class="sxs-lookup"><span data-stu-id="b9337-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="b9337-109">Таким образом, в число требований входят URL- и IP-адреса, которые могут быть сопоставлены как со Skype, так и со Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="b9337-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="b9337-110">Для всех рабочих нагрузок Microsoft 365 и Office 365 рекомендуемый способ подключения к службам Teams по возможности обходит перенаский прокси-сервер.</span><span class="sxs-lookup"><span data-stu-id="b9337-110">For all Microsoft 365 and Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="b9337-111">Если прокси-сервер находится между клиентом и центрами обработки данных Office 365, мультимедийный трафик может принудительно передаваться по протоколу TCP вместо UDP, что негативно повлияет на качество связи.</span><span class="sxs-lookup"><span data-stu-id="b9337-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="b9337-112">Скачайте образцы PAC-файлов прокси-сервера, которые можно использовать для настройки обхода трафика для управления конечными точками [Microsoft 365 и Office 365.](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)</span><span class="sxs-lookup"><span data-stu-id="b9337-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Microsoft 365 and Office 365 endpoints](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="b9337-113">Если для сетевых политик и политик безопасности требуется трафик Microsoft 365 или Office 365 для прокси-сервера, перед развертыванием Teams в производственной сфере убедитесь, что эти требования уже выполнены.</span><span class="sxs-lookup"><span data-stu-id="b9337-113">If your networking and security policies require Microsoft 365 or Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="b9337-114">Дополнительные сведения можно получить на [прокси-серверах для Teams или Skype для бизнеса Online.](proxy-servers-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="b9337-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>
