---
title: Конфигурация страницы присоединения к собранию
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Когда пользователь щелкает ссылку на собрание в запросе на собрание, страница присоединиться к собранию определяет, какой клиент уже установлен на компьютере пользователя. Если клиент уже установлен, он открывается и выполняет присоединение к собранию. Если клиент не установлен, по умолчанию открывается Веб-приложение.
ms.openlocfilehash: a7bb0983438708bbc0d30cd527eb494491c3cbf2
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754029"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="67177-105">Конфигурация страницы присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="67177-105">Configure the meeting join page</span></span>

<span data-ttu-id="67177-106">Когда пользователь щелкает ссылку на собрание в запросе на собрание, страница присоединиться к собранию определяет, какой клиент уже установлен на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="67177-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="67177-107">Если клиент уже установлен, он открывается и выполняет присоединение к собранию.</span><span class="sxs-lookup"><span data-stu-id="67177-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="67177-108">Если клиент не установлен, по умолчанию открывается Веб-приложение.</span><span class="sxs-lookup"><span data-stu-id="67177-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="67177-109">Вы можете изменить поведение страницы присоединить к собранию, если хотите разрешить пользователям присоединяться к собраниям.</span><span class="sxs-lookup"><span data-stu-id="67177-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="67177-110">Эти параметры конфигурации были удалены из панели управления, но настраиваются с помощью cmdlet CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="67177-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="67177-111">**Параметры командлета CsWebServiceConfiguration для настройки страницы присоединения к собранию**</span><span class="sxs-lookup"><span data-stu-id="67177-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="67177-112">**Параметр командлета CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="67177-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="67177-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="67177-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="67177-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="67177-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="67177-115">Если задано true, пользователи, присоединяясь к собранию с помощью клиентского приложения, кроме Lync, будут иметь возможность присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="67177-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="67177-116">Значение по умолчанию — False.</span><span class="sxs-lookup"><span data-stu-id="67177-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="67177-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="67177-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="67177-118">Если параметр установлен в true, альтернативные варианты присоединения к онлайн-конференции будут автоматически расширены и показаны пользователям.</span><span class="sxs-lookup"><span data-stu-id="67177-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="67177-119">Если параметр имеет значение False (значение по умолчанию), эти параметры будут доступны, но пользователю придется отобразить список параметров самостоятельно.</span><span class="sxs-lookup"><span data-stu-id="67177-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="67177-120">Настройка страницы пользования собраниями с помощью оболочки управления Skype для бизнеса Server 2019</span><span class="sxs-lookup"><span data-stu-id="67177-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="67177-121">Запустите оболочку управления Skype для бизнеса Server 2019: нажмите кнопку "Начните", выберите команды "Все программы", "Microsoft Skype для бизнеса Server **2019"** и "Skype для бизнеса Server Management **Shell".**</span><span class="sxs-lookup"><span data-stu-id="67177-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="67177-122">Выполните следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="67177-122">Run the following cmdlet:</span></span> 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="67177-123">Этот командлет возвращает параметры конфигурации веб-службы.</span><span class="sxs-lookup"><span data-stu-id="67177-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="67177-124">В зависимости от предпочтений запустите следующую команду с параметрами True или False (подробные сведения о параметрах для этого командлета см. в документации по командной оболочке Skype для бизнеса [Server):](../../SfbServer/manage/management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="67177-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


