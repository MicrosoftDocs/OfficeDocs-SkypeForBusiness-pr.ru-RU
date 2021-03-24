---
title: Интеграция Skype для бизнеса Server с Exchange Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: Сводка. Обзор действий по интеграции Exchange Server 2016 или Exchange Server 2013 г. и Skype для бизнеса Server.
ms.openlocfilehash: b19aa73e62b12674551690b716144fb67b4cd715
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104855"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="89981-103">Интеграция Skype для бизнеса Server с Exchange Server</span><span class="sxs-lookup"><span data-stu-id="89981-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="89981-104">**Сводка:** Просмотрите этапы интеграции Exchange Server 2013 или более позднего года и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="89981-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="89981-105">Exchange Server 2013 или более поздней и Skype для бизнеса Server совместимы и хорошо интегрируются.</span><span class="sxs-lookup"><span data-stu-id="89981-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="89981-106">Например, сведения о присутствии пользователей Skype для бизнеса можно отчитаться в Microsoft Outlook; Кроме того, Skype для бизнеса может получить доступ к календарю Outlook пользователя, заметить, что у пользователя запланирована встреча, и показать его присутствие как Занято во время собрания.</span><span class="sxs-lookup"><span data-stu-id="89981-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="89981-107">Хотя вам не нужно запускать Exchange Server для запуска Skype для бизнес-сервера (или наоборот), эти два продукта вместе улучшают пользовательский интерфейс друг друга.</span><span class="sxs-lookup"><span data-stu-id="89981-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="89981-108">В этой документации содержится информация об интеграции Skype для бизнеса Server и Exchange Server 2016 или Exchange Server 2013 г., но предполагается, что первоначальная настройка и конфигурация этих двух продуктов уже произошли.</span><span class="sxs-lookup"><span data-stu-id="89981-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="89981-109">Дополнительные сведения о развертывании Skype для бизнеса Server см. в техническом центре [Skype для бизнеса Server.](../../../Hub/index.yml)</span><span class="sxs-lookup"><span data-stu-id="89981-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](../../../Hub/index.yml).</span></span> <span data-ttu-id="89981-110">Дополнительные сведения о развертывании Exchange Server см. в документации по развертыванию для вашей версии Exchange.</span><span class="sxs-lookup"><span data-stu-id="89981-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="89981-111">Если вы интегрировали локальное устройство Skype для бизнеса Server с Microsoft Exchange Online, см. в примере Настройка интеграции между локальной установкой [Skype для](outlook-web-app.md)бизнеса Server и Outlook Web App .</span><span class="sxs-lookup"><span data-stu-id="89981-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="89981-112">Если вы интегрировали Skype для бизнеса Online с Exchange Server на месте, см. в рублях Настройка OAuth между Skype для бизнеса Online и [Exchange в помещениях.](oauth-with-online-and-on-premises.md)</span><span class="sxs-lookup"><span data-stu-id="89981-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="89981-113">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="89981-113">In this section</span></span>

[<span data-ttu-id="89981-114">Настройка партнерских приложений в Skype для бизнеса Server и Exchange Server</span><span class="sxs-lookup"><span data-stu-id="89981-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="89981-115">Настройка Skype для бизнес-сервера для использования Exchange Server архива</span><span class="sxs-lookup"><span data-stu-id="89981-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="89981-116">Настройка SharePoint Server для поиска архивных данных Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="89981-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="89981-117">Настройка Skype для бизнес-сервера для использования единого магазина контактов</span><span class="sxs-lookup"><span data-stu-id="89981-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="89981-118">Настройка использования фотографий с высоким разрешением в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="89981-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="89981-119">Настройка единой Exchange Server для голосовой почты Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="89981-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

<span data-ttu-id="89981-120">[Интеграция Skype для бизнеса Server и Microsoft Outlook Web App 2013 г.](/previous-versions/office/communications/jj688055(v=ocs.16))</span><span class="sxs-lookup"><span data-stu-id="89981-120">[Integrating Skype for Business Server and Microsoft Outlook Web App 2013](/previous-versions/office/communications/jj688055(v=ocs.16))</span></span>

[<span data-ttu-id="89981-121">Настройка хранения личных контактов на клиентских компьютерах для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="89981-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="89981-122">См. также</span><span class="sxs-lookup"><span data-stu-id="89981-122">See also</span></span>

[<span data-ttu-id="89981-123">Планирование интеграции Skype для бизнеса и Exchange</span><span class="sxs-lookup"><span data-stu-id="89981-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)