---
title: Изменение простых URL-адресов после миграции
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Change simple URLs after migration
ms:assetid: addb0dc8-8324-42b1-9a00-f4bd14fdf5c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721844(v=OCS.15)
ms:contentKeyID: 49733777
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a24eda274734e0c5a27fab30640a363de6653514
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726729"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="change-simple-urls-after-migration"></a><span data-ttu-id="c7ad0-102">Изменение простых URL-адресов после миграции</span><span class="sxs-lookup"><span data-stu-id="c7ad0-102">Change simple URLs after migration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7ad0-103">_**Тема последнего изменения:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="c7ad0-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="c7ad0-104">Lync Server поддерживает три простых URL-адреса:</span><span class="sxs-lookup"><span data-stu-id="c7ad0-104">Lync Server supports three simple URLs:</span></span>

  - <span data-ttu-id="c7ad0-105">" **Встреча** " используется в качестве базового URL-адреса для всех конференций на сайте или в Организации.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-105">**Meet** is used as the base URL for all conferences in the site or organization.</span></span> <span data-ttu-id="c7ad0-106">С помощью простого URL-адреса вы можете легко усвоеновать ссылки на собрания, а также легко и распространены.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-106">With the Meet simple URL, links to join meetings are easy to comprehend, and easy to communicate and distribute.</span></span>

  - <span data-ttu-id="c7ad0-107">С помощью **телефонного подключения** можно получить доступ к веб-странице параметров конференций с телефонным подключением.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-107">**Dial-in** enables access to the Dial-in Conferencing Settings webpage.</span></span> <span data-ttu-id="c7ad0-108">Простой URL-адрес телефонного подключения включается во все приглашения на собрания. Таким образом пользователи, которые хотят подключиться к собранию по телефону, могут найти в нем необходимый номер телефона и ПИН-код.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-108">The Dial-in simple URL is included in all meeting invitations so that users who want to dial in to the meeting can access the necessary phone number and PIN information.</span></span>

  - <span data-ttu-id="c7ad0-109">**Администратор** обеспечивает быстрый доступ к панели управления Lync Server.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-109">**Admin** enables quick access to the Lync Server Control Panel.</span></span> <span data-ttu-id="c7ad0-110">Этот URL-адрес используется внутри организации.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-110">The Admin simple URL is internal to your organization.</span></span>

<span data-ttu-id="c7ad0-111">После перехода на Lync Server 2013 необходимо учитывать, как это изменение влияет на записи DNS и сертификаты для простых URL-адресов.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-111">After migrating to Lync Server 2013, you must be aware of how the change impacts your DNS records and certificates for simple URLs.</span></span> <span data-ttu-id="c7ad0-112">Если в вашей топологии используется устаревший режиссер Lync Server 2010, изменения, внесенные в простой URL-адрес, не требуются.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-112">If the legacy Lync Server 2010 Director remains in use in the topology, no changes to your simple URLs are required.</span></span> <span data-ttu-id="c7ad0-113">Если режиссер Lync Server 2010 удаляется из топологии после миграции, необходимо обновить простые DNS-записи, чтобы они указывали на один из пулов Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-113">If the Lync Server 2010 Director is removed from the topology after migration, the simple URL DNS records must be updated to point to one of the Lync Server 2013 pools.</span></span> <span data-ttu-id="c7ad0-114">Однако каждый раз, когда вы изменяете простое имя URL-адреса, вы должны выполнить команду Enable-Кскомпутер для каждого директора и сервера переднего плана для регистрации изменения.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-114">Whenever you change a simple URL name, however, you must run Enable-CsComputer on each Director and Front End Server to register the change.</span></span>

<div>

## <a name="changing-simple-urls-after-migration"></a><span data-ttu-id="c7ad0-115">Изменение простых URL-адресов после миграции</span><span class="sxs-lookup"><span data-stu-id="c7ad0-115">Changing Simple URLs after Migration</span></span>

<span data-ttu-id="c7ad0-116">**Обновление простого URL-адреса для собрания**</span><span class="sxs-lookup"><span data-stu-id="c7ad0-116">**To update the Meet simple URL**</span></span>

1.  <span data-ttu-id="c7ad0-117">В построителе топологии щелкните правой кнопкой мыши верхний узел **Lync Server**и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-117">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="c7ad0-118">В левой области выберите **простые URL** -адреса, а затем — URL-адреса для **собраний:** выберите в поле "адрес для собрания" и нажмите кнопку **изменить URL-адрес**.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-118">Select **Simple URLs** in the left pane, then below **Meeting URLs:** select the Meet URL and then click **Edit URL**.</span></span>

3.  <span data-ttu-id="c7ad0-119">Установите для URL-адреса нужное значение и нажмите кнопку **ОК**, чтобы сохранить измененный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-119">Update the URL to the value you want, and then click **OK** to save the edited URL.</span></span>

<span data-ttu-id="c7ad0-120">**Обновление простого URL-адреса администратора**</span><span class="sxs-lookup"><span data-stu-id="c7ad0-120">**To update the Admin simple URL**</span></span>

1.  <span data-ttu-id="c7ad0-121">В построителе топологии щелкните правой кнопкой мыши верхний узел **Lync Server**и выберите команду **изменить свойства**.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-121">In Topology Builder, right-click the top node **Lync Server**, and then click **Edit Properties**.</span></span>

2.  <span data-ttu-id="c7ad0-122">Выберите **простые URL-адреса** в левой области, а затем в поле **URL-адрес администратора** введите простой URL-адрес, который вы хотите использовать для административного доступа к панели управления Lync Server 2013, а затем нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-122">Select **Simple URLs** in the left pane, then below **Administrative access URL** box, enter the simple URL you want for administrative access to Lync Server 2013 Control Panel, and then click **OK**.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="c7ad0-123">В качестве URL-адреса администрирования рекомендуется использовать максимально простой URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="c7ad0-123">We recommend using the simplest possible URL for the Admin URL.</span></span> <span data-ttu-id="c7ad0-124">Это самый простой вариант <STRONG> https://admin.</STRONG> &lt;Domain&gt;(домен).</span><span class="sxs-lookup"><span data-stu-id="c7ad0-124">The simplest option is <STRONG>https://admin.</STRONG>&lt;domain&gt;.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c7ad0-125">См. также</span><span class="sxs-lookup"><span data-stu-id="c7ad0-125">See Also</span></span>


[<span data-ttu-id="c7ad0-126">Планирование простых URL-адресов в Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c7ad0-126">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

