---
title: Настройка страницы присоединения к собранию в Skype для бизнеса Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6537765e-4384-416f-92f1-a7f3b39ebe56
description: 'Сводка: сведения о настройке страницы присоединения к собранию в Skype для бизнеса Server.'
ms.openlocfilehash: 7381db4983b5a2c1ec6dccf474f0b381e079e222
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818520"
---
# <a name="configure-the-meeting-join-page-in-skype-for-business-server"></a><span data-ttu-id="a16ec-103">Настройка страницы присоединения к собранию в Skype для бизнеса Server</span><span class="sxs-lookup"><span data-stu-id="a16ec-103">Configure the meeting join page in Skype for Business Server</span></span>
 
<span data-ttu-id="a16ec-104">**Сводка:** Научитесь настраивать страницу присоединения к собраниям в Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a16ec-104">**Summary:** Learn how to configure the meeting join page in Skype for Business Server.</span></span>
  
<span data-ttu-id="a16ec-105">Когда пользователь щелкает ссылку на собрание в приглашении на собрание, страница присоединения к собранию определяет, установлен ли клиент Skype для бизнеса на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="a16ec-105">When a user clicks a meeting link in a meeting request, the meeting join page detects whether a Skype for Business client is already installed on the user's computer.</span></span> <span data-ttu-id="a16ec-106">Если клиент уже установлен, клиент открывает и присоединяется к собранию.</span><span class="sxs-lookup"><span data-stu-id="a16ec-106">If a client is already installed, the client opens and joins the meeting.</span></span> <span data-ttu-id="a16ec-107">Если клиент не установлен, по умолчанию откроется клиент Skype для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a16ec-107">If a client is not installed, by default the Skype for Business client opens.</span></span> 
  
## <a name="configure-the-meeting-join-page"></a><span data-ttu-id="a16ec-108">Конфигурация страницы присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="a16ec-108">Configure the meeting join page</span></span>

<span data-ttu-id="a16ec-109">Если вы хотите разрешить пользователям присоединяться к собраниям с другими версиями клиента, вы можете изменить поведение страницы присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="a16ec-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings with other versions of the client.</span></span> <span data-ttu-id="a16ec-110">Эти параметры конфигурации были удалены с панели управления Skype для бизнеса Server, но их можно настроить с помощью командлета Set-Ксвебсервицеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="a16ec-110">These configuration options have been removed from the Skype for Business Server Control Panel, but you configure them by using the Set-CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="a16ec-111">**Наборы страниц для присоединения к собранию — параметры Ксвебсервицеконфигуратион**</span><span class="sxs-lookup"><span data-stu-id="a16ec-111">**Meeting Join Page Set-CsWebServiceConfiguration parameters**</span></span>

|<span data-ttu-id="a16ec-112">**Параметр Set-Ксвебсервицеконфигуратион**</span><span class="sxs-lookup"><span data-stu-id="a16ec-112">**Set-CsWebServiceConfiguration parameter**</span></span>|<span data-ttu-id="a16ec-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="a16ec-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a16ec-114">шовжоинусинглегациклиентлинк</span><span class="sxs-lookup"><span data-stu-id="a16ec-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="a16ec-115">Этот параметр устарел для использования в локальной версии Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a16ec-115">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/> <span data-ttu-id="a16ec-116">Если установлено значение true, пользователи, присоединяющиеся к собранию с помощью клиентского приложения, отличного от Skype для бизнеса, получат возможность присоединиться к собранию с помощью текущего клиентского приложения.</span><span class="sxs-lookup"><span data-stu-id="a16ec-116">If set to True, users joining a meeting by using a client application other than Skype for Business will be given the opportunity to join the meeting by using their current client application.</span></span> <span data-ttu-id="a16ec-117">Значение по умолчанию — False.</span><span class="sxs-lookup"><span data-stu-id="a16ec-117">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="a16ec-118">шовалтернатежоиноптионсекспандед</span><span class="sxs-lookup"><span data-stu-id="a16ec-118">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="a16ec-119">Этот параметр устарел для использования в локальной версии Skype для бизнеса Server.</span><span class="sxs-lookup"><span data-stu-id="a16ec-119">This parameter has been deprecated for use with the on-premises version of Skype for Business Server.</span></span>  <br/>  <span data-ttu-id="a16ec-120">Если установлено значение true, дополнительные параметры для присоединения к онлайн-конференции автоматически развертываются и отображаются для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a16ec-120">If set to True, alternate options for joining an online conference are automatically expanded and shown to users.</span></span> <span data-ttu-id="a16ec-121">Если для этого параметра задано значение false (по умолчанию), эти параметры будут доступны, но пользователю потребуется отобразить список параметров.</span><span class="sxs-lookup"><span data-stu-id="a16ec-121">If set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   

