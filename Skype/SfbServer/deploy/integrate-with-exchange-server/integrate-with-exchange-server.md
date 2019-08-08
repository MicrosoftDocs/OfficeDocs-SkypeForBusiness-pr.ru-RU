---
title: Интеграция сервера Skype для бизнеса с сервером Exchange Server
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
description: 'Аннотация: Ознакомьтесь с этапами интеграции Exchange Server 2016 или Exchange Server 2013 и Skype для бизнеса Server.'
ms.openlocfilehash: 398ded1c138743c79de0e372b930dacef08fd94f
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244045"
---
# <a name="integrate-skype-for-business-server-with-exchange-server"></a><span data-ttu-id="e3658-103">Интеграция сервера Skype для бизнеса с сервером Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e3658-103">Integrate Skype for Business Server with Exchange Server</span></span>

<span data-ttu-id="e3658-104">**Сводка:** Ознакомьтесь с этапами интеграции Exchange Server 2013 или более поздней версии и Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="e3658-104">**Summary:** Review integration steps for Exchange Server 2013 or later and Skype for Business Server.</span></span>

<span data-ttu-id="e3658-105">Сервер Exchange Server 2013 или более поздней версии и Skype для бизнеса Server совместимы и интегрируются.</span><span class="sxs-lookup"><span data-stu-id="e3658-105">Exchange Server 2013 or later and Skype for Business Server are compatible and integrate well.</span></span> <span data-ttu-id="e3658-106">Например, информацию о присутствии пользователей в Skype для бизнеса можно сообщить в Microsoft Outlook; Кроме того, Skype для бизнеса может получить доступ к календарю Outlook пользователя, обратите внимание на то, что на собрании пользователя запланировано собрание и отображается состояние присутствия пользователя во время собрания.</span><span class="sxs-lookup"><span data-stu-id="e3658-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="e3658-107">Несмотря на то, что для работы с Skype для бизнеса Server (или наоборот) вам не нужно запускать сервер Exchange Server, эти два продукта вместе расширяют возможности взаимодействия с пользователем.</span><span class="sxs-lookup"><span data-stu-id="e3658-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>

<span data-ttu-id="e3658-108">В этой документации содержатся сведения об интеграции Skype для бизнеса Server и Exchange Server 2016 или Exchange Server 2013, но предполагается, что первоначальная настройка и конфигурация этих двух продуктов уже произошел.</span><span class="sxs-lookup"><span data-stu-id="e3658-108">This documentation provides information on integrating Skype for Business Server and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="e3658-109">Подробнее о том, как развернуть Skype для бизнеса Server, можно найти в [центре технической поддержки Skype для бизнеса Server](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span><span class="sxs-lookup"><span data-stu-id="e3658-109">For details about deploying Skype for Business Server see the [Skype for Business Server Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="e3658-110">Дополнительные сведения о развертывании Exchange Server можно найти в документации по развертыванию этой версии Exchange.</span><span class="sxs-lookup"><span data-stu-id="e3658-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>

<span data-ttu-id="e3658-111">Если вы собираетесь установить локальную версию Skype для бизнеса Server в Microsoft Exchange Online, ознакомьтесь с разделами [Настройка интеграции между локальными приложениями Skype для бизнеса Server и Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="e3658-111">If you are integrating an on premises installation of Skype for Business Server with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server and Outlook Web App](outlook-web-app.md).</span></span>

<span data-ttu-id="e3658-112">Если вы интегрирует Skype для бизнеса Online на локальный сервер Exchange Server, ознакомьтесь со сведениями в разделе [Настройка OAuth между Skype для бизнеса Online и Exchange в локальной среде](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="e3658-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="e3658-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="e3658-113">In this section</span></span>

[<span data-ttu-id="e3658-114">Настройка партнерских приложений в Skype для бизнеса Server и Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e3658-114">Configure partner applications in Skype for Business Server and Exchange Server</span></span>](configure-partner-applications.md)

[<span data-ttu-id="e3658-115">Настройка сервера Skype для бизнеса Server для использования архивации Exchange Server</span><span class="sxs-lookup"><span data-stu-id="e3658-115">Configure Skype for Business Server to use Exchange Server archiving</span></span>](use-exchange-archiving.md)

[<span data-ttu-id="e3658-116">Настройка поиска архивных данных Skype для бизнеса на сервере SharePoint</span><span class="sxs-lookup"><span data-stu-id="e3658-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)

[<span data-ttu-id="e3658-117">Настройка Skype для бизнеса Server для работы с единым хранилищем контактов</span><span class="sxs-lookup"><span data-stu-id="e3658-117">Configure Skype for Business Server to use the unified contact store</span></span>](use-the-unified-contact-store.md)

[<span data-ttu-id="e3658-118">Настройка использования фотографий высокого разрешения в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e3658-118">Configure the use of high-resolution photos in Skype for Business Server</span></span>](high-resolution-photos.md)

[<span data-ttu-id="e3658-119">Настройка единой системы обмена сообщениями Exchange Server для голосовой почты Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e3658-119">Configure Exchange Server Unified Messaging for Skype for Business Server voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)

[<span data-ttu-id="e3658-120">Интеграция Skype для бизнеса Server и Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="e3658-120">Integrating Skype for Business Server and Microsoft Outlook Web App 2013</span></span>](https://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)

[<span data-ttu-id="e3658-121">Настройка хранилища личных контактов на клиентских компьютерах для Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="e3658-121">Configure the personal contacts store on client computers for Skype for Business Server</span></span>](personal-contacts-store.md)

## <a name="see-also"></a><span data-ttu-id="e3658-122">См. также</span><span class="sxs-lookup"><span data-stu-id="e3658-122">See also</span></span>

[<span data-ttu-id="e3658-123">Планирование интеграции Skype для бизнеса и Exchange</span><span class="sxs-lookup"><span data-stu-id="e3658-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)
