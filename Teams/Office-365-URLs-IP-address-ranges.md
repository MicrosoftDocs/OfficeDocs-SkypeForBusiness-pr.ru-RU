---
title: URL-адреса и диапазоны IP-адресов для Office 365
ms.reviewer: ''
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
audience: admin
ms.service: msteams
description: Сведения о правильной настройке URL-адресов и диапазонов IP-адресов для Office 365, возможностях обхода прокси-сервера переадресации для соединений со службой Microsoft Teams, а также требованиях к политикам сети и безопасности.
localization_priority: Normal
search.appverid: MET150
f1keywords: ms.teamsadmincenter.meetingsettings.network.ports
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5fc8d5bc41f7cf7a28140b30dd4a488c05b9b876
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2019
ms.locfileid: "37563873"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="1d16b-103">URL-адреса и диапазоны IP-адресов для Office 365</span><span class="sxs-lookup"><span data-stu-id="1d16b-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="1d16b-104">Перейдите в статью [URL-адреса и диапазоны IP-адресов Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams), чтобы просмотреть подробные и актуальные списки URL-адресов, IP-адресов, портов и протоколов, которые нужно настроить правильно для Teams.</span><span class="sxs-lookup"><span data-stu-id="1d16b-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges#skype-for-business-online-and-microsoft-teams) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="1d16b-105">Корпорация Майкрософт непрерывно совершенствует службу Office 365 и добавляет в нее новые функции, поэтому со временем требуемые порты, URL- и IP-адреса могут меняться.</span><span class="sxs-lookup"><span data-stu-id="1d16b-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="1d16b-106">Мы рекомендуем вам [подписаться через RSS](https://go.microsoft.com/fwlink/p/?linkid=236301), чтобы получать уведомления при изменении или обновлении этой информации.</span><span class="sxs-lookup"><span data-stu-id="1d16b-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="1d16b-107">Интерфейс звонков и собраний в Teams основан на облачной инфраструктуре следующего поколения, которая также применяется в Skype и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1d16b-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="1d16b-108">К этим технологиям относятся облачные службы, основанные на Azure, для обработки мультимедийных данных и сигнализации, H. 264 видеокодек, SILK и опус аудиокодек, устойчивость к сети, телеметрии и диагностики качества.</span><span class="sxs-lookup"><span data-stu-id="1d16b-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="1d16b-109">Таким образом, в число требований входят URL- и IP-адреса, которые могут быть сопоставлены как со Skype, так и со Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="1d16b-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="1d16b-110">Для всех рабочих нагрузок Office 365 рекомендуемым способом подключения к службам Teams является обход прокси-сервера переадресации, когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="1d16b-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="1d16b-111">Если прокси-сервер находится между клиентом и центрами обработки данных Office 365, мультимедийный трафик может принудительно передаваться по протоколу TCP вместо UDP, что негативно повлияет на качество связи.</span><span class="sxs-lookup"><span data-stu-id="1d16b-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="1d16b-112">Примеры PAC-файлов прокси-сервера, позволяющие настроить обход трафика, можно скачать в статье [Управление конечными точками Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span><span class="sxs-lookup"><span data-stu-id="1d16b-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span>

<span data-ttu-id="1d16b-113">Если в сети и политиках безопасности требуется трафик Office 365 для передачи через прокси-сервер, убедитесь, что указанные выше требования уже выполнены, прежде чем развертывать группы в рабочей среде (просмотрите [прокси-серверы для Teams или Skype для бизнеса Online](proxy-servers-for-skype-for-business-online.md) ). Инструкции).</span><span class="sxs-lookup"><span data-stu-id="1d16b-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production (review [Proxy Servers for Teams or Skype for Business Online](proxy-servers-for-skype-for-business-online.md) for guidance).</span></span>
