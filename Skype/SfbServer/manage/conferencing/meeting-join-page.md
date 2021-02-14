---
title: Настройка страницы присоединить к собранию в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: Сводка. Сведения о настройке страницы присоединить к собранию в Skype для бизнеса Server.
ms.openlocfilehash: 247664a3ff4bbc4ee055775d26f1d077b662752b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828039"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="28ebf-103">Настройка страницы присоединить к собранию в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="28ebf-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="28ebf-104">**Сводка:** Узнайте, как настроить страницу присоединить к собранию в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="28ebf-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="28ebf-105">Когда пользователь щелкает ссылку на собрание в запросе на собрание, страница присоединиться к собранию определяет, установлен ли клиент Skype для бизнеса на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="28ebf-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="28ebf-106">Если клиент уже установлен, он открывается и присоединяется к собранию.</span><span class="sxs-lookup"><span data-stu-id="28ebf-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="28ebf-107">Если клиент не установлен, по умолчанию открывается клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="28ebf-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="28ebf-108">Конфигурация страницы присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="28ebf-108">Configure the meeting join page</span></span>

<span data-ttu-id="28ebf-109">Вы можете изменить поведение страницы присоединить к собранию, если хотите разрешить пользователям присоединяться к собраниям с другими версиями клиента.</span><span class="sxs-lookup"><span data-stu-id="28ebf-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="28ebf-110">Эти параметры конфигурации были удалены из панели управления Skype для бизнеса Server, но их можно настроить с помощью Set-CsWebServiceConfiguration управления.</span><span class="sxs-lookup"><span data-stu-id="28ebf-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="28ebf-111">**Параметры параметров Set-CsWebServiceConfiguration присоединить к собранию**</span><span class="sxs-lookup"><span data-stu-id="28ebf-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="28ebf-112">**Параметр Set-CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="28ebf-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="28ebf-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="28ebf-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="28ebf-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="28ebf-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="28ebf-115">Этот параметр больше не используется в локальной версии Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="28ebf-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="28ebf-116">Если задано true, пользователи, присоединяясь к собранию с помощью клиентского приложения, кроме Skype для бизнеса, будут иметь возможность присоединиться к собранию с помощью текущего клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="28ebf-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="28ebf-117">Значение по умолчанию — False.</span><span class="sxs-lookup"><span data-stu-id="28ebf-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="28ebf-118">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="28ebf-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="28ebf-119">Этот параметр больше не используется в локальной версии Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="28ebf-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="28ebf-120">Если установлено true, альтернативные варианты присоединения к конференции по сети автоматически расширяются и показываются пользователям.</span><span class="sxs-lookup"><span data-stu-id="28ebf-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="28ebf-121">Если установлено значение False (значение по умолчанию), эти параметры будут доступны, но пользователю придется отобразить список параметров для себя.</span><span class="sxs-lookup"><span data-stu-id="28ebf-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

