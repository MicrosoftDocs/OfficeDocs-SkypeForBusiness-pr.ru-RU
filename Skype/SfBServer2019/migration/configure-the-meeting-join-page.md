---
title: Конфигурация страницы присоединения к собранию
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Когда пользователь щелкает ссылку собрания в приглашении на собрание, собрание страницы присоединения к обнаруживает клиента уже установленной на компьютере пользователя. Если клиент уже установлен, этот клиент открывает и присоединился к собранию. Если клиент не установлен, по умолчанию откроется веб-приложения.
ms.openlocfilehash: 88ae915318505efef6ae716a17217aaa1e7b12df
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238718"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="fbc91-105">Конфигурация страницы присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="fbc91-105">Configure the meeting join page</span></span>

<span data-ttu-id="fbc91-106">Когда пользователь щелкает ссылку собрания в приглашении на собрание, собрание страницы присоединения к обнаруживает клиента уже установленной на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="fbc91-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="fbc91-107">Если клиент уже установлен, этот клиент открывает и присоединился к собранию.</span><span class="sxs-lookup"><span data-stu-id="fbc91-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="fbc91-108">Если клиент не установлен, по умолчанию откроется веб-приложения.</span><span class="sxs-lookup"><span data-stu-id="fbc91-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="fbc91-109">Можно изменить поведение присоединения к собранию страницы, чтобы разрешить пользователям присоединяться к собраниям.</span><span class="sxs-lookup"><span data-stu-id="fbc91-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="fbc91-110">Эти параметры конфигурации были удалены из панели управления, но их настройка с помощью командлета CsWebServiceConfiguration.</span><span class="sxs-lookup"><span data-stu-id="fbc91-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="fbc91-111">**Параметры CsWebServiceConfiguration для страницы присоединения к собранию**</span><span class="sxs-lookup"><span data-stu-id="fbc91-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="fbc91-112">**Параметр CsWebServiceConfiguration**</span><span class="sxs-lookup"><span data-stu-id="fbc91-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="fbc91-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="fbc91-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fbc91-114">ShowJoinUsingLegacyClientLink</span><span class="sxs-lookup"><span data-stu-id="fbc91-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="fbc91-115">Если задано значение True, пользователи, присоединяющиеся к собранию с помощью клиентского приложения, отличного от Lync получит возможность присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="fbc91-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="fbc91-116">Значение по умолчанию — False.</span><span class="sxs-lookup"><span data-stu-id="fbc91-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="fbc91-117">ShowAlternateJoinOptionsExpanded</span><span class="sxs-lookup"><span data-stu-id="fbc91-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="fbc91-118">Если параметр имеет значение True, альтернативные варианты для присоединение к конференции в режиме online будет автоматически развернут и отображается для пользователей.</span><span class="sxs-lookup"><span data-stu-id="fbc91-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="fbc91-119">Если параметр имеет значение False (значение по умолчанию), эти параметры будут доступны, но пользователь будет иметь для отображения списка параметров для себя.</span><span class="sxs-lookup"><span data-stu-id="fbc91-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="fbc91-120">Настройка собрания страницы присоединения к с помощью Скайп для консоли 2019 Business Server</span><span class="sxs-lookup"><span data-stu-id="fbc91-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="fbc91-121">Запустите Скайп для консоли 2019 Business Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы**, щелкните **Скайп Microsoft для Business Server 2019**и нажмите кнопку **Скайп для консоли Business Server**.</span><span class="sxs-lookup"><span data-stu-id="fbc91-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="fbc91-122">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="fbc91-122">Run the following cmdlet:</span></span> 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="fbc91-123">Этот командлет возвращает параметры конфигурации службы веб-сайта.</span><span class="sxs-lookup"><span data-stu-id="fbc91-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="fbc91-124">Выполните следующую команду, с помощью параметров установлено значение True или False, в зависимости от ваших предпочтений (для получения дополнительных сведений о параметрах для этого командлета см [Скайп для консоли Business Server](../../SfbServer/manage/management-shell.md) ):</span><span class="sxs-lookup"><span data-stu-id="fbc91-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


