---
title: Настройка Федерации для поставщика голосовой конференц-связи в гибридном развертывании
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
description: Сводка. Узнайте, как настроить федерацию для поставщика аудио-конференций в Skype для бизнеса Online.
ms.openlocfilehash: a19704327d1cf5591a1ebb3f62aa23f46fe09d10
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726889"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="d0de9-103">Настройка Федерации для поставщика голосовой конференц-связи в гибридном развертывании</span><span class="sxs-lookup"><span data-stu-id="d0de9-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="d0de9-104">**Сводка:** Узнайте, как настроить федерацию для поставщика голосовой конференц-связи в Skype для бизнеса Online.</span><span class="sxs-lookup"><span data-stu-id="d0de9-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="d0de9-105">Если вы хотите использовать поставщика аудио-конференций (ACP) в гибридном развертывании (локально в сети), необходимо настроить федерацию между локальным развертыванием и партнером ACP в качестве разрешенного сервера-партнера.</span><span class="sxs-lookup"><span data-stu-id="d0de9-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="d0de9-106">Вы можете настроить федерацию, добавив домен партнера ACP и пограничный сервер (этот способ также может называться прокси-сервером доступа) в список федеративных доменов для локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="d0de9-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="d0de9-107">Затем партнеру ACP потребуется добавить полное доменное имя локального пула пограничных серверов в список разрешенных федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="d0de9-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="d0de9-108">Обратитесь к поставщику ACP за дополнительными сведениями.</span><span class="sxs-lookup"><span data-stu-id="d0de9-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="d0de9-109">Затем партнеру ACP потребуется добавить полное доменное имя локального пула пограничных серверов в список разрешенных федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="d0de9-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="d0de9-110">**Добавление домена ACP и пограничного сервера в качестве разрешенного федеративного домена**</span><span class="sxs-lookup"><span data-stu-id="d0de9-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="d0de9-111">Чтобы добавить домен ACP в качестве разрешенного сервера-партнера (разрешенный федеративный домен), выполните действия, описанные в разделе [Настройка поддержки для разрешенных внешних доменов](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span><span class="sxs-lookup"><span data-stu-id="d0de9-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="d0de9-112">В качестве пограничного сервера Добавьте полное доменное имя пограничного сервера партнера ACP.</span><span class="sxs-lookup"><span data-stu-id="d0de9-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="d0de9-113">Вам может потребоваться связаться с партнером ACP, чтобы получить полное доменное имя для пограничного сервера, которое также может называться в качестве прокси-сервера для доступа к вашему почтовому серверу.</span><span class="sxs-lookup"><span data-stu-id="d0de9-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="d0de9-114">**Предоставление полного доменного имени пула пограничного сервера партнеру ACP**</span><span class="sxs-lookup"><span data-stu-id="d0de9-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="d0de9-115">Партнеру ACP необходимо настроить федерацию, чтобы добавить локальный домен в качестве разрешенного сервера-партнера, добавив полное доменное имя пула пограничного сервера в качестве разрешенного федеративного домена.</span><span class="sxs-lookup"><span data-stu-id="d0de9-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


