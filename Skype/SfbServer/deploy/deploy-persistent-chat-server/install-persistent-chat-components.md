---
title: Установка компонентов сохраняемой беседы в Skype для бизнеса Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 61370aa6-9708-4ff8-b531-b258a928806f
description: Сводка. В этом разделе вы узнаете, как использовать мастер развертывания Skype для бизнеса Server для установки компонентов и служб Skype для бизнеса Server 2015.
ms.openlocfilehash: c3e68d5b5a41d06544f030df6877828da4b87c9e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802089"
---
# <a name="install-persistent-chat-components-in-skype-for-business-server-2015"></a><span data-ttu-id="144e7-103">Установка компонентов сохраняемой беседы в Skype для бизнеса Server 2015</span><span class="sxs-lookup"><span data-stu-id="144e7-103">Install Persistent Chat components in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="144e7-104">**Сводка:** В этом разделе вы узнаете, как использовать мастер развертывания Skype для бизнеса Server для установки компонентов и служб Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="144e7-104">**Summary:** Read this topic to learn how to use the Skype for Business Server Deployment Wizard to install Skype for Business Server 2015 components and services.</span></span>
  
<span data-ttu-id="144e7-105">Перед установкой компонентов сохраняемой беседы убедитесь, что уже установлено необходимое оборудование и программное обеспечение, а также создана соответствующая топология для поддержки сервера сохраняемой беседы.</span><span class="sxs-lookup"><span data-stu-id="144e7-105">Before you install Persistent Chat components, be sure you have already installed prerequisite hardware and software, and created the appropriate topology to support Persistent Chat Server.</span></span> <span data-ttu-id="144e7-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and Plan for Persistent Chat Server in Skype for Business Server [2015.](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="144e7-106">For details about planning and requirements, see [Requirements for your Skype for Business environment](../../plan-your-deployment/requirements-for-your-environment/requirements-for-your-environment.md) and [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md).</span></span> <span data-ttu-id="144e7-107">Сведения об обновлении и публикации топологии для добавления сервера сохраняемой беседы см. в подстройки "Добавление сервера сохраняемой беседы в топологию Skype для бизнеса [Server 2015".](add-persistent-chat-server.md)</span><span class="sxs-lookup"><span data-stu-id="144e7-107">For information about how to update and publish your topology to include Persistent Chat Server, see [Add Persistent Chat Server to your Skype for Business Server 2015 topology](add-persistent-chat-server.md).</span></span>
  
> [!NOTE] 
> <span data-ttu-id="144e7-108">Сохраняемая беседа доступна в Skype для бизнеса Server 2015, но больше не поддерживается в Skype для бизнеса Server 2019.</span><span class="sxs-lookup"><span data-stu-id="144e7-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="144e7-109">Такие же функции доступны в Teams.</span><span class="sxs-lookup"><span data-stu-id="144e7-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="144e7-110">Дополнительные сведения [см. в сведениях о том,](/microsoftteams/upgrade-start-here)как начать обновление Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="144e7-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="144e7-111">Если необходимо использовать сохраняемого чата, вы можете либо перенести пользователей, которым требуются эти функции, в Teams, либо продолжить использование Skype для бизнеса Server 2015.</span><span class="sxs-lookup"><span data-stu-id="144e7-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

## <a name="install-and-start-services"></a><span data-ttu-id="144e7-112">Установка и запуск служб</span><span class="sxs-lookup"><span data-stu-id="144e7-112">Install and start services</span></span>

<span data-ttu-id="144e7-113">С помощью мастера развертывания Skype для бизнеса Server выберите "Установка или обновление системы Skype для бизнеса Server", чтобы выполнить следующие действия:</span><span class="sxs-lookup"><span data-stu-id="144e7-113">Using the Skype for Business Server Deployment Wizard, choose Install or Update Skype for Business Server System to perform the following steps:</span></span> 
  
1. <span data-ttu-id="144e7-114">Установка локального хранилища конфигурации</span><span class="sxs-lookup"><span data-stu-id="144e7-114">Install Local Configuration Store</span></span>
    
2. <span data-ttu-id="144e7-115">Установка или удаление компонентов Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="144e7-115">Setup or Remove Skype for Business Server Components</span></span>
    
3. <span data-ttu-id="144e7-116">Запрос, установка или назначение сертификатов</span><span class="sxs-lookup"><span data-stu-id="144e7-116">Request, Install or Assign Certificates</span></span>
    
4. <span data-ttu-id="144e7-117">Запуск служб</span><span class="sxs-lookup"><span data-stu-id="144e7-117">Start services</span></span>
    
<span data-ttu-id="144e7-118">Дополнительные сведения об использовании мастера развертывания для установки компонентов, назначения сертификатов и запуска служб см. в сведениях об установке Skype для бизнеса [Server 2015](../../deploy/install/install.md) и установке Skype для бизнеса [Server 2015](../../deploy/install/install-skype-for-business-server.md)на серверах в топологии.</span><span class="sxs-lookup"><span data-stu-id="144e7-118">For details on how to use the Deployment Wizard to install components, assign certificates, and start services, see [Install Skype for Business Server 2015](../../deploy/install/install.md) and [Install Skype for Business Server 2015 on servers in the topology](../../deploy/install/install-skype-for-business-server.md).</span></span>
  

