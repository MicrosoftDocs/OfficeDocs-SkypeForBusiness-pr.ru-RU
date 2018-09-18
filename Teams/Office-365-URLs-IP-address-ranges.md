---
title: URL-адреса и диапазоны IP-адресов для Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: Сведения о правильной настройке URL-адресов и диапазонов IP-адресов для Office 365, возможностях обхода прокси-сервера переадресации для соединений со службой Microsoft Teams, а также требованиях к политикам сети и безопасности.
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: fddcd7a43b6296172b3bac0a7aad31032a585618
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23889546"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="7a95c-103">URL-адреса и диапазоны IP-адресов для Office 365</span><span class="sxs-lookup"><span data-stu-id="7a95c-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="7a95c-104">Перейдите в статью [URL-адреса и диапазоны IP-адресов Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges), чтобы просмотреть подробные и актуальные списки URL-адресов, IP-адресов, портов и протоколов, которые нужно настроить правильно для Teams.</span><span class="sxs-lookup"><span data-stu-id="7a95c-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="7a95c-105">Корпорация Майкрософт непрерывно совершенствует службу Office 365 и добавляет в нее новые функции, поэтому со временем требуемые порты, URL- и IP-адреса могут меняться.</span><span class="sxs-lookup"><span data-stu-id="7a95c-105">Microsoft is continuously improving the Office 365 service and adding new functionalities, therefore the required ports, URLs and IP addresses may change over time.</span></span> <span data-ttu-id="7a95c-106">Мы рекомендуем вам [подписаться через RSS](https://go.microsoft.com/fwlink/p/?linkid=236301), чтобы получать уведомления при изменении или обновлении этой информации.</span><span class="sxs-lookup"><span data-stu-id="7a95c-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="7a95c-107">Интерфейс звонков и собраний в Teams основан на облачной инфраструктуре следующего поколения, которая также применяется в Skype и Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7a95c-107">Teams also provides a calling and meetings experience that is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="7a95c-108">К таким технологическим нововведениям относятся облачные службы для обработки мультимедиа и сигнализации на основе Azure, видеокодек H.264, аудиокодек SILK и Opus, устойчивость сети, телеметрия и диагностика качества связи.</span><span class="sxs-lookup"><span data-stu-id="7a95c-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="7a95c-109">Таким образом, в число требований входят URL- и IP-адреса, которые могут быть сопоставлены как со Skype, так и со Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="7a95c-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="7a95c-110">Для всех рабочих нагрузок Office 365 рекомендуемым способом подключения к службам Teams является обход прокси-сервера переадресации, когда это возможно.</span><span class="sxs-lookup"><span data-stu-id="7a95c-110">For all Office 365 workloads, the recommended connection method to Microsoft Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="7a95c-111">Если прокси-сервер находится между клиентом и центрами обработки данных Office 365, мультимедийный трафик может принудительно передаваться по протоколу TCP вместо UDP, что негативно повлияет на качество связи.</span><span class="sxs-lookup"><span data-stu-id="7a95c-111">When a proxy server sits between a client and the Office 365 datacenters, media might be forced over TCP instead of UDP, that would impact media quality.</span></span> <span data-ttu-id="7a95c-112">Примеры PAC-файлов прокси-сервера, позволяющие настроить обход трафика, можно скачать в статье [Управление конечными точками Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span><span class="sxs-lookup"><span data-stu-id="7a95c-112">A sample proxy PAC files that can be used to configure traffic bypass can be downloaded from [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a) guide.</span></span>

<span data-ttu-id="7a95c-113">Если вашим политикам сети и безопасности требуется, чтобы трафик Office 365 протекал через прокси-сервер, обязательно выполните описанные выше требования перед развертыванием Teams в рабочей среде (см. статью [Прокси-серверы для Skype для бизнеса Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online)).</span><span class="sxs-lookup"><span data-stu-id="7a95c-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, then make sure that the above requirements are already met before deploying Microsoft Teams into production (review [Proxy Servers for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) for guidance.)</span></span>
