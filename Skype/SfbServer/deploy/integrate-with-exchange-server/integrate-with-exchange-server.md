---
title: Интеграция Skype для бизнеса Server с Exchange Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 12/20/2018
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Сводка: Ознакомьтесь с действиями по интеграции для Exchange Server 2016 или Exchange Server 2013 и Skype для бизнеса Server.'
ms.openlocfilehash: 398ded1c138743c79de0e372b930dacef08fd94f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244045"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="704f2-103">Интеграция Skype для бизнеса Server с Exchange Server</span><span class="sxs-lookup"><span data-stu-id="704f2-103">Integrate Skype for Business Server 2015 with Exchange Server</span></span>

<span data-ttu-id="704f2-104">**Сводка:** Ознакомьтесь с действиями по интеграции для Exchange Server 2013 или более поздней версией и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="704f2-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="704f2-105">Exchange Server 2013 или более поздней версии и Skype для бизнеса Server совместимы и хорошо интегрируются.</span><span class="sxs-lookup"><span data-stu-id="704f2-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="704f2-106">Например, сведения о присутствии пользователя Skype для бизнеса можно просматривать в Microsoft Outlook; аналогично Skype для бизнеса может получить доступ к календарю пользователя Outlook, отметить наличие запланированного собрания у пользователя и во время собрания показывать присутствие пользователя как "Занят".</span><span class="sxs-lookup"><span data-stu-id="704f2-106">For example, skype16_client user presence information can be reported in Microsoft Outlook; likewise, skype16_client can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="704f2-107">Хотя Exchange Server не требуется для использования Skype для бизнеса Server (и наоборот), оба продукта вместе расширяют взаимные возможности взаимодействия пользователей.</span><span class="sxs-lookup"><span data-stu-id="704f2-107">Although you do not have to run ExchangeServer in order to run skype16_server_short (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="704f2-108">В этом документе приводятся сведения о том, как интегрировать Skype для бизнеса Server и Exchange Server 2016 или Exchange Server 2013, при этом предполагается, что первоначальная настройка и конфигурирование этих двух продуктов уже были выполнены.</span><span class="sxs-lookup"><span data-stu-id="704f2-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="704f2-109">Дополнительные сведения о развертывании Skype для бизнеса Server, см. в [Центре технической поддержки Skype для бизнеса Server](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span><span class="sxs-lookup"><span data-stu-id="704f2-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="704f2-110">Подробности по развертыванию Exchange Server см. в документации по развертыванию для вашей версии Exchange.</span><span class="sxs-lookup"><span data-stu-id="704f2-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="704f2-111">В случае интеграции локальной установки Skype для бизнеса с Microsoft Exchange Online, см. раздел [Настройка интеграции между локальной системой Skype для бизнеса Server и Outlook Web App](outlook-web-app.md),</span><span class="sxs-lookup"><span data-stu-id="704f2-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="704f2-112">В случае локальной интеграции Skype для бизнеса Online с Exchange Server см. раздел [Настройка подключения по протоколу OAuth между Skype для бизнеса Online и локальной системой Exchange](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="704f2-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="704f2-113">В этом разделе</span><span class="sxs-lookup"><span data-stu-id="704f2-113">In this section</span></span>

[<span data-ttu-id="704f2-114">Настройка партнерских приложений в Skype для бизнеса Server и Exchange Server</span><span class="sxs-lookup"><span data-stu-id="704f2-114">Configure partner applications in Skype for Business Server 2015 and Microsoft Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="704f2-115">Настройка Skype для бизнеса Server на использование архивирования Exchange Server</span><span class="sxs-lookup"><span data-stu-id="704f2-115">Configure Skype for Business Server to use Exchange archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="704f2-116">Настройка поиска архивных данных Skype для бизнеса на сервере SharePoint</span><span class="sxs-lookup"><span data-stu-id="704f2-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="704f2-117">Настройка Skype для бизнеса Server для работы с единым хранилищем контактов</span><span class="sxs-lookup"><span data-stu-id="704f2-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="704f2-118">Настройка использования фотографий высокого разрешения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="704f2-118">Configure the use of high-resolution photos in Skype for Business Server 2015</span></span>](high-resolution-photos.md)

[<span data-ttu-id="704f2-119">Настройка единой системы обмена сообщениями Exchange Server для голосовой почты Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="704f2-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="704f2-120">Взаимодействие Skype для бизнеса Server с Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="704f2-120">Integrating Skype for Business Server 2015 and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="704f2-121">Настройка хранилища личных контактов на клиентских компьютерах для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="704f2-121">Configure the personal contacts store on client computers for Skype for Business Server 2015</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="704f2-122">См. также</span><span class="sxs-lookup"><span data-stu-id="704f2-122">See also</span></span>

[<span data-ttu-id="704f2-123">Планирование интеграции Skype для бизнеса и Exchange</span><span class="sxs-lookup"><span data-stu-id="704f2-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
