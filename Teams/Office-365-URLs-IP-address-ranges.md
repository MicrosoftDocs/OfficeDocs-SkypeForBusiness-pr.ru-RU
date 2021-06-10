---
title: Microsoft 365 и Office 365 URL-адреса и диапазоны IP-адресов
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Узнайте, как правильно настроить Microsoft 365 или Office 365 URL-адреса и диапазоны IP-адресов и по возможности обойти прокси-сервер для подключений к службе Microsoft Teams.
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
ms.openlocfilehash: 9a29984b0b389bacb50a9aa6512a9ccc8bfe07de
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094521"
---
<a name="microsoft-365-and-office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="1458c-103">Microsoft 365 и Office 365 URL-адреса и диапазоны IP-адресов</span><span class="sxs-lookup"><span data-stu-id="1458c-103">Microsoft 365 and Office 365 URLs and IP address ranges</span></span>
=======================================================

<span data-ttu-id="1458c-104">Подробный и новый список URL-адресов, IP-адресов, IP-адресов, портов и протоколов, которые должны быть правильно настроены для Teams, можно найти в Microsoft 365 и [Office 365.](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams)</span><span class="sxs-lookup"><span data-stu-id="1458c-104">Go to [Microsoft 365 and Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="1458c-105">Корпорация Майкрософт непрерывно совершенствует службы Microsoft 365 и Office 365 и добавляет новые функции, поэтому со временем требуемые порты, URL- и IP-адреса могут меняться.</span><span class="sxs-lookup"><span data-stu-id="1458c-105">Microsoft is continuously improving the Microsoft 365 and Office 365 services and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="1458c-106">Мы рекомендуем подписаться [на RSS-канал,](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) чтобы получать уведомления об обновлении или смене данных.</span><span class="sxs-lookup"><span data-stu-id="1458c-106">We recommend that you [subscribe via RSS](/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="1458c-107">Вызовы Teams собраниями основаны на облачной инфраструктуре нового поколения, которая также используется Skype и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1458c-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="1458c-108">К этим технологиям относятся облачные службы на базе Azure для обработки мультимедиа и сигнального сигнала, видеокодек H.264, аудиокодек SILK и Opus, устойчивость сети, телеметрия и диагностика качества.</span><span class="sxs-lookup"><span data-stu-id="1458c-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="1458c-109">Поэтому существуют URL-адреса и URL-адреса, которые могут быть связаны как с Skype, так и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1458c-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="1458c-110">Для всех Microsoft 365 и Office 365 рабочих нагрузок рекомендуемый способ подключения к Teams службам — обход прокси-сервера, если это возможно.</span><span class="sxs-lookup"><span data-stu-id="1458c-110">For all Microsoft 365 and Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="1458c-111">Если прокси-сервер находится между клиентом и Office 365 центрами обработки данных, то вместо UDP может потребоваться использовать передачу мультимедиа через TCP, что повлияет на качество мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="1458c-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="1458c-112">Скачайте образцы PAC-файлов прокси-сервера, которые можно использовать для настройки обхода трафика в Microsoft 365 и [Office 365 конечных точек.](/office365/enterprise/managing-office-365-endpoints)</span><span class="sxs-lookup"><span data-stu-id="1458c-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Microsoft 365 and Office 365 endpoints](/office365/enterprise/managing-office-365-endpoints).</span></span>

<span data-ttu-id="1458c-113">Если для сетевых политик и политик безопасности требуется Microsoft 365 или Office 365 трафик для прокси-сервера, убедитесь, что эти требования уже выполнены, прежде чем Teams в производственной сфере.</span><span class="sxs-lookup"><span data-stu-id="1458c-113">If your networking and security policies require Microsoft 365 or Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production.</span></span> <span data-ttu-id="1458c-114">Дополнительные сведения можно узнать в документе [Прокси-серверы для Teams или Skype для бизнеса Online.](proxy-servers-for-skype-for-business-online.md)</span><span class="sxs-lookup"><span data-stu-id="1458c-114">For more information, read [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md).</span></span>