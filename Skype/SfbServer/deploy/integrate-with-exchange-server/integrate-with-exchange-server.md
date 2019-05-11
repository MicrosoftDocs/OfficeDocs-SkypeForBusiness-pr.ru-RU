---
title: Интеграция Скайп для Business Server с Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Сводка: Просмотрите действия по интеграции для Exchange Server 2016 или Exchange Server 2013 и Скайп for Business Server.'
ms.openlocfilehash: e5e33e77c60aa4be0ae28f21945d9ce5dccddfc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "33891714"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="e689a-103">Интеграция Скайп для Business Server с Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e689a-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="e689a-104">**Сводка:** Просмотрите этапы интеграции для Exchange Server 2013 или более поздней версии и Скайп for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e689a-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="e689a-105">Скайп для Business Server и Exchange Server 2013 или более поздняя версия совместимости и интеграции.</span><span class="sxs-lookup"><span data-stu-id="e689a-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="e689a-106">Например могут быть выявлены Скайп для бизнес-информация присутствия пользователя в Microsoft Outlook; Аналогичным образом Скайп для бизнеса можно получить доступ к календарю Outlook, обратите внимание, что у пользователя есть время совещания, запланированного и показывать состояние присутствия пользователя «занят» во время собрания.</span><span class="sxs-lookup"><span data-stu-id="e689a-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="e689a-107">Несмотря на то, что не нужно выполнить Exchange Server, чтобы запустить Скайп для Business Server (и наоборот) двух продуктов друг с другом расширить возможности пользователей друг друга.</span><span class="sxs-lookup"><span data-stu-id="e689a-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="e689a-108">В этой документации содержит сведения об интеграции Скайп Business Server и Exchange Server 2016 или Exchange Server 2013, но предполагается начальной установки и настройки этих двух продуктов уже выполнена.</span><span class="sxs-lookup"><span data-stu-id="e689a-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="e689a-109">Для получения дополнительных сведений о развертывании Скайп для Business Server см [Скайп for Business Server Технический центр](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span><span class="sxs-lookup"><span data-stu-id="e689a-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="e689a-110">Для получения дополнительных сведений о развертывании Exchange Server см документации по развертыванию для вашей версии Exchange.</span><span class="sxs-lookup"><span data-stu-id="e689a-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="e689a-111">Если вы реализуете интеграцию на локальном установки Скайп для Business Server с Microsoft Exchange Online, ознакомьтесь со [Настройка интеграции между локальной Скайп для Business Server и Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="e689a-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="e689a-112">Если вы реализуете интеграцию Скайп для бизнеса в Интернет с помощью Exchange Server при локальном, видеть [Настройка OAuth между Скайп для бизнеса в Интернет и Exchange при локальном](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="e689a-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e689a-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="e689a-113">In this section</span></span>

[<span data-ttu-id="e689a-114">Настройка партнерских приложений в Скайп Business Server и Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e689a-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="e689a-115">Настройка Скайп для бизнес-сервера архивирование Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e689a-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="e689a-116">Настройка поиска архивных данных Skype для бизнеса на сервере SharePoint</span><span class="sxs-lookup"><span data-stu-id="e689a-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="e689a-117">Настройка Skype для бизнеса Server для работы с единым хранилищем контактов</span><span class="sxs-lookup"><span data-stu-id="e689a-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="e689a-118">Настройка использования фотографий высокого разрешения в Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="e689a-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="e689a-119">Настройка единой системы обмена сообщениями Exchange Server для голосовой почты Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e689a-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="e689a-120">Интеграция Скайп for Business Server и Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="e689a-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="e689a-121">Настройка хранилища личных контактов на клиентских компьютерах для Скайп для Business Server</span><span class="sxs-lookup"><span data-stu-id="e689a-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="e689a-122">См. также</span><span class="sxs-lookup"><span data-stu-id="e689a-122">See also</span></span>

[<span data-ttu-id="e689a-123">Планирование интеграции Skype для бизнеса и Exchange</span><span class="sxs-lookup"><span data-stu-id="e689a-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
