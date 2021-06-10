---
title: Устранение неполадок с подключением Teams клиента
ms.reviewer: ''
author: SerdarSoysal
ms.author: serdars
manager: serdars
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
ms.openlocfilehash: f9ef787a5e103649c1526fab321cc8a9a088254c
ms.sourcegitcommit: 36bc47b2b9ee0e738fa814c31accacfe816da4a3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2021
ms.locfileid: "52856168"
---
# <a name="troubleshoot-connectivity-issues-with-the-microsoft-teams-client"></a><span data-ttu-id="77abf-103">Устранение проблем связи с клиентом Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77abf-103">Troubleshoot connectivity issues with the Microsoft Teams client</span></span>

<span data-ttu-id="77abf-104">Большинство проблем с клиентом Microsoft Teams вызваны подключением к брандмауэру или прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="77abf-104">Most issues discovered with the Microsoft Teams client can be traced back to firewall or proxy connectivity.</span></span> <span data-ttu-id="77abf-105">Проверив, открыты ли нужные порты, URL- и IP-адреса брандмауэра или прокси-севера, вы минимизируете вероятность неполадок.</span><span class="sxs-lookup"><span data-stu-id="77abf-105">Verifying that the necessary URLs, IP addresses and ports are opened in your firewall or proxy will minimize unnecessary troubleshooting.</span></span> <span data-ttu-id="77abf-106">Дополнительные сведения о URL-адресах и IP-адресах, необходимых для Microsoft Teams, см. в статье Microsoft 365 и [Office 365 URL-адреса](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) и IP-адреса.</span><span class="sxs-lookup"><span data-stu-id="77abf-106">For specific information on URLs and IPs required for Microsoft Teams, please see the [Microsoft 365 and Office 365 URLs and IP Address](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) support article.</span></span> <span data-ttu-id="77abf-107">В описанных ниже сценариях требуется открыть определенные URL-адреса и порты в брандмауэре.</span><span class="sxs-lookup"><span data-stu-id="77abf-107">The following scenarios require specific URLs and ports to be opened in the firewall.</span></span>

- <span data-ttu-id="77abf-108">Проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="77abf-108">Authentication</span></span>

- <span data-ttu-id="77abf-109">Взаимодействие с клиентом Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="77abf-109">Microsoft Teams Client Connectivity</span></span>

- <span data-ttu-id="77abf-110">Совместная работа</span><span class="sxs-lookup"><span data-stu-id="77abf-110">Collaboration</span></span>

- <span data-ttu-id="77abf-111">Мультимедиа</span><span class="sxs-lookup"><span data-stu-id="77abf-111">Media</span></span>

- <span data-ttu-id="77abf-112">Общие службы</span><span class="sxs-lookup"><span data-stu-id="77abf-112">Shared Services</span></span>

- <span data-ttu-id="77abf-113">Интеграция со сторонними решениями</span><span class="sxs-lookup"><span data-stu-id="77abf-113">Third Party Integration</span></span>

- <span data-ttu-id="77abf-114">Взаимодействие со Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="77abf-114">Skype for Business Interoperability</span></span>

- <span data-ttu-id="77abf-115">Взаимодействие с клиентом Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="77abf-115">Skype for Business Client Interoperability</span></span>

## <a name="when-teams-is-offline-or-in-low-bandwidth-conditions"></a><span data-ttu-id="77abf-116">Если Teams не в сети или при низкой пропускной способности</span><span class="sxs-lookup"><span data-stu-id="77abf-116">When Teams is offline or in low bandwidth conditions</span></span>

<span data-ttu-id="77abf-117">Хорошая новость заключается в том, что Teams работает даже в автономном режиме или при низкой пропускной способности.</span><span class="sxs-lookup"><span data-stu-id="77abf-117">The good news is that Teams keeps running even when you're offline or running in low bandwidth conditions.</span></span> <span data-ttu-id="77abf-118">Teams сохраняет все неуправляемые сообщения в существующих чатах (в течение 24 часов) и отправляет их, как только вы снова будете в сети.</span><span class="sxs-lookup"><span data-stu-id="77abf-118">Teams saves all your unsent messages for existing chats (for up to 24 hours) and sends them as soon as you're back online.</span></span> <span data-ttu-id="77abf-119">Если вы работаете в автономном режиме более 24 часов, Teams позволяет повторно отправить или удалить неуданные сообщения.</span><span class="sxs-lookup"><span data-stu-id="77abf-119">If you're offline for longer than 24 hours, Teams lets you choose to resend or delete unsent messages.</span></span> <span data-ttu-id="77abf-120">Мы работаем над добавлением этой функции в новые чаты и обновим эту документацию, когда она будет доступна.</span><span class="sxs-lookup"><span data-stu-id="77abf-120">We're working on adding this functionality to new chats and will update this documentation when that's available.</span></span>

## <a name="related-topics"></a><span data-ttu-id="77abf-121">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="77abf-121">Related topics</span></span>

[<span data-ttu-id="77abf-122">Устранение неполадок Teams</span><span class="sxs-lookup"><span data-stu-id="77abf-122">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)