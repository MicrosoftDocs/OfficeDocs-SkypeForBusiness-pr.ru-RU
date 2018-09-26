---
title: Настройка федерации для поставщика аудиоконференций в гибридном развертывании
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 'Сводка: Сведения о настройке федерации для поставщика аудиоконференций в Скайп для бизнеса в Интернет.'
ms.openlocfilehash: 2f89045e7d2ee3e51a6526344d2dcf2f07c0d98d
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "25030758"
---
# <a name="configure-federation-for-an-audio-conferencing-provider-in-your-hybrid-deployment"></a><span data-ttu-id="5bc3e-103">Настройка федерации для поставщика аудиоконференций в гибридном развертывании</span><span class="sxs-lookup"><span data-stu-id="5bc3e-103">Configure federation for an audio conferencing provider in your hybrid deployment</span></span>

<span data-ttu-id="5bc3e-104">**Сводка:** Сведения о настройке федерации для поставщика аудиоконференций в Скайп для бизнеса в Интернет.</span><span class="sxs-lookup"><span data-stu-id="5bc3e-104">**Summary:** Learn how to configure federation for an audio conferencing provider in Skype for Business Online.</span></span>

<span data-ttu-id="5bc3e-105">Если вы хотите использовать поставщика конференц-связи аудио (ACP) в гибридном развертывании (локальная online), необходимые для настройки федерации между локальным развертыванием и партнеров ACP как разрешенным сервером партнера.</span><span class="sxs-lookup"><span data-stu-id="5bc3e-105">If you want to use an Audio Conferencing Provider (ACP) in your hybrid deployment (on-premises with online), you need to configure federation between your on-premises deployment and the ACP partner as an Allowed Partner Server.</span></span> <span data-ttu-id="5bc3e-106">Федерации можно настроить путем добавления домена партнера ACP и пограничного сервера (это также может называться прокси-сервера доступа) в список федеративные домены для локального развертывания.</span><span class="sxs-lookup"><span data-stu-id="5bc3e-106">You can configure federation by adding the ACP partner domain and Edge server (this may also be called the Access Proxy) to the Federated Domains list for your on-premises deployment.</span></span> <span data-ttu-id="5bc3e-107">Ваш партнер ACP затем необходимо добавить полное доменное имя пула пограничных серверов в локальной в список разрешенных федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="5bc3e-107">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span> <span data-ttu-id="5bc3e-108">Обратитесь к поставщику услуг ACP для получения дополнительной информации.</span><span class="sxs-lookup"><span data-stu-id="5bc3e-108">Contact your ACP provider for additional details.</span></span> <span data-ttu-id="5bc3e-109">Ваш партнер ACP затем необходимо добавить полное доменное имя пула пограничных серверов в локальной в список разрешенных федеративных доменов.</span><span class="sxs-lookup"><span data-stu-id="5bc3e-109">Your ACP partner then needs to add the FQDN of your on-premises Edge Server pool to their allowed federated domains list.</span></span>

- <span data-ttu-id="5bc3e-110">**Добавление домена ACP и пограничного сервера в качестве разрешенных федеративных доменов**</span><span class="sxs-lookup"><span data-stu-id="5bc3e-110">**Adding the ACP Domain and Edge Server as an Allowed Federated Domain**</span></span>

    <span data-ttu-id="5bc3e-111">Чтобы добавить домен ACP разрешенным сервером партнера (разрешено федеративного домена), выполните действия, описанные в [Настройка поддержки для разрешенных внешних доменов](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span><span class="sxs-lookup"><span data-stu-id="5bc3e-111">To add the ACP domain as an Allowed Partner Server (allowed Federated Domain), follow the steps in [Configure Support for Allowed External Domains](https://technet.microsoft.com/library/3ee6e175-986d-4c33-b03a-b9f93083dca6.aspx).</span></span> <span data-ttu-id="5bc3e-112">Для пограничного сервера добавьте полное доменное имя партнера ACP пограничного сервера.</span><span class="sxs-lookup"><span data-stu-id="5bc3e-112">For the Edge Server, add the FQDN of the ACP partner's Edge Server.</span></span> <span data-ttu-id="5bc3e-113">Может потребоваться связаться со своим партнером ACP, чтобы получить полное доменное имя для своего пограничного сервера, на который ваши ACP могут ссылаться как на свой прокси-сервер доступа.</span><span class="sxs-lookup"><span data-stu-id="5bc3e-113">You may need to contact your ACP partner to obtain the FQDN for their Edge Server, which may also be referred to by your ACP as their Access Proxy.</span></span>

- <span data-ttu-id="5bc3e-114">**Предоставление полного доменного ИМЕНИ пула пограничных серверов ACP для партнеров**</span><span class="sxs-lookup"><span data-stu-id="5bc3e-114">**Providing the FQDN of your Edge Server Pool to the ACP partner**</span></span>

    <span data-ttu-id="5bc3e-115">Партнеру ACP необходимо настроить федерацию, чтобы добавить ваш локальный домен как разрешенный сервер-партнер, добавив полное доменное имя пула пограничных серверов в качестве разрешенного федеративного домена.</span><span class="sxs-lookup"><span data-stu-id="5bc3e-115">The ACP partner needs to configure federation to add your on-premises domain as an Allowed Partner Server by adding the FQDN of your Edge Server pool as an allowed Federated domain.</span></span>


