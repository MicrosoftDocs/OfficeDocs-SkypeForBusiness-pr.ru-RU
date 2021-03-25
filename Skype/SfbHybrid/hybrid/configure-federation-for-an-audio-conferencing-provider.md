---
title: Настройка федерации для поставщика аудиоконференций в гибридном развертывании
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: Сводка. Сведения о настройке федерации для поставщика аудиоконференций в Skype для бизнеса Online.
ms.openlocfilehash: 5d9c49299452f579cd7c58adf54facb09f0b8a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51118978"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="50d3e-103">Настройка федерации для поставщика аудиоконференций в гибридном развертывании</span><span class="sxs-lookup"><span data-stu-id="50d3e-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="50d3e-104">**Сводка:** Узнайте, как настроить федерацию для поставщика аудиоконференций в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="50d3e-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="50d3e-105">Если вы хотите использовать поставщика аудиоконференций (ACP) в гибридном развертывании (локально с помощью сети), необходимо настроить федерацию между локальной развертыванием и партнером ACP в качестве разрешенного сервера-партнера.</span><span class="sxs-lookup"><span data-stu-id="50d3e-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="50d3e-106">Вы можете настроить федерацию, добавив домен партнера ACP и сервер Edge (это также можно назвать прокси-сервер доступа) в список федератированных доменов для локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="50d3e-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="50d3e-107">Затем партнеру ACP необходимо добавить FQDN локального пула Edge Server в разрешенный список федераированных доменов.</span><span class="sxs-lookup"><span data-stu-id="50d3e-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="50d3e-108">Дополнительные сведения обратитесь к поставщику ACP.</span><span class="sxs-lookup"><span data-stu-id="50d3e-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="50d3e-109">Затем партнеру ACP необходимо добавить FQDN локального пула Edge Server в разрешенный список федераированных доменов.</span><span class="sxs-lookup"><span data-stu-id="50d3e-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="50d3e-110">**Добавление домена ACP и edge Server в качестве разрешенного федератного домена**</span><span class="sxs-lookup"><span data-stu-id="50d3e-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="50d3e-111">Чтобы добавить домен ACP в качестве разрешенного сервера партнеров (разрешенный федераированный домен), выполните действия в Настройка поддержки разрешенных [внешних доменов.](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains)</span><span class="sxs-lookup"><span data-stu-id="50d3e-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](/previous-versions/office/lync-server-2013/lync-server-2013-configure-support-for-allowed-external-domains).</span></span> <span data-ttu-id="50d3e-112">Для edge Server добавьте FQDN edge Server партнера ACP.</span><span class="sxs-lookup"><span data-stu-id="50d3e-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="50d3e-113">Возможно, вам потребуется связаться со своим партнером по ACP, чтобы получить FQDN для их edge Server, который также может быть передан вашей ACP в качестве их прокси-доступа.</span><span class="sxs-lookup"><span data-stu-id="50d3e-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="50d3e-114">**Предоставление FQDN вашего пула edge Server партнеру ACP**</span><span class="sxs-lookup"><span data-stu-id="50d3e-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="50d3e-115">Партнеру ACP необходимо настроить федерацию для добавления локального домена в качестве разрешенного сервера-партнера, добавив FQDN вашего пула edge Server в разрешенный федерательный домен.</span><span class="sxs-lookup"><span data-stu-id="50d3e-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>