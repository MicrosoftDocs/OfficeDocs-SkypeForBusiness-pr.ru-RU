---
title: 'Lync Server 2013: Настройка приглашения на собрание'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 014a42597e3df416d9e502eaaa90e2f1e71e35ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2019
ms.locfileid: "34841177"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a><span data-ttu-id="1fd21-102">Настройка приглашения на собрание в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1fd21-102">Configuring the meeting invitation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1fd21-103">_**Тема последнего изменения:** 2013-07-16_</span><span class="sxs-lookup"><span data-stu-id="1fd21-103">_**Topic Last Modified:** 2013-07-16_</span></span>

<span data-ttu-id="1fd21-104">Вы можете настроить приглашения на собрание, отправленные надстройкой "собрание по сети" для Lync 2013, добавив следующие необязательные элементы в тексте приглашения на собрание.</span><span class="sxs-lookup"><span data-stu-id="1fd21-104">You can customize meeting invitations sent by the Online Meeting Add-in for Lync 2013 by including the following optional items in the body of the meeting invitation:</span></span>

  - <span data-ttu-id="1fd21-105">**Логотип вашей организации** Добавьте логотип своей организации в приглашения на собрание с помощью параметра URL-адрес эмблемы.</span><span class="sxs-lookup"><span data-stu-id="1fd21-105">**Your organization’s logo** Add your organization’s logo to meeting invitations by using the Logo URL option.</span></span> <span data-ttu-id="1fd21-106">Если приглашения на собрание будут отправляться людям, которые являются внешними по отношению к вашей организации, это изображение должно находиться по общедоступному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="1fd21-106">If meeting invitations will be sent to people external to your organization, the image should be located at a publicly available URL.</span></span> <span data-ttu-id="1fd21-107">Поддерживаются форматы изображений GIF и JPG.</span><span class="sxs-lookup"><span data-stu-id="1fd21-107">The supported image formats are GIF and JPG.</span></span> <span data-ttu-id="1fd21-108">Несмотря на то, что в Lync Server 2013 хранится URL-адрес без ограничений на размер изображения, для достижения наилучших результатов максимальный размер изображения должен составлять 30 пикселей в высоту на 188 пикселей по ширине.</span><span class="sxs-lookup"><span data-stu-id="1fd21-108">Although Lync Server 2013 stores the URL with no size restrictions on the image, for best results, the maximum size of the image should be 30 pixels high by 188 pixels wide.</span></span>

  - <span data-ttu-id="1fd21-109">**Ссылка на специальную справку или службу поддержки** Добавьте URL-адрес сайта группы справки или поддержки своей организации.</span><span class="sxs-lookup"><span data-stu-id="1fd21-109">**A Custom Help or Support Link** Add a URL for your organization’s help or support team website.</span></span> <span data-ttu-id="1fd21-110">Если приглашения на собрание будут отправляться людям, которые являются внешними по отношению к вашей организации, этот URL-адрес должен быть общедоступным.</span><span class="sxs-lookup"><span data-stu-id="1fd21-110">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="1fd21-111">Максимальная длина URL-адреса составляет 1 КБ.</span><span class="sxs-lookup"><span data-stu-id="1fd21-111">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="1fd21-112">**Текст заявления** об отказе от ответственности Добавьте URL-адрес для юридического текста или заявление об отказе, которое будет отображаться во всех приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="1fd21-112">**Legal disclaimer text** Add a URL for legal text or a disclaimer that will be displayed in all meeting invitations.</span></span> <span data-ttu-id="1fd21-113">Если приглашения на собрание будут отправляться людям, которые являются внешними по отношению к вашей организации, этот URL-адрес должен быть общедоступным.</span><span class="sxs-lookup"><span data-stu-id="1fd21-113">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="1fd21-114">Максимальная длина URL-адреса составляет 1 КБ.</span><span class="sxs-lookup"><span data-stu-id="1fd21-114">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="1fd21-115">**Настраиваемый текст нижнего колонтитула** Добавьте текст, который будет отображаться в приглашении в качестве настраиваемого нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="1fd21-115">**Custom footer text** Add text that will be rendered as a custom footer in the invitation.</span></span> <span data-ttu-id="1fd21-116">Максимальная длина текста, который может быть добавлен, составляет 2 КБ.</span><span class="sxs-lookup"><span data-stu-id="1fd21-116">The maximum length of text that can be added is 2 KB.</span></span>

<span data-ttu-id="1fd21-117">Эти параметры можно настроить с помощью панели управления Lync Server либо из командной консоли Lync Server Management.</span><span class="sxs-lookup"><span data-stu-id="1fd21-117">You can configure these options by using either Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>


<span data-ttu-id="1fd21-118">**Настройка приглашения на собрание с помощью панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="1fd21-118">**To Customize the Meeting Invitation by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="1fd21-119">Войдите в учетную запись пользователя, которая является членом группы Рткуниверсалсерверадминс (или имеет эквивалентные права пользователей) или назначьте роль Кссерверадминистратор или Ксадминистратор, выполните вход на любой компьютер в сети, в которой вы развернули Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1fd21-119">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="1fd21-120">Откройте окно браузера и введите URL-адрес администратора, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1fd21-120">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1fd21-121">Дополнительные сведения о различных способах, которые можно использовать для запуска панели управления Lync Server, приведены в разделе [Открытие меню администрирования Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1fd21-121">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1fd21-122">На панели навигации слева выберите **Конференц** -связь, а затем — **Конфигурация собрания**.</span><span class="sxs-lookup"><span data-stu-id="1fd21-122">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="1fd21-123">На странице **Конфигурация собрания** нажмите кнопку **Создать**, а затем выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="1fd21-123">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="1fd21-p106">Чтобы создать политику уровня сайта, выберите вариант **Настройка сайта**. В поле поиска **Выбор сайта** частично или полностью введите имя сайта, для которого требуется определить параметры присоединения к собранию. В полученном списке сайтов выберите нужный сайт и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1fd21-p106">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="1fd21-p107">Чтобы создать политику уровня пула, выберите вариант **Конфигурация пула**. В поле поиска **Выбор службы** частично или полностью введите имя службы пула, для которой требуется определить параметры присоединения к собранию. В полученном списке служб выберите нужную службу и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="1fd21-p107">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="1fd21-130">Выполните одно из указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="1fd21-130">Do any of the following:</span></span>
    
      - <span data-ttu-id="1fd21-131">В поле **URL-адрес логотипа** введите URL-адрес изображения логотипа Организации.</span><span class="sxs-lookup"><span data-stu-id="1fd21-131">In the **Logo URL** field, type the URL for your organization’s logo image.</span></span>
    
      - <span data-ttu-id="1fd21-132">В поле **URL-адрес справки** введите URL-адрес сайта справки или службы поддержки Организации.</span><span class="sxs-lookup"><span data-stu-id="1fd21-132">In the **Help URL** field, type the URL to your organization’s help or support site.</span></span>
    
      - <span data-ttu-id="1fd21-133">В поле **юридическое текстовое** введите URL-адрес юридического или отказа, который вы хотите включить в приглашения на собрание.</span><span class="sxs-lookup"><span data-stu-id="1fd21-133">In the **Legal text** field, type the URL to the legal text or disclaimer that you want to include in meeting invitations.</span></span>
    
      - <span data-ttu-id="1fd21-134">В **текстовом поле настраиваемый нижний колонтитул** введите текст нижнего колонтитула длиной до 2 КБ.</span><span class="sxs-lookup"><span data-stu-id="1fd21-134">In the **Custom footer text** field, type footer text, up to 2 KB.</span></span>

<span data-ttu-id="1fd21-135">**Настройка приглашения на собрание с помощью командной консоли Lync Server Management Shell**</span><span class="sxs-lookup"><span data-stu-id="1fd21-135">**To Customize the Meeting Invitation by using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="1fd21-136">Запустите командную консоль Lync Server Management Shell: нажмите кнопку **Пуск**, выберите **все программы**, а затем — **Microsoft Lync Server 2013**, а затем — **Командная консоль Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1fd21-136">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="1fd21-137">Запустите командлет **New-ксмитингконфигуратион** или **Set-ксмитингконфигуратион** , чтобы создать или настроить параметры приглашения на собрание.</span><span class="sxs-lookup"><span data-stu-id="1fd21-137">Run the **New-CsMeetingConfiguration** or **Set-CsMeetingConfiguration** cmdlet to create or configure the meeting invitation options.</span></span> <span data-ttu-id="1fd21-138">Например, выполните командлет:</span><span class="sxs-lookup"><span data-stu-id="1fd21-138">For example, run:</span></span>
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

