---
title: URL-адреса и диапазоны IP-адресов для Office 365
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/21/2018
ms.topic: article
ms.service: msteams
description: Сведения о правильной настройке URL-адресов и диапазонов IP-адресов для Office 365, возможностях обхода прокси-сервера переадресации для соединений со службой Microsoft Teams, а также требованиях к политикам сети и безопасности.
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a21130d3e1c2e81203bb409fc2a53c77645bf0ba
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851925"
---
<a name="office-365-urls-and-ip-address-ranges"></a><span data-ttu-id="4089b-103">URL-адреса и диапазоны IP-адресов для Office 365</span><span class="sxs-lookup"><span data-stu-id="4089b-103">Office 365 URLs and IP address ranges</span></span>
=====================================

<span data-ttu-id="4089b-104">Перейдите в [Office 365 URL-адреса и диапазоны IP-адресов](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) подробные и актуальные список URL-адресов, адреса IP-адресов, порты и протоколы, должен быть правильно настроен для групп.</span><span class="sxs-lookup"><span data-stu-id="4089b-104">Go to [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) for a detailed and up-to-date list of the URLs, IP addresses, ports, and protocols that must be correctly configured for Teams.</span></span> <span data-ttu-id="4089b-105">Microsoft постоянно повышения качества обслуживания Office 365 и добавление новых функций, которая означает, что необходимые порты URL-адресов, и IP-адреса могут изменяться со временем.</span><span class="sxs-lookup"><span data-stu-id="4089b-105">Microsoft is continuously improving the Office 365 service and adding new functionality, which means the required ports, URLs, and IP addresses may change over time.</span></span> <span data-ttu-id="4089b-106">Мы рекомендуем, вы [Подпишитесь на RSS-канал](https://go.microsoft.com/fwlink/p/?linkid=236301) , чтобы получать уведомления при обновлении или изменить эти сведения.</span><span class="sxs-lookup"><span data-stu-id="4089b-106">We recommend that you [subscribe via RSS](https://go.microsoft.com/fwlink/p/?linkid=236301) to receive notifications when this information is updated or changed.</span></span>

<span data-ttu-id="4089b-107">Команды, собраний и вызова интерфейса создан на основе инфраструктуры следующего поколения на основе облака, который также используется Скайп и Скайп для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4089b-107">The Teams calling and meetings experience is built on the next generation cloud-based infrastructure that is also used by Skype and Skype for Business.</span></span> <span data-ttu-id="4089b-108">К таким технологическим нововведениям относятся облачные службы для обработки мультимедиа и сигнализации на основе Azure, видеокодек H.264, аудиокодек SILK и Opus, устойчивость сети, телеметрия и диагностика качества связи.</span><span class="sxs-lookup"><span data-stu-id="4089b-108">These technology investments include Azure-based cloud services for media processing and signaling, H.264 video codec, SILK and Opus audio codec, network resiliency, telemetry, and quality diagnostics.</span></span> <span data-ttu-id="4089b-109">Таким образом, в число требований входят URL- и IP-адреса, которые могут относиться как к Skype, так и к Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="4089b-109">As such, there are URLs and IPs that are required that may be associated with both Skype and Skype for Business.</span></span>

<span data-ttu-id="4089b-110">Для всех рабочих нагрузок Office 365 метод рекомендуемые подключения к службам групп — это обход прокси-сервере переадресации, где это возможно.</span><span class="sxs-lookup"><span data-stu-id="4089b-110">For all Office 365 workloads, the recommended connection method to Teams services is bypassing the forward proxy where possible.</span></span> <span data-ttu-id="4089b-111">Если прокси-сервера находится между клиентом и центров обработки данных Office 365, мультимедиа может принудительно через TCP вместо UDP-ПОРТ, который будет влиять на качество мультимедиа.</span><span class="sxs-lookup"><span data-stu-id="4089b-111">When a proxy server sits between a client and the Office 365 data centers, media might be forced over TCP instead of UDP, which would impact media quality.</span></span> <span data-ttu-id="4089b-112">Загрузите примеры файлов PAC прокси-сервера, которые могут использоваться для настройки сервера-посредника трафика из [конечных точек управления Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span><span class="sxs-lookup"><span data-stu-id="4089b-112">Download sample proxy PAC files that can be used to configure traffic bypass from [Managing Office 365 endpoints](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a).</span></span>

<span data-ttu-id="4089b-113">Если вашей сети и безопасности политиками Office 365 трафик через прокси-сервер, убедитесь в том, что выше уже требований перед развертыванием в рабочей группы ( [Прокси-серверы для Скайп для бизнеса в Интернет](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) для просмотра руководство по).</span><span class="sxs-lookup"><span data-stu-id="4089b-113">If your networking and security policies require Office 365 traffic to flow through a proxy server, make sure that the above requirements are already met before deploying Teams into production (review [Proxy Servers for Skype for Business Online](https://docs.microsoft.com/SkypeForBusiness/optimizing-your-network/proxy-servers-for-skype-for-business-online) for guidance).</span></span>
