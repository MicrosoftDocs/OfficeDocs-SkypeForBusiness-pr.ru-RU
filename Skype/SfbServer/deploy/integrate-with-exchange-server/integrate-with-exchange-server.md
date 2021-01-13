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
description: Сводка. Обзор этапов интеграции для Exchange Server 2016 или Exchange Server 2013 и Skype для бизнеса Server.
ms.openlocfilehash: 6b5c63c0ad6783c11fd8fde25d1b00dc84d7e15a
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49833739"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="5ffff-103">Интеграция Skype для бизнеса Server с Exchange Server</span><span class="sxs-lookup"><span data-stu-id="5ffff-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="5ffff-104">**Сводка:** Просмотрите этапы интеграции Exchange Server 2013 или более поздней и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="5ffff-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="5ffff-105">Exchange Server 2013 или более поздней и Skype для бизнеса Server совместимы и хорошо интегрируются.</span><span class="sxs-lookup"><span data-stu-id="5ffff-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="5ffff-106">Например, сведения о присутствии пользователей Skype для бизнеса можно отчитаться в Microsoft Outlook; Кроме того, Skype для бизнеса может получить доступ к календарю пользователя в Outlook, заметить, что у пользователя запланировано собрание, и показать его присутствие как "Занят" во время собрания.</span><span class="sxs-lookup"><span data-stu-id="5ffff-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="5ffff-107">Хотя вам не нужно запускать Exchange Server, чтобы запустить Skype для бизнеса Server (или наоборот), эти два продукта вместе улучшают пользовательский интерфейс друг друга.</span><span class="sxs-lookup"><span data-stu-id="5ffff-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="5ffff-108">В этой документации содержится информация об интеграции Skype для бизнеса Server и Exchange Server 2016 или Exchange Server 2013, но предполагается, что первоначальная настройка и настройка этих двух продуктов уже произошли.</span><span class="sxs-lookup"><span data-stu-id="5ffff-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="5ffff-109">Дополнительные сведения о развертывании Skype для бизнеса Server см. в техническом [центре Skype для бизнеса Server.](https://go.microsoft.com/fwlink/p/?LinkId=246127)</span><span class="sxs-lookup"><span data-stu-id="5ffff-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="5ffff-110">Дополнительные сведения о развертывании Exchange Server см. в документации по развертыванию для вашей версии Exchange.</span><span class="sxs-lookup"><span data-stu-id="5ffff-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="5ffff-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="5ffff-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="5ffff-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="5ffff-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="5ffff-113">В этом разделе:</span><span class="sxs-lookup"><span data-stu-id="5ffff-113">In this section</span></span>

[<span data-ttu-id="5ffff-114">Настройка партнерских приложений в Skype для бизнеса Server и Exchange Server</span><span class="sxs-lookup"><span data-stu-id="5ffff-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="5ffff-115">Настройка Skype для бизнеса Server для использования Exchange Server архива</span><span class="sxs-lookup"><span data-stu-id="5ffff-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="5ffff-116">Настройка SharePoint Server для поиска архивных данных Skype для бизнеса</span><span class="sxs-lookup"><span data-stu-id="5ffff-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="5ffff-117">Настройка Skype для бизнеса Server для использования единого магазина контактов</span><span class="sxs-lookup"><span data-stu-id="5ffff-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="5ffff-118">Настройка использования фотографий высокого разрешения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5ffff-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="5ffff-119">Настройка единой Exchange Server для голосовой почты Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5ffff-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="5ffff-120">Интеграция Skype для бизнеса Server и Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="5ffff-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="5ffff-121">Настройка хранения личных контактов на клиентских компьютерах для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="5ffff-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="5ffff-122">См. также</span><span class="sxs-lookup"><span data-stu-id="5ffff-122">See also</span></span>

[<span data-ttu-id="5ffff-123">Планирование интеграции Skype для бизнеса и Exchange</span><span class="sxs-lookup"><span data-stu-id="5ffff-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
