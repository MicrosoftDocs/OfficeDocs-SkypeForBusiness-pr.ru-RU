---
title: Конфигурация страницы присоединения к собранию
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: End User
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Когда пользователь щелкает ссылку на собрание в приглашении на собрание, страница присоединения к собранию определяет, какой клиент уже установлен на компьютере пользователя. Если клиент уже установлен, этот клиент открывает и присоединяется к собранию. Если клиент не установлен, по умолчанию откроется веб-приложение.
ms.openlocfilehash: c5f6cd5b1d04b54f8db9f82080bc8dbabefdc11e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/20/2019
ms.locfileid: "34298279"
---
# <a name="configure-the-meeting-join-page"></a><span data-ttu-id="d13b7-105">Конфигурация страницы присоединения к собранию</span><span class="sxs-lookup"><span data-stu-id="d13b7-105">Configure the meeting join page</span></span>

<span data-ttu-id="d13b7-106">Когда пользователь щелкает ссылку на собрание в приглашении на собрание, страница присоединения к собранию определяет, какой клиент уже установлен на компьютере пользователя.</span><span class="sxs-lookup"><span data-stu-id="d13b7-106">When a user clicks a meeting link in a meeting request, the meeting join page detects which client is already installed on the user's computer.</span></span> <span data-ttu-id="d13b7-107">Если клиент уже установлен, этот клиент открывает и присоединяется к собранию.</span><span class="sxs-lookup"><span data-stu-id="d13b7-107">If a client is already installed, that client opens and joins the meeting.</span></span> <span data-ttu-id="d13b7-108">Если клиент не установлен, по умолчанию откроется веб-приложение.</span><span class="sxs-lookup"><span data-stu-id="d13b7-108">If a client is not installed, by default the Web App opens.</span></span>
  
<span data-ttu-id="d13b7-109">Если вы хотите разрешить пользователям присоединяться к собраниям, вы можете изменить поведение страницы присоединения к собранию.</span><span class="sxs-lookup"><span data-stu-id="d13b7-109">You can modify the behavior of the meeting join page if you want to allow users to join meetings.</span></span> <span data-ttu-id="d13b7-110">Эти параметры конфигурации были удалены из панели управления, но их можно настроить с помощью командлета Ксвебсервицеконфигуратион.</span><span class="sxs-lookup"><span data-stu-id="d13b7-110">These configuration options have been removed from the Control Panel, but you configure them by using the CsWebServiceConfiguration cmdlet.</span></span>
  
<span data-ttu-id="d13b7-111">**Параметры Ксвебсервицеконфигуратион на странице присоединения к собранию**</span><span class="sxs-lookup"><span data-stu-id="d13b7-111">**Meeting Join Page CsWebServiceConfiguration Parameters**</span></span>

|<span data-ttu-id="d13b7-112">**Параметр Ксвебсервицеконфигуратион**</span><span class="sxs-lookup"><span data-stu-id="d13b7-112">**CsWebServiceConfiguration Parameter**</span></span>|<span data-ttu-id="d13b7-113">**Описание**</span><span class="sxs-lookup"><span data-stu-id="d13b7-113">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d13b7-114">Шовжоинусинглегациклиентлинк</span><span class="sxs-lookup"><span data-stu-id="d13b7-114">ShowJoinUsingLegacyClientLink</span></span>  <br/> |<span data-ttu-id="d13b7-115">Если установлено значение true, пользователи, присоединяющиеся к собранию с помощью клиентского приложения, отличного от Lync, получают возможность присоединиться к собранию.</span><span class="sxs-lookup"><span data-stu-id="d13b7-115">If set to True, users joining a meeting by using a client application other than Lync will be given the opportunity to join the meeting.</span></span> <span data-ttu-id="d13b7-116">Значение по умолчанию — False.</span><span class="sxs-lookup"><span data-stu-id="d13b7-116">The default value is False.</span></span>  <br/> |
|<span data-ttu-id="d13b7-117">Шовалтернатежоиноптионсекспандед</span><span class="sxs-lookup"><span data-stu-id="d13b7-117">ShowAlternateJoinOptionsExpanded</span></span>  <br/> |<span data-ttu-id="d13b7-118">Если установлено значение true, дополнительные параметры для присоединения к онлайн-конференции автоматически развертываются и появятся для пользователей.</span><span class="sxs-lookup"><span data-stu-id="d13b7-118">When set to True, alternate options for joining an online conference will automatically be expanded and shown to users.</span></span> <span data-ttu-id="d13b7-119">Если задано значение false (по умолчанию), эти параметры будут доступны, но пользователю потребуется отобразить список параметров.</span><span class="sxs-lookup"><span data-stu-id="d13b7-119">When set to False (the default value), these options will be available, but the user will have to display the list of options for themselves.</span></span>  <br/> |
   
### <a name="to-configure-the-meeting-join-page-by-using-skype-for-business-server-2019-management-shell"></a><span data-ttu-id="d13b7-120">Настройка страницы присоединения к собранию с помощью управляющей оболочки Skype для Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="d13b7-120">To configure the meeting join page by using Skype for Business Server 2019 Management Shell</span></span>

1. <span data-ttu-id="d13b7-121">Запустите консоль управления Skype для бизнеса Server 2019: нажмите кнопку **Пуск**, выберите пункт **все программы**, а затем — **Microsoft Skype для бизнеса Server 2019**и выберите пункт **консоль управления Skype для бизнеса Server**.</span><span class="sxs-lookup"><span data-stu-id="d13b7-121">Start the Skype for Business Server 2019 Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="d13b7-122">Выполнить следующий командлет:</span><span class="sxs-lookup"><span data-stu-id="d13b7-122">Run the following cmdlet:</span></span> 
    
   ```
   Get-CsWebServiceConfiguration
   ```

    <span data-ttu-id="d13b7-123">Этот командлет возвращает параметры конфигурации веб-службы.</span><span class="sxs-lookup"><span data-stu-id="d13b7-123">This cmdlet returns the web service configuration settings.</span></span>
    
3. <span data-ttu-id="d13b7-124">Выполните следующую команду, указав для параметров значение истина или ложь, в зависимости от вашего предпочтения (Дополнительные сведения о параметрах этого командлета можно найти в документации по консоли [управления в Skype для бизнеса Server](../../SfbServer/manage/management-shell.md) ).</span><span class="sxs-lookup"><span data-stu-id="d13b7-124">Run the following command, with the parameters set to True or False, depending on your preference (for details about the parameters for this cmdlet, see the [Skype for Business Server Management Shell](../../SfbServer/manage/management-shell.md) documentation):</span></span>
    
   ```
   Set-CsWebServiceConfiguration -Identity global -ShowJoinUsingLegacyClientLink $True
   ```


