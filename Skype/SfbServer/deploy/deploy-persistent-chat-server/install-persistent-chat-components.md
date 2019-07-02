---
title: Установка компонентов для сохраняемого чата в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: 'Аннотация: Ознакомьтесь с этой статьей, чтобы получить сведения о том, как использовать мастер развертывания Skype для бизнеса Server для установки компонентов и служб Skype для бизнеса Server 2015.'
ms.openlocfilehash: 2b19599ff3523a1b96a2349d62c948ed3fe72d7b
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418162"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="b9375-103">Установка компонентов для сохраняемого чата в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="b9375-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b9375-104">**Сводка:** В этой статье рассказывается, как использовать мастер развертывания Skype для бизнеса Server для установки компонентов и служб Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b9375-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="b9375-105">Прежде чем устанавливать компоненты сохраняемого чата, убедитесь, что вы уже установили необходимые оборудование и программное обеспечение и создали подходящую топологию для поддержки сервера сохраняемого чата.</span><span class="sxs-lookup"><span data-stu-id="b9375-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="b9375-106">Подробные сведения о планировании и требованиях можно найти в разделе [требования к среде Skype для бизнеса](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) и [Планирование постоянного сервера чата в Skype для бизнеса Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="b9375-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="b9375-107">Сведения о том, как обновлять и публиковать топологию, чтобы включить сохраняемый сервер чата, приведены в разделе [Добавление сохраняемого сервера чата в топологию 2015 в Skype для бизнеса Server](add-persistent-chat-server.md).</span><span class="sxs-lookup"><span data-stu-id="b9375-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="b9375-108">Сохраняемый чат доступен в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b9375-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b9375-109">Эта функция доступна в Teams.</span><span class="sxs-lookup"><span data-stu-id="b9375-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="b9375-110">Дополнительные сведения можно найти в разделе [Начало работы с обновлением Microsoft Teams](/microsoftteams/upgrade-start-here).</span><span class="sxs-lookup"><span data-stu-id="b9375-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="b9375-111">Если вы хотите использовать сохраняемый чат, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить работу с Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="b9375-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="b9375-112">Установка и запуск служб</span><span class="sxs-lookup"><span data-stu-id="b9375-112">Install and start services</span></span>

<span data-ttu-id="b9375-113">С помощью мастера развертывания Skype для бизнеса Server выберите Установка или обновление системы Skype для бизнеса Server, чтобы выполнить указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="b9375-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="b9375-114">Установка локального хранилища конфигурации</span><span class="sxs-lookup"><span data-stu-id="b9375-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="b9375-115">Установка или удаление компонентов Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="b9375-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="b9375-116">Запрос, установка или назначение сертификатов</span><span class="sxs-lookup"><span data-stu-id="b9375-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="b9375-117">Запуск служб</span><span class="sxs-lookup"><span data-stu-id="b9375-117">Start services</span></span>
    
<span data-ttu-id="b9375-118">Подробнее о том, как использовать мастер развертывания для установки компонентов, назначения сертификатов и запуска служб, можно найти в разделе [Установка Skype для бизнеса server 2015](../../deploy/install/install.md) и [Установка Skype для бизнеса Server 2015 на серверах в топологии](../../deploy/install/install-skype-for-business-server.md).</span><span class="sxs-lookup"><span data-stu-id="b9375-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

