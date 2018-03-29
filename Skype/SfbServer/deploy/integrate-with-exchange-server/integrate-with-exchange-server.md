---
title: Интеграция Skype для бизнеса Server 2015 с Exchange Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 795dc1c6-524f-4012-8b66-103b55198044
description: 'Сводка: Просмотрите этапы интеграции для Exchange Server 2016 или Exchange Server 2013 и Скайп для Business Server 2015.'
ms.openlocfilehash: c8cbecd6b78e3dc14ad2133a93d9fc2d1f6bb3d6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/28/2018
---
# <a name="integrate-skype-for-business-server-2015-with-exchange-server"></a><span data-ttu-id="0a38d-103">Интеграция Skype для бизнеса Server 2015 с Exchange Server</span><span class="sxs-lookup"><span data-stu-id="0a38d-103">Integrate Skype for Business Server 2015 with Exchange Server</span></span>
 
<span data-ttu-id="0a38d-104">**Сводка:** Просмотрите этапы интеграции для Exchange Server 2016 или Exchange Server 2013 и Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0a38d-104">**Summary:** Review integration steps for Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0a38d-105">Exchange Server 2016 или Exchange Server 2013 и Скайп для Business Server 2015 совместимости и интеграции.</span><span class="sxs-lookup"><span data-stu-id="0a38d-105">Exchange Server 2016 or Exchange Server 2013 and Skype for Business Server 2015 are compatible and integrate well.</span></span> <span data-ttu-id="0a38d-106">Например могут быть выявлены Скайп для бизнес-информация присутствия пользователя в Microsoft Outlook; Аналогичным образом Скайп для бизнеса можно получить доступ к календарю Outlook, обратите внимание, что у пользователя есть время совещания, запланированного и показывать состояние присутствия пользователя «занят» во время собрания.</span><span class="sxs-lookup"><span data-stu-id="0a38d-106">For example, Skype for Business user presence information can be reported in Microsoft Outlook; likewise, Skype for Business can access a user's Outlook calendar, notice the user has a meeting scheduled, and show the user's presence as Busy during the meeting.</span></span> <span data-ttu-id="0a38d-107">Несмотря на то, что не нужно выполнить Exchange Server, чтобы запустить Скайп для Business Server (и наоборот) двух продуктов друг с другом расширить возможности пользователей друг друга.</span><span class="sxs-lookup"><span data-stu-id="0a38d-107">Although you do not have to run Exchange Server in order to run Skype for Business Server (or vice-versa) the two products together enhance each other's user experience.</span></span>
  
<span data-ttu-id="0a38d-108">В этой документации содержит сведения об интеграции Скайп Business Server 2015, Exchange Server 2016 или Exchange Server 2013, но предполагается начальной установки и настройки этих двух продуктов уже выполнена.</span><span class="sxs-lookup"><span data-stu-id="0a38d-108">This documentation provides information on integrating Skype for Business Server 2015 and Exchange Server 2016 or Exchange Server 2013, but it assumes the initial setup and configuration of these two products has already happened.</span></span> <span data-ttu-id="0a38d-109">Для получения дополнительных сведений о развертывании Скайп для Business Server 2015 видеть [Скайп for Business Server 2015 Технический центр](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span><span class="sxs-lookup"><span data-stu-id="0a38d-109">For details about deploying Skype for Business Server 2015 see the [Skype for Business Server 2015 Tech Center](https://go.microsoft.com/fwlink/p/?LinkId=246127).</span></span> <span data-ttu-id="0a38d-110">Для получения дополнительных сведений о развертывании Exchange Server см документации по развертыванию для вашей версии Exchange.</span><span class="sxs-lookup"><span data-stu-id="0a38d-110">For details about deploying Exchange Server see the deployment documentation for your version of Exchange.</span></span>
  
<span data-ttu-id="0a38d-111">Если вы реализуете интеграцию на локальном установки Скайп для 2015 Business Server с Microsoft Exchange Online, ознакомьтесь со [Настройка интеграции между локальной Скайп Business Server 2015 и Outlook Web App](outlook-web-app.md).</span><span class="sxs-lookup"><span data-stu-id="0a38d-111">If you are integrating an on premises installation of Skype for Business Server 2015 with Microsoft Exchange Online, see [Configure integration between on-premises Skype for Business Server 2015 and Outlook Web App](outlook-web-app.md).</span></span>
  
<span data-ttu-id="0a38d-112">Если вы реализуете интеграцию Скайп для бизнеса в Интернет с помощью Exchange Server при локальном, видеть [Настройка OAuth между Скайп для бизнеса в Интернет и Exchange при локальном](oauth-with-online-and-on-premises.md).</span><span class="sxs-lookup"><span data-stu-id="0a38d-112">If you are integrating Skype for Business Online with Exchange Server on premises, see [Configure OAuth between Skype for Business Online and Exchange on premises](oauth-with-online-and-on-premises.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="0a38d-113">Содержание</span><span class="sxs-lookup"><span data-stu-id="0a38d-113">In this section</span></span>

[<span data-ttu-id="0a38d-114">Настройка партнерских приложений в Скайп для Business Server 2015 и Exchange Server</span><span class="sxs-lookup"><span data-stu-id="0a38d-114">Configure partner applications in Skype for Business Server 2015 and Exchange Server</span></span>](configure-partner-applications.md)
  
[<span data-ttu-id="0a38d-115">Настройка Скайп для 2015 Business Server для использования архивации Exchange Server</span><span class="sxs-lookup"><span data-stu-id="0a38d-115">Configure Skype for Business Server 2015 to use Exchange Server archiving</span></span>](use-exchange-archiving.md)
  
[<span data-ttu-id="0a38d-116">Настройка SharePoint Server для поиска архивированных Скайп для бизнес-данных</span><span class="sxs-lookup"><span data-stu-id="0a38d-116">Configure SharePoint Server to search for archived Skype for Business data</span></span>](sharepoint-to-search-for-archived-data.md)
  
[<span data-ttu-id="0a38d-117">Настройка Скайп для 2015 Business Server для использования в единое хранилище контактов</span><span class="sxs-lookup"><span data-stu-id="0a38d-117">Configure Skype for Business Server 2015 to use the unified contact store</span></span>](use-the-unified-contact-store.md)
  
[<span data-ttu-id="0a38d-118">Настройка использования фотографий высокого разрешения в Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0a38d-118">Configure the use of high-resolution photos in Skype for Business Server 2015</span></span>](high-resolution-photos.md)
  
[<span data-ttu-id="0a38d-119">Настройка единой системы обмена сообщениями Exchange Server для Скайп Business Server 2015 голосовой почты</span><span class="sxs-lookup"><span data-stu-id="0a38d-119">Configure Exchange Server Unified Messaging for Skype for Business Server 2015 voice mail</span></span>](exchangeunified-messaging-for-voice-mail.md)
  
[<span data-ttu-id="0a38d-120">Интеграция Скайп for Business Server 2015 и Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="0a38d-120">Integrating Skype for Business Server 2015 and Microsoft Outlook Web App 2013</span></span>](http://technet.microsoft.com/library/513d4cc7-aa87-4f68-b99d-d58b63bdf242.aspx)
  
[<span data-ttu-id="0a38d-121">Настройка хранилища личных контактов на клиентских компьютерах для Скайп для Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0a38d-121">Configure the personal contacts store on client computers for Skype for Business Server 2015</span></span>](personal-contacts-store.md)
  
## <a name="see-also"></a><span data-ttu-id="0a38d-122">См. также</span><span class="sxs-lookup"><span data-stu-id="0a38d-122">See also</span></span>

#### 

[<span data-ttu-id="0a38d-123">Планирование интеграции Скайп для бизнеса и Exchange</span><span class="sxs-lookup"><span data-stu-id="0a38d-123">Plan to integrate Skype for Business and Exchange</span></span>](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)

