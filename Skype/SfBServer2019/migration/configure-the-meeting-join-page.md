---
title: Конфигурация страницы присоединения к собранию
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Когда пользователь щелкает ссылку на собрание в приглашении на собрание, страница присоединения к собранию определяет, какой клиент уже установлен на компьютере пользователя. Если клиент уже установлен, этот клиент открывает и присоединяется к собранию. Если клиент не установлен, по умолчанию откроется веб-приложение.
ms.openlocfilehash: 5c9e6653783d90411e0f701b5d3395c569d8bdff
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989564"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="56cc5-105">Конфигурация страницы присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="56cc5-105">Configure the meeting join page</span></span>

<span data-ttu-id="56cc5-106">Когда пользователь щелкает ссылку на собрание в приглашении на собрание, страница присоединения к собранию определяет, какой клиент уже установлен на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="56cc5-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="56cc5-107">Если клиент уже установлен, этот клиент открывает и присоединяется к собранию.</span><span class="sxs-lookup"><span data-stu-id="56cc5-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="56cc5-108">Если клиент не установлен, по умолчанию откроется веб-приложение.</span><span class="sxs-lookup"><span data-stu-id="56cc5-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="56cc5-109">Если вы хотите разрешить пользователям присоединяться к собраниям, вы можете изменить поведение страницы присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="56cc5-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="56cc5-110">Эти параметры конфигурации были удалены из панели управления, но их можно настроить с помощью командлета Ксвебсервицеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="56cc5-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="56cc5-111">**Параметры Ксвебсервицеконфигуратион на странице присоединения к собранию**</span><span class="sxs-lookup"><span data-stu-id="56cc5-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="56cc5-112">**Параметр Ксвебсервицеконфигуратион**</span><span class="sxs-lookup"><span data-stu-id="56cc5-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="56cc5-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="56cc5-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="56cc5-114">шовжоинусинглегациклиентлинк</span><span class="sxs-lookup"><span data-stu-id="56cc5-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="56cc5-115">Если установлено значение true, пользователи, присоединяющиеся к собранию с помощью клиентского приложения, отличного от Lync, получают возможность присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="56cc5-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="56cc5-116">Значение по умолчанию — False.</span><span class="sxs-lookup"><span data-stu-id="56cc5-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="56cc5-117">шовалтернатежоиноптионсекспандед</span><span class="sxs-lookup"><span data-stu-id="56cc5-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="56cc5-118">Если установлено значение true, дополнительные параметры для присоединения к онлайн-конференции автоматически развертываются и появятся для пользователей.</span><span class="sxs-lookup"><span data-stu-id="56cc5-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="56cc5-119">Если задано значение false (по умолчанию), эти параметры будут доступны, но пользователю потребуется отобразить список параметров.</span><span class="sxs-lookup"><span data-stu-id="56cc5-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="56cc5-120">Настройка страницы присоединения к собранию с помощью управляющей оболочки Skype для Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="56cc5-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="56cc5-121">Запустите консоль управления Skype для бизнеса Server 2019: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Skype для бизнеса Server 2019**и выберите пункт **консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="56cc5-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="56cc5-122">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="56cc5-122">Run the following cmdlet:</span></span> 
    
   ```PowerShell
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="56cc5-123">Этот командлет возвращает параметры конфигурации веб-службы.</span><span class="sxs-lookup"><span data-stu-id="56cc5-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="56cc5-124">Выполните следующую команду, указав для параметров значение истина или ложь, в зависимости от вашего предпочтения (Дополнительные сведения о параметрах этого командлета можно найти в документации по консоли [управления в Skype для бизнеса Server](../../SfbServer/manage/management-shell.md) ).</span><span class="sxs-lookup"><span data-stu-id="56cc5-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```PowerShell
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


