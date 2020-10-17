---
title: 'Lync Server 2013: Настройка приглашения на собрание'
description: 'Lync Server 2013: Настройка приглашения на собрание.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the meeting invitation
ms:assetid: 7faa4797-0344-418b-9fa3-59dfb9c2baf7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398638(v=OCS.15)
ms:contentKeyID: 48184641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 64438d7a451cb794c125207fa594e1c00b534c80
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564335"
---
# <a name="configuring-the-meeting-invitation-in-lync-server-2013"></a><span data-ttu-id="5d1ad-103">Настройка приглашения на собрание в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5d1ad-103">Configuring the meeting invitation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d1ad-104">_**Последнее изменение темы:** 2013-07-16_</span><span class="sxs-lookup"><span data-stu-id="5d1ad-104">_**Topic Last Modified:** 2013-07-16_</span></span>

<span data-ttu-id="5d1ad-105">Вы можете настроить приглашения на собрания, отправляемые надстройкой "собрание по сети" для Lync 2013, включив следующие необязательные элементы в текст приглашения на собрание:</span><span class="sxs-lookup"><span data-stu-id="5d1ad-105">You can customize meeting invitations sent by the Online Meeting Add-in for Lync 2013 by including the following optional items in the body of the meeting invitation:</span></span>

  - <span data-ttu-id="5d1ad-106">**Логотип организации** Добавьте логотип организации в приглашения на собрания с помощью параметра URL-адрес логотипа.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-106">**Your organization’s logo** Add your organization’s logo to meeting invitations by using the Logo URL option.</span></span> <span data-ttu-id="5d1ad-107">если приглашения на собрания будут отправляться людям вне организации, то изображение эмблемы должно располагаться по общедоступному URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-107">If meeting invitations will be sent to people external to your organization, the image should be located at a publicly available URL.</span></span> <span data-ttu-id="5d1ad-108">Поддерживаются форматы изображений GIF и JPG.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-108">The supported image formats are GIF and JPG.</span></span> <span data-ttu-id="5d1ad-109">Несмотря на то, что в Lync Server 2013 хранится URL-адрес без ограничений на размер изображения, для достижения лучших результатов максимальный размер изображения должен быть равен 30 пикселов в высоту (188 x ширина).</span><span class="sxs-lookup"><span data-stu-id="5d1ad-109">Although Lync Server 2013 stores the URL with no size restrictions on the image, for best results, the maximum size of the image should be 30 pixels high by 188 pixels wide.</span></span>

  - <span data-ttu-id="5d1ad-110">**Ссылка на настраиваемую справку или поддержку** Добавьте URL-адрес веб-сайта группы справки или поддержки вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-110">**A Custom Help or Support Link** Add a URL for your organization’s help or support team website.</span></span> <span data-ttu-id="5d1ad-111">Если приглашения на собрания будут отправляться людям вне организации, то этот URL-адрес должен быть общедоступным.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-111">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="5d1ad-112">Максимальная длина URL-адреса — 1 КБ.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-112">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="5d1ad-113">**Юридический текст заявления об отказе** Добавьте URL-адрес для юридического текста или заявление об отказе, которое будет отображаться во всех приглашениях на собрания.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-113">**Legal disclaimer text** Add a URL for legal text or a disclaimer that will be displayed in all meeting invitations.</span></span> <span data-ttu-id="5d1ad-114">Если приглашения на собрания будут отправляться людям вне организации, то этот URL-адрес должен быть общедоступным.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-114">If meeting invitations will be sent to people external to your organization, the URL should be publicly available.</span></span> <span data-ttu-id="5d1ad-115">Максимальная длина URL-адреса — 1 КБ.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-115">The maximum URL length is 1 KB.</span></span>

  - <span data-ttu-id="5d1ad-116">**Настраиваемый текст нижнего колонтитула** Добавьте текст, который будет отображаться в приглашении в качестве настраиваемого нижнего колонтитула.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-116">**Custom footer text** Add text that will be rendered as a custom footer in the invitation.</span></span> <span data-ttu-id="5d1ad-117">Максимальная длина этого текста — 2 КБ.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-117">The maximum length of text that can be added is 2 KB.</span></span>

<span data-ttu-id="5d1ad-118">Эти параметры можно настроить с помощью панели управления Lync Server или командной консоли Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-118">You can configure these options by using either Lync Server Control Panel or Lync Server Management Shell.</span></span>

<div>


<span data-ttu-id="5d1ad-119">**Настройка приглашения на собрание с помощью панели управления Lync Server**</span><span class="sxs-lookup"><span data-stu-id="5d1ad-119">**To Customize the Meeting Invitation by using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="5d1ad-120">Из учетной записи пользователя, которая является членом группы RTCUniversalServerAdmins (или имеет эквивалентные права пользователя) или назначается роли CsServerAdministrator или CsAdministrator, войдите на любой компьютер в сети, в которой развернут Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-120">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or assigned to the CsServerAdministrator or CsAdministrator role, log on to any computer that is in the network in which you deployed Lync Server 2013.</span></span>

2.  <span data-ttu-id="5d1ad-121">Откройте окно браузера и введите URL-адрес администрирования, чтобы открыть панель управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-121">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="5d1ad-122">Для получения дополнительных сведений о различных методах, которые можно использовать для запуска панели управления Lync Server, ознакомьтесь со статьей [Open Lync server 2013 администрирование](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="5d1ad-122">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="5d1ad-123">В левой панели навигации последовательно нажмите пункты **Conferencing (Конференц-связь)** и **Meeting Configuration (Конфигурация собрания)**.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-123">In the left navigation bar, click **Conferencing** and then click **Meeting Configuration**.</span></span>

4.  <span data-ttu-id="5d1ad-124">На странице **конфигурации собрания** нажмите **New (Создать)**, а затем выполните одно из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-124">On the **Meeting Configuration** page, click **New**, and then do one of the following:</span></span>
    
      - <span data-ttu-id="5d1ad-p106">Чтобы создать политику на уровне узла, выберите пункт **Site configuration (Конфигурация узла)**. В поле поиска **Select a Site (Выбор узла)** введите имя (или часть имени) узла, для которого требуется определить параметры присоединения к собранию. В появившемся списке узлов выберите нужный и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-p106">To create a site-level policy, click **Site configuration**. In the **Select a Site** search field, type all or part of the name of the site for which you want to define meeting join settings. In the resulting list of sites, click the site you want, and then click **OK**.</span></span>
    
      - <span data-ttu-id="5d1ad-p107">Чтобы создать политику на уровне пула, выберите пункт **Pool configuration (Конфигурация пула)**. В поле поиска **Select a Service (Выбор службы)** введите имя (или его часть) службы пула, для которой требуется определить параметры присоединения к собранию. В появившемся списке служб выберите нужный пул и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-p107">To create a pool-level policy, click **Pool configuration**. In the **Select a Service** search field, type all or part of the name of the pool service for which you want to define meeting join settings. In the resulting list of services, click the pool you want, and then click **OK**.</span></span>

5.  <span data-ttu-id="5d1ad-131">Выполните любые из следующих действий.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-131">Do any of the following:</span></span>
    
      - <span data-ttu-id="5d1ad-132">В поле **Logo URL (URL-адрес эмблемы)** введите URL-адрес изображения эмблемы вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-132">In the **Logo URL** field, type the URL for your organization’s logo image.</span></span>
    
      - <span data-ttu-id="5d1ad-133">В поле **Help URL (URL-адрес справки)** введите URL-адрес сайта справки или службы поддержки вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-133">In the **Help URL** field, type the URL to your organization’s help or support site.</span></span>
    
      - <span data-ttu-id="5d1ad-134">В поле **Legal text (Юридическое заявление)** введите URL-адрес юридического заявления или заявления об отказе от ответственности, которое требуется включить в приглашения на собрания.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-134">In the **Legal text** field, type the URL to the legal text or disclaimer that you want to include in meeting invitations.</span></span>
    
      - <span data-ttu-id="5d1ad-135">В поле **Custom footer text (Текст нижнего колонтитула)** введите текст нижнего колонтитула объемом до 2 КБ.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-135">In the **Custom footer text** field, type footer text, up to 2 KB.</span></span>

<span data-ttu-id="5d1ad-136">**Настройка приглашения на собрание с помощью командной консоли Lync Server**</span><span class="sxs-lookup"><span data-stu-id="5d1ad-136">**To Customize the Meeting Invitation by using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="5d1ad-137">Запустите командную консоль Lync Server: нажмите кнопку **Пуск**, последовательно выберите пункты **Все программы** и **Microsoft Lync Server 2013** и щелкните элемент **Командная консоль Lync Server**.</span><span class="sxs-lookup"><span data-stu-id="5d1ad-137">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="5d1ad-p108">Выполните командлет **New-CsMeetingConfiguration** или **Set-CsMeetingConfiguration**, чтобы создать или настроить параметры приглашения на собрание. Например, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5d1ad-p108">Run the **New-CsMeetingConfiguration** or **Set-CsMeetingConfiguration** cmdlet to create or configure the meeting invitation options. For example, run:</span></span>
    
        New-CsMeetingConfiguration -Identity site:Redmond -LogoURL "http://www.contoso.com/logo/contosobanner.gif" -HelpURL "http://www.contoso.com/support" -LegalURL "http://www.contoso.com/disclaimer" -CustomFooterText "Communications may be monitored or recorded."

</div>

</div>

<span> </span>

</div>

</div>

</div>

