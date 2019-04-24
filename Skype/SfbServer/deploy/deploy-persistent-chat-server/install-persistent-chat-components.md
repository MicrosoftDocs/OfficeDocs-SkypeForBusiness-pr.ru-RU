---
title: Установка компонентов для сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Сводка: Прочтите этот раздел, чтобы узнать, как использовать Скайп для мастер развертывания Business Server для установки Скайп для компонентов Business Server 2015 и служб.'
ms.openlocfilehash: 78fb134ef8db5b0c47c890db9454858ff392a624
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32222304"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="0f7c4-103">Установка компонентов для сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="0f7c4-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0f7c4-104">**Сводка:** Прочтите этот раздел, чтобы узнать, как использовать Скайп для мастер развертывания Business Server для установки Скайп для компонентов Business Server 2015 и служб.</span><span class="sxs-lookup"><span data-stu-id="0f7c4-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="0f7c4-105">Перед установкой компонентов Persistent Chat, обязательно, уже установки необходимого оборудования и программного обеспечения и создания соответствующих топологии для поддержки серверов сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="0f7c4-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="0f7c4-106">Для получения дополнительных сведений о планировании и требования к просмотрите [требования к вашей Скайп для бизнес-среде](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) и [Планирование сервера сохраняемого чата в Скайп для Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="0f7c4-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="0f7c4-107">Сведения об обновлении и публикации топологии для включения сервера сохраняемого чата содержатся в разделе [Добавление сервера сохраняемого чата для вашей Скайп для топологии Business Server 2015](add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="0f7c4-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="0f7c4-108">Сохраняемый чат доступна в Скайп для Business Server 2015, но больше не поддерживается в Скайп для Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0f7c4-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0f7c4-109">Те же функциональные возможности доступны в группах.</span><span class="sxs-lookup"><span data-stu-id="0f7c4-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="0f7c4-110">Для получения дополнительных сведений см [Реализация из Скайп для бизнеса для групп Майкрософт](/microsoftteams/journey-skypeforbusiness-teams).</span><span class="sxs-lookup"><span data-stu-id="0f7c4-110">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="0f7c4-111">Если необходимо использовать сохраняемого чата, возможны либо перенос пользователей, которым требуется эта функция групп, или для дальнейшего использования Скайп для Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="0f7c4-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="0f7c4-112">Установка и запуск служб</span><span class="sxs-lookup"><span data-stu-id="0f7c4-112">Install and start services</span></span>

<span data-ttu-id="0f7c4-113">С помощью мастера развертывания сервера Business Скайп, выберите установить или обновление Скайп для бизнес-системе сервера, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="0f7c4-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="0f7c4-114">Установка локального хранилища конфигурации</span><span class="sxs-lookup"><span data-stu-id="0f7c4-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="0f7c4-115">Установка или удаление компонентов Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="0f7c4-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="0f7c4-116">Запрос, установка или назначение сертификатов</span><span class="sxs-lookup"><span data-stu-id="0f7c4-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="0f7c4-117">Запуск служб</span><span class="sxs-lookup"><span data-stu-id="0f7c4-117">Start services</span></span>
    
<span data-ttu-id="0f7c4-118">Для получения дополнительных сведений об использовании мастер развертывания для установки компонентов назначение сертификатов и запустите службы, [Установка Скайп для Business Server 2015](../../deploy/install/install.md) и [Установить Скайп для 2015 Business Server на серверах в топологии](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="0f7c4-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

